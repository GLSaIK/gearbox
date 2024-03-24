# gearbox
UNSAT gearbox code

local speed = math.floor(getreg("speed"))
local wasd = getComponents("wasd")[1]
local pr = getreg("park")
local br = getreg("brake")
local a = 0

if wasd.isS() then
c = 1
else 
c = 0
end
if wasd.isW() then
a = 1
else 
a = 0
end

if a == 1 or c == 1 then
setreg("pr", false)
setreg("br", false)
end

if a == 0 and c == 0 then
setreg("br", true)
setreg("1", false)
setreg("2",false)
setreg("3",false)
setreg("4",false)
setreg("5",false)
end


if a == 1 and speed < 4 and wasd.isSeated() then
setreg("1", true)
end

if speed > 4 and speed < 15 and wasd.isSeated() and a == 1 then
setreg("2", true)
setreg("1", false)
end

if speed > 15 and speed <33 and wasd.isSeated() and a == 1 then
setreg("3", true)
setreg("2", false)
end

if speed > 33 and speed < 56 and wasd.isSeated() and a == 1 then
setreg("4", true)
setreg("3", false)
end


if speed > 56 and wasd.isSeated() and a == 1 then
setreg("5", true)
setreg("4", false)
else 
setreg("5", false)
end

if pr == 1 then
setreg("pr", true)
setreg("br", false)
end

if wasd.isS() then
setreg("2", true)
end

if wasd.isS() then 
setreg("s",true)
else
setreg("s",false)
end
if wasd.isW() then 
setreg("w",true)
else
setreg("w",false)
end

if wasd.isA() then 
setreg("a",true)
else
setreg("a",false)
end
if wasd.isD() then 
setreg("d",true)
else
setreg("d",false)
end

if wasd.isS() and getreg("bk") == 0 then
setreg("st", true)
else
setreg("st", false)
end
if wasd.isS() and getreg("bk") == 1 then
setreg("ba", true)
else
setreg("ba", false)
end
