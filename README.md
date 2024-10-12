local Player = owner
NLS([[local Player = game:GetService("Players").LocalPlayer
	
	local Char = Player.Character
	local Event = Char:WaitForChild("UserInput_Event")
	
	local UIS = game:GetService("UserInputService")
	
	local input = function(io,a)
	    if a then return end
		local io = {KeyCode=io.KeyCode,UserInputType=io.UserInputType,UserInputState=io.UserInputState}
		Event:FireServer(io)
	end
	UIS.InputBegan:Connect(input)
	UIS.InputEnded:Connect(input)
	local Changed = false
	local Mouse = Player:GetMouse()
	local h,t = Mouse.Hit,Mouse.Target
	while wait(1/30) do
		if h~=Mouse.Hit or t~=Mouse.Target then
			Event:FireServer({isMouse=true,Target=Mouse.Target,Hit=Mouse.Hit})
            h,t=Mouse.Hit,Mouse.Target
		end
	end]])

local Mouse,mouse,UserInputService,ContextActionService
do
	script.Parent = Player.Character
	local CAS = {Actions={}}
	local Event = Instance.new("RemoteEvent")
	Event.Name = "UserInput_Event"
	Event.Parent = Player.Character
	local fakeEvent = function()
		local t = {_fakeEvent=true}
		t.Connect = function(self,f)self.Function=f end
		t.connect = t.Connect
		return t
	end
    local m = {Target=nil,Hit=CFrame.new(),KeyUp=fakeEvent(),KeyDown=fakeEvent(),Button1Up=fakeEvent(),Button1Down=fakeEvent()}
	local UIS = {InputBegan=fakeEvent(),InputEnded=fakeEvent()}
	function CAS:BindAction(name,fun,touch,...)
		CAS.Actions[name] = {Name=name,Function=fun,Keys={...}}
	end
	function CAS:UnbindAction(name)
		CAS.Actions[name] = nil
	end
	local function te(self,ev,...)
		local t = m[ev]
		if t and t._fakeEvent and t.Function then
			t.Function(...)
		end
	end
	m.TrigEvent = te
	UIS.TrigEvent = te
	Event.OnServerEvent:Connect(function(plr,io)
	    if plr~=Player then return end
		if io.isMouse then
			m.Target = io.Target
			m.Hit = io.Hit
		elseif io.UserInputType == Enum.UserInputType.MouseButton1 then
	        if io.UserInputState == Enum.UserInputState.Begin then
				m:TrigEvent("Button1Down")
			else
				m:TrigEvent("Button1Up")
			end
		else
			for n,t in pairs(CAS.Actions) do
				for _,k in pairs(t.Keys) do
					if k==io.KeyCode then
						t.Function(t.Name,io.UserInputState,io)
					end
				end
			end
	        if io.UserInputState == Enum.UserInputState.Begin then
	            m:TrigEvent("KeyDown",io.KeyCode.Name:lower())
				UIS:TrigEvent("InputBegan",io,false)
			else
				m:TrigEvent("KeyUp",io.KeyCode.Name:lower())
				UIS:TrigEvent("InputEnded",io,false)
	        end
	    end
	end)
	Mouse,mouse,UserInputService,ContextActionService = m,m,UIS,CAS
	end

--  --
local S = setmetatable({},{__index = function(s,i) return game:service(i) end})
local cF = {N=CFrame.new,A=CFrame.Angles,fEA=CFrame.fromEulerAnglesXYZ}
local C3 = {tRGB= function(c3) return c3.r*255,c3.g*255,c3.b*255 end,N=Color3.new,RGB=Color3.fromRGB,HSV=Color3.fromHSV,tHSV=Color3.toHSV}
local V3 = {N=Vector3.new,FNI=Vector3.FromNormalId,A=Vector3.FromAxis}
local M = {C=math.cos,R=math.rad,S=math.sin,P=math.pi,RNG=math.random,MRS=math.randomseed,H=math.huge,RRNG = function(min,max,div) return math.rad(math.random(min,max)/(div or 1)) end}
local R3 = {N=Region3.new}
local De = S.Debris
local WS = workspace
local Lght = S.Lighting
local RepS = S.ReplicatedStorage
local IN = Instance.new
local Plrs = S.Players
local Alpha = .3
	
NewInstance = function(instance,parent,properties)
	local inst = Instance.new(instance)
	inst.Parent = parent
	if(properties)then
		for i,v in next, properties do
			pcall(function() inst[i] = v end)
		end
	end
	return inst;
end


-- Script --


plr = Player
char = plr.Character
hum = char.Humanoid
local cam = game.Workspace.CurrentCamera
Camera = cam
local CamInterrupt = false
local TwoD = false
local TargetInfo = {nil, nil}
cam.CameraType = "Custom"
t = char.Torso
h = char.Head
ra = char["Right Arm"]
la = char["Left Arm"]
rl = char["Right Leg"]
ll = char["Left Leg"]
tors = char.Torso
lleg = char["Left Leg"]
root = char.HumanoidRootPart
hed = char.Head
rleg = char["Right Leg"]
rarm = char["Right Arm"]
larm = char["Left Arm"]
radian = math.rad
random = math.random
Mrandom = math.random
Vec3 = Vector3.new
local God = true
Inst = Instance.new
cFrame = CFrame.new
Euler = CFrame.fromEulerAnglesXYZ
vt = Vector3.new
VT = Vector3.new
bc = BrickColor.new
br = BrickColor.random
it = Instance.new
IT = Instance.new
cf = CFrame.new
Cf = CFrame.new
SIN = math.sin
COS = math.cos
RAD = math.rad
BrickC = BrickColor.new
BRICKC = BrickColor.new
CF = CFrame.new
equipped = false
advanced = false
vt = Vector3.new
euler = CFrame.fromEulerAnglesXYZ
angles = CFrame.Angles
ANGLES = CFrame.Angles
local sine = 0
local SINE = 0
local RootCF = CFrame.fromEulerAnglesXYZ(-1.57, 0, 3.14)
local RHCF = CFrame.fromEulerAnglesXYZ(0, 1.6, 0)
local LHCF = CFrame.fromEulerAnglesXYZ(0, -1.6, 0)
radian = math.rad
random = math.random
Player_Size = 1
Cos = math.cos
Sin = math.sin
Rad = math.rad	
rad = math.rad	
MRANDOM = math.random
local Diversial = false
local enableddam = true
local DAMAGEMULTIPLIER = 1
--local etypemodes = "S"

local Effects = IT("Folder", Character)
Effects.Name = "Effects"


local Booleans = {CamFollow = true, GyroUse = true}

function lerp(object, newCFrame, alpha)
	return object:lerp(newCFrame, alpha)
end




local Directer = Inst("BodyGyro", root)
Directer.MaxTorque = Vec3(0, 0, 0)
Directer.P = 600000
local CPart = Inst("Part")
CPart.Anchored = true
CPart.CanCollide = false
CPart.Locked = true
CPart.Transparency = 1
local rval = 0
local rainbowmode = false
local chaosmode = false
local insanitymode = false
local universalchaos = false
local glitching = false



kan = Instance.new("Sound", char.Head)
kan.Volume = 1.98
kan.TimePosition = 0
kan.PlaybackSpeed = 1
kan.Pitch = 1
kan.SoundId = "rbxassetid://12489056016"
kan.Name = "wrecked"
kan.Looped = true
kan:Play()

local currentThemePlaying = kan.SoundId
local currentPitch = kan.Pitch
local currentVol = kan.Volume
function newTheme(ID,timepos,pitch,vol)
local kanz = kan
--kanz:Stop()
kanz.Volume = vol
--kanz.TimePosition = timepos
kanz.PlaybackSpeed = pitch
kanz.Pitch = pitch
kanz.SoundId = ID
kanz.Name = "wrecked"
kanz.Looped = true
currentThemePlaying = kanz.SoundId
currentVol = kanz.Volume
currentPitch = kanz.Pitch
--kanz:Play()
--coroutine.resume(coroutine.create(function()
--wait(0.05)
--end))
end

function Cso(ID, PARENT, VOLUME, PITCH)
	local NSound = nil
	coroutine.resume(coroutine.create(function()
		NSound = IT("Sound", PARENT)
		NSound.Volume = VOLUME
		NSound.Pitch = PITCH
		NSound.SoundId = "http://www.roblox.com/asset/?id="..ID
		task.wait()
		NSound:play()
		game:GetService("Debris"):AddItem(NSound, 10)
	end))
	return NSound
end
function newThemeCust(ID,timepos,pitch,vol)
local kanz = kan
kanz:Stop()
kanz.Volume = vol
kanz.TimePosition = timepos
kanz.PlaybackSpeed = pitch
kanz.Pitch = pitch
MID = ID
kanz.SoundId = ID
kanz.Name = "wrecked"
kanz.Looped = true
kanz:Play()
coroutine.resume(coroutine.create(function()
task.wait(0.05)
end))
end

local mutedtog = false



function CameraEnshaking(Length,Intensity)

end
CamShake=function(Part,Distan,Power,Times) 

end

local Instance = setmetatable({ClearChildrenOfClass = function(where,class,recursive) local children = (recursive and where:GetDescendants() or where:GetChildren()) for _,v in next, children do if(v:IsA(class))then v:destroy();end;end;end},{__index = Instance})

--// Require stuff \\--
function CamShake(who,times,intense,origin) 
	
end

function CamShakeAll(times,intense,origin)

end

function shakes(power,length)
	
end

function chatfunc(text, color)
	local chat = coroutine.wrap(function()
		if Character:FindFirstChild("TalkingBillBoard") ~= nil then
			Character:FindFirstChild("TalkingBillBoard"):destroy()
		end
		local naeeym2 = Instance.new("BillboardGui", Character)
		naeeym2.Size = UDim2.new(0, 100, 0, 40)
		naeeym2.StudsOffset = Vector3.new(0, 3, 0)
		naeeym2.Adornee = Character.Head
		naeeym2.Name = "TalkingBillBoard"
		local tecks2 = Instance.new("TextLabel", naeeym2)
		tecks2.BackgroundTransparency = 1
		tecks2.BorderSizePixel = 0
		tecks2.Text = ""
		tecks2.Font = "SciFi"
		tecks2.TextSize = 30
		tecks2.TextStrokeTransparency = 0
		tecks2.TextColor3 = color
		tecks2.TextStrokeColor3 = Color3.new(0, 0, 0)
		tecks2.Size = UDim2.new(1, 0, 0.5, 0)
		local tecks3 = Instance.new("TextLabel", naeeym2)
		tecks3.BackgroundTransparency = 1
		tecks3.BorderSizePixel = 0
		tecks3.Text = ""
		tecks3.Font = "SciFi"
		tecks3.TextSize = 30
		tecks3.TextStrokeTransparency = 0
		tecks3.TextColor3 = Color3.new(0, 0, 0)
		tecks3.TextStrokeColor3 = color
		tecks3.Size = UDim2.new(1, 0, 0.5, 0)
		coroutine.resume(coroutine.create(function()
			while true do
				task.wait()
				if chaosmode == true  or insanitymode == true then
					tecks2.TextColor3 = BrickColor.random().Color
					tecks3.TextStrokeColor3 = BrickColor.random().Color
				end
				tecks2.Position = UDim2.new(0, math.random(-5, 5), 0, math.random(-5, 5))
				tecks3.Position = UDim2.new(0, math.random(-5, 5), 0, math.random(-5, 5))
				tecks2.Rotation = math.random(-5, 5)
				tecks3.Rotation = math.random(-5, 5)
			end
		end))
		for i = 1, string.len(text) do
			CFuncs.Sound.Create("rbxassetid://274118116", char, 0.25, 0.115)
			tecks2.Text = string.sub(text, 1, i)
			tecks3.Text = string.sub(text, 1, i)
			task.wait()
		end
		task.wait(1)
		local randomrot = math.random(1, 2)
		if randomrot == 1 then
			for i = 1, 50 do
				task.wait()
				tecks2.Rotation = tecks2.Rotation - 0.75
				tecks2.TextStrokeTransparency = tecks2.TextStrokeTransparency + 0.04
				tecks3.Rotation = tecks2.Rotation + 0.75
				tecks3.TextStrokeTransparency = tecks2.TextStrokeTransparency + 0.04
			end
		elseif randomrot == 2 then
			for i = 1, 50 do
				task.wait()
				tecks2.Rotation = tecks2.Rotation + 0.75
				tecks2.TextStrokeTransparency = tecks2.TextStrokeTransparency + 0.04
				tecks3.Rotation = tecks2.Rotation - 0.75
				tecks3.TextStrokeTransparency = tecks2.TextStrokeTransparency + 0.04
			end
		end
		naeeym2:Destroy()
	end)
	chat()
	end
	

function Sound(parent,id,pitch,volume,looped,effect,autoPlay)
	local Sound = IN("Sound")
	Sound.SoundId = "rbxassetid://".. tostring(id or 0)
	Sound.Pitch = pitch or 1
	Sound.Volume = volume or 1
	Sound.Looped = looped or false
	if(autoPlay)then
		coroutine.wrap(function()
			repeat task.wait() until Sound.IsLoaded
			Sound.Playing = autoPlay or false
		end)()
	end
	if(not looped and effect)then
		Sound.Stopped:connect(function()
			Sound.Volume = 0
			Sound:destroy()
		end)
	elseif(effect)then
		warn("Sound can't be looped and a sound effect!")
	end
	Sound.Parent =parent or Torso
	return Sound
end
	

	function CreateParte(FORMFACTOR, PARENT, MATERIAL, REFLECTANCE, TRANSPARENCY, BRICKCOLOR, NAME, SIZE, ANCHOR)
	local NEWPART = IT("Part")
	NEWPART.formFactor = FORMFACTOR
	NEWPART.Reflectance = REFLECTANCE
	NEWPART.Transparency = TRANSPARENCY
	NEWPART.CanCollide = false
	NEWPART.Locked = true
	NEWPART.Anchored = true
	if ANCHOR == false then
		NEWPART.Anchored = false
	end
	NEWPART.BrickColor = BRICKC(tostring(BRICKCOLOR))
	NEWPART.Name = NAME
	NEWPART.Size = SIZE
	NEWPART.Position = Torso.Position
	NEWPART.Material = MATERIAL
	NEWPART:BreakJoints()
	NEWPART.Parent = PARENT
	return NEWPART
end

	
function CreateSound(ID, PARENT, VOLUME, PITCH)
	local NSound = nil
	coroutine.resume(coroutine.create(function()
		NSound = Instance.new("Sound", PARENT)
		NSound.Volume = VOLUME
		NSound.Pitch = PITCH
		NSound.SoundId = "http://www.roblox.com/asset/?id="..ID
		task.wait()
		NSound:play()
		game:GetService("Debris"):AddItem(NSound, 10)
	end))
	return NSound
end

	function bosschatfunc(text,color,watval)
for i,v in pairs(game:GetService("Players"):GetPlayers()) do
coroutine.resume(coroutine.create(function()
if v.PlayerGui:FindFirstChild("Dialog")~= nil then
v.PlayerGui:FindFirstChild("Dialog"):destroy()
end
local scrg = Instance.new("ScreenGui",v.PlayerGui)
CFuncs["EchoSound"].Create("rbxassetid://525200869", scrg, 0.5, 1,0,10,0.1,0.25,1)
scrg.Name = "Dialog"
--gui below
local wobble = Instance.new("Frame",scrg)
wobble.Name = "Wobble"
wobble.BackgroundTransparency = 0.7
wobble.Size = UDim2.new(1.1,0,1.1,0)
wobble.Position = UDim2.new(-0.08,0,0.943,0)
local wobble2 = Instance.new("Frame",scrg)
wobble2.Name = "wobble2"
wobble2.BackgroundTransparency = 0.7
wobble2.Size = UDim2.new(1.1,0,0.5,0)
wobble2.Position = UDim2.new(-0.08,0,0.9,0)

--text below
local txtlb = Instance.new("TextLabel",scrg)
txtlb.Text = ""
txtlb.Font = "Bodoni"
txtlb.TextColor3 = Color3.new(0,0,0)
txtlb.TextStrokeTransparency = 0
txtlb.BackgroundTransparency = 1
txtlb.BackgroundColor3 = Color3.new(0,0,0)
txtlb.TextStrokeColor3 = color
txtlb.TextScaled = true
txtlb.Size = UDim2.new(1,0,0.25,0)
txtlb.TextXAlignment = "Center"
txtlb.Position = UDim2.new(0,0,0.75 + 1,0)
local txtlb2 = Instance.new("TextLabel",scrg)
txtlb2.Text = "???:"
txtlb2.Font = "Arcade"
txtlb2.TextColor3 = Color3.new(0,0,0)
txtlb2.TextStrokeTransparency = 0
txtlb2.BackgroundTransparency = 1
txtlb2.TextStrokeColor3 = color
txtlb2.TextSize = 40
txtlb2.TextXAlignment = "Center"
txtlb2.TextYAlignment = "Center"
txtlb2.Size = UDim2.new(0,42,0,42)
txtlb2.Position = UDim2.new(0.48,0,0.867,0) -- {0.476, 0},{0.867, 0}

local fvalen = 0.55
local fval = -0.49
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if chaosmode == true then
txtlb.Rotation = math.random(-1,1)
txtlb2.Rotation = math.random(-1,1)
txtlb.Position = txtlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb.TextStrokeColor3 = BrickColor.random().Color
txtlb2.TextStrokeColor3 = BrickColor.random().Color
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if scrg.Parent ~= nil then
	fvalen = fvalen - 0.0001
elseif scrg.Parent == nil then
break
end
end
end))
local flol = 1.75
local flil = 1.6
coroutine.resume(coroutine.create(function()
	for i = 0, 9 do
		task.wait()
		fval = fval + 0.05
		flol = flol - 0.1
		flil = flil - 0.1
		txtlb.Text = ""
		txtlb.Position = UDim2.new(0,0,flol,0)
		txtlb2.Position = UDim2.new(0,0,flil,0)
	end
	txtlb.Text = text
task.wait(watval)
local valinc = 0
for i = 0, 99 do
task.wait()
valinc = valinc + 0.0001
flol = flol + valinc
flil = flil + valinc
txtlb.Rotation = txtlb.Rotation + valinc*20
txtlb2.Rotation = txtlb2.Rotation - valinc*50
txtlb.Position = UDim2.new(0,0,flol,0)
txtlb2.Position = UDim2.new(0,0,flil,0)
txtlb.TextStrokeTransparency = txtlb.TextStrokeTransparency + 0.01
txtlb.TextTransparency = txtlb.TextTransparency + 0.01
txtlb2.TextStrokeTransparency = txtlb2.TextStrokeTransparency + 0.01
txtlb2.TextTransparency = txtlb2.TextTransparency + 0.01
txtlb.BackgroundTransparency = txtlb.BackgroundTransparency + 0.0025
end
scrg:Destroy()
end))
end))
end
end
--WAAHAHWA A WARNING!

function warnedpeople(text,represfont,color,color2)
	if disably ~= true then
CFuncs["Sound"].Create("rbxassetid://1208650519", char, 2,1) -- 1208650519
CFuncs["Sound"].Create("rbxassetid://963718869", char, 0.8,1)
for i,v in pairs(game:GetService("Players"):GetPlayers()) do
coroutine.resume(coroutine.create(function()
if v.PlayerGui:FindFirstChild("Spinny")~= nil then
v.PlayerGui:FindFirstChild("Spinny"):destroy()
end
local scrg = Instance.new("ScreenGui",v.PlayerGui)
scrg.Name = "Spinny"
local frm = Instance.new("Frame",scrg)
frm.BackgroundTransparency = 0.25
frm.BackgroundColor3 = color
frm.BorderSizePixel = 0
frm.Rotation = 45
frm.Size = UDim2.new(3,0,0,100)
frm.Position = UDim2.new(-4,0,0,0)
local frm2 = frm:Clone()
frm2.Parent = scrg
frm2.BackgroundColor3 = color2
frm2.Position = UDim2.new(-4.05,0,0,0)
local imlb = Instance.new("ImageLabel",scrg)
imlb.BackgroundTransparency = 1
imlb.BackgroundColor3 = Color3.new(0,0,0)
imlb.Image = "rbxassetid://2344851144"
imlb.Size = UDim2.new(0,750,0,750)
imlb.ImageColor3 = color2
imlb.ImageTransparency = 0.25
imlb.Position = UDim2.new(-2.5,0,-2.5,0)
local imlb2 = imlb:Clone()
imlb2.Image = "rbxassetid://2076458450"
imlb2.Size = UDim2.new(1,0,1,0)
imlb2.ImageColor3 = color
imlb2.ImageTransparency = 0
imlb2.Position = UDim2.new(0,0,0,0)
local imlb3 = imlb:Clone()
imlb3.Image = "rbxassetid://2312119891"
imlb3.Size = UDim2.new(1,0,1,0)
imlb3.ImageColor3 = color2
imlb3.ImageTransparency = 0
imlb3.Position = UDim2.new(0,0,0,0)
local imlb4 = imlb:Clone()
imlb4.Image = "rbxassetid://2092248396"
imlb4.Size = UDim2.new(3,0,3,0)
imlb3.ImageColor3 = color
imlb4.ImageTransparency = 0
imlb4.Position = UDim2.new(-1,0,-1,0)
local imlb5 = imlb:Clone()
imlb5.Image = "rbxassetid://2344870656"
imlb5.Size = UDim2.new(10,0,10,0)
imlb5.ImageColor3 = color2
imlb5.ImageTransparency = 0
imlb5.Position = UDim2.new(-4.5,0,-4.5,0)
imlb2.Parent = imlb
imlb3.Parent = imlb
imlb4.Parent = imlb
imlb5.Parent = imlb
local txtlb2 = Instance.new("TextLabel",imlb)
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if insanitymode == false then
txtlb2.Text = text
elseif insanitymode == true then
txtlb2.Text = est[math.random(1,17)]
end
end
end))
txtlb2.Font = represfont
txtlb2.TextColor3 = color
txtlb2.TextStrokeTransparency = 0
txtlb2.BackgroundTransparency = 1
txtlb2.TextStrokeColor3 = color2
txtlb2.TextScaled = true
txtlb2.Size = UDim2.new(1,0,1,0)
txtlb2.Position = UDim2.new(0,0,0,0)
local fvalen = 0.55
local fval = -0.49
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rainbowmode == true then
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(r/255,g/255,b/255)
txtlb2.TextColor3 = Color3.new(r/255,g/255,b/255)
imlb.ImageColor3 = Color3.new(r/255,g/255,b/255)
frm.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
frm2.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
txtlb2.TextStrokeColor3 = Color3.new(1,1,1)
txtlb2.TextColor3 = Color3.new(r/255,g/255,b/255)
imlb.ImageColor3 = Color3.new(r/255,g/255,b/255)
imlb3.ImageColor3 = Color3.new(r/255,g/255,b/255)
frm.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
frm2.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if insanitymode == true then
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
txtlb2.TextColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb2.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb3.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb4.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb5.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
frm.BackgroundColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
frm2.BackgroundColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
text = est[math.random(1,17)]
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if glitching == true then
txtlb2.Rotation = math.random(-1,1)
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(0,0,math.random(0.1,1))
txtlb2.TextColor3 = Color3.new(0,0,math.random(0,0.2))
imlb.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb2.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb3.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb4.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb5.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
frm.BackgroundColor3 = Color3.new(0,0,math.random(0.1,1))
frm2.BackgroundColor3 = Color3.new(0,0,math.random(0.1,1))
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if chaosmode == true then
txtlb2.Rotation = math.random(-1,1)
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
imlb.ImageColor3 = BrickColor.random().Color
txtlb2.TextStrokeColor3 = BrickColor.random().Color
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if scrg.Parent ~= nil then
	fvalen = fvalen - 0.0001
elseif scrg.Parent == nil then
break
end
end
end))
local flol = -5
local flil = 1.6
coroutine.resume(coroutine.create(function()
	for i = 0, 49 do
		task.wait()
		flol = flol + 0.125
		flil = flil - 0.1
		frm.Size = frm.Size + UDim2.new(0.1,0,0,0)
		frm.Rotation = frm.Rotation - 0.25
		frm2.Size = frm2.Size + UDim2.new(0.1,0,0,0)
		frm2.Rotation = frm.Rotation + 0.325
		imlb3.Rotation = imlb3.Rotation - 10
		imlb2.Rotation = imlb.Rotation + 7.5
		imlb.Rotation = imlb.Rotation + 5
		if insanitymode == false then
		txtlb2.Rotation = txtlb2.Rotation - 5.125
		elseif insanitymode == true then
		txtlb2.Rotation = txtlb2.Rotation - 5.125 + math.random(-6,6)
		end
		imlb.Position = imlb.Position + UDim2.new(0.05125,0,0.04775,0)
	end
	for i = 0, 99 do
		task.wait()
		fval = fval + 0.05
		flol = flol + 0.005
		frm.Size = frm.Size + UDim2.new(0.005,0,0,0)
		frm.Rotation = frm.Rotation - 0.075
		frm2.Size = frm2.Size + UDim2.new(0.005,0,0,0)
		frm2.Rotation = frm2.Rotation + 0.125
		imlb3.Rotation = imlb3.Rotation - 2
		imlb2.Rotation = imlb.Rotation + 1.5
		imlb.Rotation = imlb.Rotation + 1
		if insanitymode == false then
		txtlb2.Rotation = txtlb2.Rotation - 1.125
		elseif insanitymode == true then
		txtlb2.Rotation = txtlb2.Rotation - 1.125 + math.random(-6,6)
		end
		imlb.Position = imlb.Position + UDim2.new(0.0015,0,0.00075,0)
	end
local valinc = 0
local vinc2 = 1
for i = 0, 99 do
task.wait()
vinc2 = vinc2 + 0.25
valinc = valinc + 0.0001
flol = flol + valinc
flil = flil + valinc
txtlb2.Rotation = txtlb2.Rotation - 1.125*vinc2
imlb3.Rotation = imlb3.Rotation - 2*vinc2
imlb.Rotation = imlb.Rotation + 1*vinc2
imlb.Position = imlb.Position + UDim2.new(0.0015*vinc2,0,0.0005*vinc2,0)
frm.Size = frm.Size + UDim2.new(0.005*vinc2,0,0,0)
frm.Rotation = frm.Rotation + 0.1*vinc2
frm2.Size = frm2.Size + UDim2.new(0.005*vinc2,0,0,0)
frm2.Rotation = frm2.Rotation + 0.225*vinc2
frm2.BackgroundTransparency = frm2.BackgroundTransparency + 0.0075
frm.BackgroundTransparency = frm.BackgroundTransparency + 0.0075
imlb.ImageTransparency = imlb.ImageTransparency + 0.005
imlb2.ImageTransparency = imlb2.ImageTransparency + 0.01
imlb3.ImageTransparency = imlb3.ImageTransparency + 0.01
imlb4.ImageTransparency = imlb4.ImageTransparency + 0.01
imlb5.ImageTransparency = imlb4.ImageTransparency + 0.01
txtlb2.TextStrokeTransparency = txtlb2.TextStrokeTransparency + 0.01
txtlb2.TextTransparency = txtlb2.TextTransparency + 0.01
end
scrg:Destroy()
end))
end))
end
end
end

--ok what?
function IdolsWarn(text,represfont,color,color2)
	if disably ~= true then
CFuncs["Sound"].Create("rbxassetid://534859368", char, 1.25,1)
CFuncs["Sound"].Create("rbxassetid://963718869", char, 0.8,1)
for i,v in pairs(game:GetService("Players"):GetPlayers()) do
coroutine.resume(coroutine.create(function()
if v.PlayerGui:FindFirstChild("Spinny")~= nil then
v.PlayerGui:FindFirstChild("Spinny"):destroy()
end
local scrg = Instance.new("ScreenGui",v.PlayerGui)
scrg.Name = "Spinny"
local frm = Instance.new("Frame",scrg)
frm.BackgroundTransparency = 0.25
frm.BackgroundColor3 = color
frm.BorderSizePixel = 0
frm.Rotation = 45
frm.Size = UDim2.new(3,0,0,100)
frm.Position = UDim2.new(-4,0,0,0)
local frm2 = frm:Clone()
frm2.Parent = scrg
frm2.BackgroundColor3 = color2
frm2.Position = UDim2.new(-4.05,0,0,0)
local imlb = Instance.new("ImageLabel",scrg)
imlb.BackgroundTransparency = 1
imlb.BackgroundColor3 = color
imlb.Image = "rbxassetid://787198541"
imlb.Size = UDim2.new(0,750,0,750)
imlb.ImageColor3 = color2
imlb.ImageTransparency = 0.25
imlb.Position = UDim2.new(-2.5,0,-2.5,0)
local imlb2 = imlb:Clone()
imlb2.Image = "rbxassetid://197468643"
imlb2.Size = UDim2.new(1,0,1,0)
imlb2.ImageTransparency = 0
imlb2.Position = UDim2.new(0,0,0,0)
local imlb3 = imlb:Clone()
imlb3.Image = "rbxassetid://787191999"
imlb3.Size = UDim2.new(1,0,1,0)
imlb3.ImageColor3 = color2
imlb3.ImageTransparency = 0
imlb3.Position = UDim2.new(0,0,0,0)
local imlb4 = imlb:Clone()
imlb4.Image = "rbxassetid://2092248396"
imlb4.Size = UDim2.new(3,0,3,0)
imlb3.ImageColor3 = color
imlb4.ImageTransparency = 0
imlb4.Position = UDim2.new(-1,0,-1,0)
local imlb5 = imlb:Clone()
imlb5.Image = "rbxassetid://2344870656"
imlb5.Size = UDim2.new(10,0,10,0)
imlb5.ImageColor3 = color2
imlb5.ImageTransparency = 0
imlb5.Position = UDim2.new(-4.5,0,-4.5,0)
imlb2.Parent = imlb
imlb3.Parent = imlb
imlb4.Parent = imlb
imlb5.Parent = imlb
local txtlb2 = Instance.new("TextLabel",imlb)
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if glitching == false then
txtlb2.Text = text
elseif glitching == true then
txtlb2.Text = est[math.random(1,17)]
end
end
end))
txtlb2.Font = represfont
txtlb2.TextColor3 = color
txtlb2.TextStrokeTransparency = 0
txtlb2.BackgroundTransparency = 1
txtlb2.TextStrokeColor3 = color2
txtlb2.TextScaled = true
txtlb2.Size = UDim2.new(1,0,1,0)
txtlb2.Position = UDim2.new(0,0,0,0)
local fvalen = 0.55
local fval = -0.49
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rainbowmode == true then
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(r/255,g/255,b/255)
txtlb2.TextColor3 = Color3.new(r/255,g/255,b/255)
imlb.ImageColor3 = Color3.new(r/255,g/255,b/255)
frm.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
frm2.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
txtlb2.TextStrokeColor3 = Color3.new(1,1,1)
txtlb2.TextColor3 = Color3.new(r/255,g/255,b/255)
imlb.ImageColor3 = Color3.new(r/255,g/255,b/255)
imlb3.ImageColor3 = Color3.new(r/255,g/255,b/255)
frm.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
frm2.BackgroundColor3 = Color3.new(r/255,g/255,b/255)
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if glitching == true then
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
txtlb2.TextColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb2.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb3.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb4.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
imlb5.ImageColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
frm.BackgroundColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
frm2.BackgroundColor3 = Color3.new(math.random(0,1),math.random(0,1),math.random(0,1))
text = est[math.random(1,17)]
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if insanitymode == true then
txtlb2.Rotation = math.random(-1,1)
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.TextStrokeColor3 = Color3.new(0,0,math.random(0.1,1))
txtlb2.TextColor3 = Color3.new(0,0,math.random(0,0.2))
imlb.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb2.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb3.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb4.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
imlb5.ImageColor3 = Color3.new(0,0,math.random(0.1,1))
frm.BackgroundColor3 = Color3.new(0,0,math.random(0.1,1))
frm2.BackgroundColor3 = Color3.new(0,0,math.random(0.1,1))
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if chaosmode == true then
txtlb2.Rotation = math.random(-1,1)
imlb.Position = imlb.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
txtlb2.Position = txtlb2.Position + UDim2.new(0,math.random(-1,1)/5,0,math.random(-1,1)/5)
imlb.ImageColor3 = BrickColor.random().Color
txtlb2.TextStrokeColor3 = BrickColor.random().Color
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if scrg.Parent ~= nil then
	fvalen = fvalen - 0.0001
elseif scrg.Parent == nil then
break
end
end
end))
local flol = -5
local flil = 1.6
coroutine.resume(coroutine.create(function()
	for i = 0, 49 do
		task.wait()
		flol = flol + 0.125
		flil = flil - 0.1
		frm.Size = frm.Size + UDim2.new(0.1,0,0,0)
		frm.Rotation = frm.Rotation - 0.25
		frm2.Size = frm2.Size + UDim2.new(0.1,0,0,0)
		frm2.Rotation = frm.Rotation + 0.325
		imlb3.Rotation = imlb3.Rotation - 10
		imlb2.Rotation = imlb.Rotation + 7.5
		imlb.Rotation = imlb.Rotation + 5
		if glitching == false then
		txtlb2.Rotation = txtlb2.Rotation - 5.125
		elseif glitching == true then
		txtlb2.Rotation = txtlb2.Rotation - 5.125 + math.random(-6,6)
		end
		imlb.Position = imlb.Position + UDim2.new(0.05125,0,0.04775,0)
	end
	for i = 0, 99 do
		task.wait()
		fval = fval + 0.05
		flol = flol + 0.005
		frm.Size = frm.Size + UDim2.new(0.005,0,0,0)
		frm.Rotation = frm.Rotation - 0.075
		frm2.Size = frm2.Size + UDim2.new(0.005,0,0,0)
		frm2.Rotation = frm2.Rotation + 0.125
		imlb3.Rotation = imlb3.Rotation - 2
		imlb2.Rotation = imlb.Rotation + 1.5
		imlb.Rotation = imlb.Rotation + 1
		if glitching == false then
		txtlb2.Rotation = txtlb2.Rotation - 1.125
		elseif glitching == true then
		txtlb2.Rotation = txtlb2.Rotation - 1.125 + math.random(-6,6)
		end
		imlb.Position = imlb.Position + UDim2.new(0.0015,0,0.00075,0)
	end
local valinc = 0
local vinc2 = 1
for i = 0, 99 do
task.wait()
vinc2 = vinc2 + 0.25
valinc = valinc + 0.0001
flol = flol + valinc
flil = flil + valinc
txtlb2.Rotation = txtlb2.Rotation - 1.125*vinc2
imlb3.Rotation = imlb3.Rotation - 2*vinc2
imlb.Rotation = imlb.Rotation + 1*vinc2
imlb.Position = imlb.Position + UDim2.new(0.0015*vinc2,0,0.0005*vinc2,0)
frm.Size = frm.Size + UDim2.new(0.005*vinc2,0,0,0)
frm.Rotation = frm.Rotation + 0.1*vinc2
frm2.Size = frm2.Size + UDim2.new(0.005*vinc2,0,0,0)
frm2.Rotation = frm2.Rotation + 0.225*vinc2
frm2.BackgroundTransparency = frm2.BackgroundTransparency + 0.0075
frm.BackgroundTransparency = frm.BackgroundTransparency + 0.0075
imlb.ImageTransparency = imlb.ImageTransparency + 0.005
imlb2.ImageTransparency = imlb2.ImageTransparency + 0.01
imlb3.ImageTransparency = imlb3.ImageTransparency + 0.01
imlb4.ImageTransparency = imlb4.ImageTransparency + 0.01
imlb5.ImageTransparency = imlb4.ImageTransparency + 0.01
txtlb2.TextStrokeTransparency = txtlb2.TextStrokeTransparency + 0.01
txtlb2.TextTransparency = txtlb2.TextTransparency + 0.01
end
scrg:Destroy()
end))
end))
end
end
end

CFuncs = {
	["Part"] = {
		Create = function(Parent, Material, Reflectance, Transparency, BColor, Name, Size)
			local Part = Instance.new("Part")
			Part.Parent = Parent
			Part.Material = Material
			Part.Reflectance = Reflectance
			Part.Transparency = Transparency
			Part.CanCollide = false
			Part.Locked = true
			Part.BrickColor = BrickColor.new(tostring(BColor))
			Part.Name = Name
			Part.Size = Size
			return Part
		end;
	};

	["Mesh"] = {
		Create = function(Mesh, Part, MeshType, MeshId, OffSet, Scale)
			local Msh = Instance.new(Mesh)
			Msh.Parent = Part
			Msh.Offset = OffSet
			Msh.Scale = Scale
			if Mesh == "SpecialMesh" then
				Msh.MeshType = MeshType
				Msh.MeshId = MeshId
			end
			return Msh
		end;
	};

	["Weld"] = {
		Create = function(Parent, Part0, Part1, C0, C1)
			local Weld = Instance.new("Weld")
			Weld.Parent = Parent
			Weld.Part0 = Part0
			Weld.Part1 = Part1
			Weld.C0 = C0
			Weld.C1 = C1
			return Weld
		end;
	};

	["Sound"] = {
		Create = function(id, par, vol, pit)
			coroutine.resume(coroutine.create(function()
				local S = Instance.new("Sound")
				S.Volume = vol
				S.Name = "EffectSoundo"
				S.Pitch = pit or 1
				S.SoundId = id
				S.Parent = par or workspace
				wait()
				S:Play()
				game:GetService("Debris"):AddItem(S, 10)
			end))
		end;
	};

	["TimeSound"] = {
		Create = function(id, par, vol, pit, timepos)
			coroutine.resume(coroutine.create(function()
				local S = Instance.new("Sound")
				S.Volume = vol
				S.Name = "EffectSoundo"
				S.Pitch = pit or 1
				S.SoundId = id
				S.TimePosition = timepos
				S.Parent = par or workspace
				wait()
				S:Play()
				game:GetService("Debris"):AddItem(S, 10)
			end))
		end;
	};

	["EchoSound"] = {
		Create = function(id, par, vol, pit, timepos, delays, echodelay, fedb, dryl)
			coroutine.resume(coroutine.create(function()
				local Sas = Instance.new("Sound")
				Sas.Volume = vol
				Sas.Name = "EffectSoundo"
				Sas.Pitch = pit or 1
				Sas.SoundId = id
				Sas.TimePosition = timepos
				Sas.Parent = par or workspace

				local E = Instance.new("EchoSoundEffect")
				E.Delay = echodelay
				E.Name = "Echo"
				E.Feedback = fedb
				E.DryLevel = dryl
				E.Parent = Sas

				wait()
				Sas:Play()
				game:GetService("Debris"):AddItem(Sas, delays)
			end))
		end;
	};

	["LongSound"] = {
		Create = function(id, par, vol, pit)
			coroutine.resume(coroutine.create(function()
				local S = Instance.new("Sound")
				S.Volume = vol
				S.Pitch = pit or 1
				S.SoundId = id
				S.Parent = par or workspace
				wait()
				S:Play()
				game:GetService("Debris"):AddItem(S, 60)
			end))
		end;
	};

	["ParticleEmitter"] = {
		Create = function(Parent, Color1, Color2, LightEmission, Size, Texture, Transparency, ZOffset, Accel, Drag, LockedToPart, VelocityInheritance, EmissionDirection, Enabled, LifeTime, Rate, Rotation, RotSpeed, Speed, VelocitySpread)
			local fp = Instance.new("ParticleEmitter")
			fp.Parent = Parent
			fp.Color = ColorSequence.new(Color1, Color2)
			fp.LightEmission = LightEmission
			fp.Size = Size
			fp.Texture = Texture
			fp.Transparency = Transparency
			fp.ZOffset = ZOffset
			fp.Acceleration = Accel
			fp.Drag = Drag
			fp.LockedToPart = LockedToPart
			fp.VelocityInheritance = VelocityInheritance
			fp.EmissionDirection = EmissionDirection
			fp.Enabled = Enabled
			fp.Lifetime = LifeTime
			fp.Rate = Rate
			fp.Rotation = Rotation
			fp.RotSpeed = RotSpeed
			fp.Speed = Speed
			fp.VelocitySpread = VelocitySpread
			return fp
		end;
	};
}

function New(Object, Parent, Name, Data)
	local Object = Instance.new(Object)
	for Index, Value in pairs(Data or {}) do
		Object[Index] = Value
	end
	Object.Parent = Parent
	Object.Name = Name
	return Object
end

local halocolor = BrickColor.new("Pastel light blue")
local halocolor2 = BrickColor.new("Really black")
local starcolor = BrickColor.new("Really black")
local lunacolor = BrickColor.new("Navy blue")
local lunacolor2 = BrickColor.new("Bright blue")
local wepcolor = BrickColor.new("Really black")
local maincolor = BrickColor.new("Really black")
local m = Instance.new("Model", char)
local m2 = Instance.new("Model", char)
local m3 = Instance.new("Model", char)
local m4 = Instance.new("Model", char)
local m5 = Instance.new("Model", char)
local mw1 = Instance.new("Model", char)
local mw2 = Instance.new("Model", char)
local mw3 = Instance.new("Model", char)
local mw4 = Instance.new("Model", char)
local extrawingmod1 = Instance.new("Model", char)
local extrawingmod2 = Instance.new("Model", char)
local colorizermod = Instance.new("Model",char)
local colorizermod2 = Instance.new("Model",char)

local est = {"cReav!n..?","aKh0a123O...?","vR08...?","kImkIm143lOp..?","dArk lEaDEr & rEd lEaAdEr...?","sUicIdE","dIEeEE","kArMa","iNsaNiTy","l0vE...?"}

gui = function(GuiType, parent, text, backtrans, backcol, pos, size)
  local gui = it(GuiType)
  gui.Parent = parent
  gui.Text = text
  gui.BackgroundTransparency = backtrans
  gui.BackgroundColor3 = backcol
  gui.SizeConstraint = "RelativeXY"
  gui.TextXAlignment = "Center"
  gui.TextYAlignment = "Center"
  gui.Position = pos
  gui.Size = size
  gui.Font = "SourceSans"
  gui.FontSize = "Size14"
  gui.TextWrapped = false
  gui.TextStrokeTransparency = 0
  gui.TextColor = BrickColor.new("White")
  return gui
end
--------------------------- GUI STUFF
local basgui = it("GuiMain")
basgui.Parent = plr.PlayerGui
local basgui = Instance.new("GuiMain")
basgui.Parent = plr.PlayerGui
basgui.Name = "VISgui"
local wobble = Instance.new("Frame",basgui)
wobble.Name = "Wobble"
wobble.BackgroundTransparency = 0.5
wobble.Size = UDim2.new(1.1,0,1.1,0)
wobble.Position = UDim2.new(-0.08,0,0.943,0)
local wobble2 = Instance.new("Frame",basgui)
wobble2.Name = "wobble2"
wobble2.BackgroundTransparency = 0.5
wobble2.Size = UDim2.new(1.1,0,0.09,0)
wobble2.Position = UDim2.new(-0.08,0,0.878,0)
local TextFrame = Instance.new("TextLabel",basgui)
TextFrame.Name = "Farmer"
TextFrame.Font = "Fantasy"
TextFrame.Text = plr.Name.." "
TextFrame.TextSize = 60
TextFrame.BackgroundTransparency = 1
TextFrame.Size = UDim2.new(0,42,0,42)
TextFrame.Position = UDim2.new(0.48,0,0.867,0) -- {0.476, 0},{0.867, 0}
local ModeFrame = Instance.new("TextLabel",basgui)
ModeFrame.Name = "Farmer5000"
ModeFrame.Font = "Fantasy"
ModeFrame.Text = "Unfair Glitcher"
ModeFrame.TextSize = 30
ModeFrame.BackgroundTransparency = 1
ModeFrame.TextStrokeTransparency = 0
ModeFrame.Size = UDim2.new(0,42,0,42)
ModeFrame.Rotation = 15
ModeFrame.Position = UDim2.new(0.069,0,0.86,0) -- {0.476, 0},{0.901, 0}
local ned = Instance.new("TextLabel",basgui)
ned.ZIndex = 2
ned.Font = "Bodoni"
ned.BackgroundTransparency = 1
ned.BorderSizePixel = 0.65
ned.Size = UDim2.new(0.3,0,0.2,0)
ned.Position = UDim2.new(0.5,0.05,0.5,0)
ned.TextColor3 = BrickColor.new("Really red").Color
ned.TextStrokeColor3 = BrickColor.new("Really black").Color
ned.TextScaled = true
ned.TextStrokeTransparency = 0
ned.Text = "MAYHEM"
ned.TextSize = 24
ned.Rotation = 1
ned.TextXAlignment = "Right"
ned.TextYAlignment = "Center"




function CreateParta(parent, transparency, reflectance, material, brickcolor)
	local p = Instance.new("Part")
	p.TopSurface = 0
	p.BottomSurface = 0
	p.Parent = parent
	p.Size = Vector3.new(0.1, 0.1, 0.1)
	p.Transparency = transparency
	p.Reflectance = reflectance
	p.CanCollide = false
	p.Locked = true
	p.BrickColor = brickcolor
	p.Material = material
	return p
end
function CreateMeshe(Mesh, Part, MeshType, MeshId, OffSet, Scale)
	local Msh = Create(Mesh)({
		Parent = Part,
		Offset = OffSet,
		Scale = Scale
	})
	if Mesh == "SpecialMesh" then
		Msh.MeshType = MeshType
		Msh.MeshId = MeshId
	end
	return Msh
end
function CreateMesh(parent, meshtype, x1, y1, z1)
	local mesh = Instance.new("SpecialMesh", parent)
	mesh.MeshType = meshtype
	mesh.Scale = Vector3.new(x1 * 10, y1 * 10, z1 * 10)
	return mesh
end
function CreateSpecialMesh(parent, meshid, x1, y1, z1)
	local mesh = Instance.new("SpecialMesh", parent)
	mesh.MeshType = "FileMesh"
	mesh.MeshId = meshid
	mesh.Scale = Vector3.new(x1, y1, z1)
	return mesh
end
function CreateSpecialGlowMesh(parent, meshid, x1, y1, z1)
	local mesh = Instance.new("SpecialMesh", parent)
	mesh.MeshType = "FileMesh"
	mesh.MeshId = meshid
	mesh.TextureId = "http://www.roblox.com/asset/?id=269748808"
	mesh.Scale = Vector3.new(x1, y1, z1)
	mesh.VertexColor = Vector3.new(parent.BrickColor.r, parent.BrickColor.g, parent.BrickColor.b)
	return mesh
end
function CreateWeld(parent, part0, part1, C1X, C1Y, C1Z, C1Xa, C1Ya, C1Za, C0X, C0Y, C0Z, C0Xa, C0Ya, C0Za)
	local weld = Instance.new("Weld")
	weld.Parent = parent
	weld.Part0 = part0
	weld.Part1 = part1
	weld.C1 = CFrame.new(C1X, C1Y, C1Z) * CFrame.Angles(C1Xa, C1Ya, C1Za)
	weld.C0 = CFrame.new(C0X, C0Y, C0Z) * CFrame.Angles(C0Xa, C0Ya, C0Za)
	return weld
end
-------------- ground effect
local cen = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
CreateWeld(cen,root,cen,0,3,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local effar = Instance.new("ParticleEmitter",cen)
effar.Texture = "rbxassetid://2344870656"
effar.LightEmission = 1
effar.Color = ColorSequence.new(Color3.new(1,0,0))
effar.Rate = 50
effar.Enabled = false
effar.EmissionDirection = "Front"
effar.Lifetime = NumberRange.new(1)
effar.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,15,0),NumberSequenceKeypoint.new(0.1,5,0),NumberSequenceKeypoint.new(0.8,15,0),NumberSequenceKeypoint.new(1,40,0)})
effar.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.8,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
effar.Speed = NumberRange.new(80,90)
effar.Acceleration = Vector3.new(0,10,0)
effar.Drag = 5
effar.Rotation = NumberRange.new(-500,500)
effar.SpreadAngle = Vector2.new(0,900)
effar.RotSpeed = NumberRange.new(-500,500)
--------------
local secondchar = Instance.new("Model",char)
local GhostCol = BrickColor.new("Really red")
local sectors = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(sectors,"Brick",2*8,2*8,1*8)
local torsweld = CreateWeld(sectors,root,sectors,1,-1,-2,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local seclarm = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(seclarm,"Brick",1*8,2*8,1*8)
local larmsweld = CreateWeld(seclarm,sectors,seclarm,1.5,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local secrarm = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(secrarm,"Brick",1*8,2*8,1*8)
local rarmsweld = CreateWeld(secrarm,sectors,secrarm,-1.5,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local seclleg = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(seclleg,"Brick",1*8,2*8,1*8)
local llegsweld = CreateWeld(seclleg,sectors,seclleg,0.5,2,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local secrleg = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(secrleg,"Brick",1*8,2*8,1*8)
local rlegsweld = CreateWeld(secrleg,sectors,secrleg,-0.5,2,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local seched = CreateParta(secondchar,1,0,"Neon",GhostCol)
CreateMesh(seched,"Brick",1*8,1*8,1*8)
local hedsweld = CreateWeld(seched,sectors,seched,0,-1.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--------------
secrleg.Transparency = 01
seclleg.Transparency = 01
secrarm.Transparency = 01
seclarm.Transparency = 01
seched.Transparency = 01
sectors.Transparency = 01
--------------
local sorb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
CreateWeld(sorb,rarm,sorb,0,1,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local sorb2 = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
CreateWeld(sorb2,larm,sorb2,0,1,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local sorb3 = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
CreateWeld(sorb3,root,sorb3,0,0,0,math.rad(-90),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local CALAMITYorb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
local calor = CreateWeld(CALAMITYorb,tors,CALAMITYorb,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local CHAOSorb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
local chaor = CreateWeld(CHAOSorb,tors,CHAOSorb,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local Murderorb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
local mayor = CreateWeld(Murderorb,tors,Murderorb,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local EQUINOXorb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.random())
local equor = CreateWeld(EQUINOXorb,tors,EQUINOXorb,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--------------


--rings&stuff
local handlex = CreateParta(mw2, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Brick", 0, 0, 0)
local handlexweld = CreateWeld(handlex, tors, handlex, 0, -1.5, -1.05, math.rad(0), math.rad(0), math.rad(0), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))
local valuaring = 10
for i = 0, 49 do
	valuaring = valuaring + 10
	rn = CreateParta(mw2, 0, 0, "Neon", halocolor)
	CreateMesh(rn, "Brick", 0.25, 0.1, 0.1)
	CreateWeld(rn, handlex, rn, 0, 1, 0, math.rad(0), math.rad(0), math.rad(valuaring), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))
end
local handle = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Brick", 0.5, 0.5, 0.5)
local handleweld = CreateWeld(handle, tors, handle, 0, -1.5, -1.05, math.rad(0), math.rad(0), math.rad(0), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))
-----LEFT WING-----
--lwing1

local lwing1 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local lwing1weld = CreateWeld(lwing1,handle,lwing1,3,0,0,math.rad(5),math.rad(0),math.rad(12.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))

wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing1,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing1,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing1,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--lwing2


local lwing2 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local lwing2weld = CreateWeld(lwing2,handle,lwing2,4,1,0,math.rad(10),math.rad(0),math.rad(25),0,0,0,math.rad(0),math.rad(0),math.rad(0))

wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing2,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing2,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing2,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--lwing3


local lwing3 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local lwing3weld = CreateWeld(lwing3,handle,lwing3,4.75,2,0,math.rad(15),math.rad(0),math.rad(37.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))

wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing3,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing3,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing3,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--lwing4

local lwing4 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local lwing4weld = CreateWeld(lwing4, handle, lwing4, 5.75, 3, 0, math.rad(20), math.rad(0), math.rad(50), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing4,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing4,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing4,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--lwing5
local lwing5 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local lwing5weld = CreateWeld(lwing5, handle, lwing5, 6.75, 4, 0, math.rad(25), math.rad(0), math.rad(62.5), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing5,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing5,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing5,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--lwing6
local lwing6 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local lwing6weld = CreateWeld(lwing6, handle, lwing6, 7.75, 5, 0, math.rad(30), math.rad(0), math.rad(75), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,lwing6,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,lwing6,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod1,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,lwing6,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

-----RIGHT WING-----
--rwing1
local rwing1 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local rwing1weld = CreateWeld(rwing1,handle,rwing1,-3,0,0,math.rad(5),math.rad(0),math.rad(-12.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))

wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing1,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing1,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing1,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))


--rwing2

local rwing2 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local rwing2weld = CreateWeld(rwing2,handle,rwing2,-4,1,0,math.rad(10),math.rad(0),math.rad(-25),0,0,0,math.rad(0),math.rad(0),math.rad(0))

wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing2,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing2,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing2,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--rwing3

local rwing3 = CreateParta(m,1,1,"Neon",maincolor)
CreateMesh(handle,"Brick",0.5,0.5,0.5)
local rwing3weld = CreateWeld(rwing3,handle,rwing3,-4.75,2,0,math.rad(15),math.rad(0),math.rad(-37.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))


wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing3,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing3,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(mw2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing3,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--rwing4
local rwing4 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local rwing4weld = CreateWeld(rwing4, handle, rwing4, -5.75, 3, 0, math.rad(20), math.rad(0), math.rad(-50), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing4,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing4,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing4,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--rwing5
local rwing5 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local rwing5weld = CreateWeld(rwing5, handle, rwing5, -6.75, 4, 0, math.rad(25), math.rad(0), math.rad(-62.5), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing5,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing5,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing5,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--rwing6
local rwing6 = CreateParta(m, 1, 1, "Neon", maincolor)
CreateMesh(handle, "Wedge", 0.5, 0.5, 0.5)
local rwing6weld = CreateWeld(rwing6, handle, rwing6, -7.75, 3, 0, math.rad(30), math.rad(0), math.rad(-75), 0, 0, 0, math.rad(0), math.rad(0), math.rad(0))

wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,0.25,0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,0.25,0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,-0.75,0.25,math.rad(180),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,-0.75,0.25,math.rad(180),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
--bottom
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,0.75,-0.25,math.rad(0),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,0.5)
CreateWeld(wed,rwing6,wed,0,0.75,-0.25,math.rad(0),math.rad(-90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,0.5,1.5)
CreateWeld(wed,rwing6,wed,0,-0.25,1.75,math.rad(0),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))
wed = CreateParta(extrawingmod2,0,0,"Neon",halocolor)
CreateMesh(wed,"Wedge",0.05,1.5,0.5)
CreateWeld(wed,rwing6,wed,0,-1.75,0.25,math.rad(90),math.rad(90),math.rad(90),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--glove



gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,larm,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,larm,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))



gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,larm,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,larm,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gane = CreateParta(m3,0,0,"SmoothPlastic",lunacolor2)
CreateMesh(gane,"Brick",1.0625,0.2,1.0625)
CreateWeld(gane,larm,gane,0,0.6,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

star = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateSpecialMesh(star,"http://www.roblox.com/asset/?id=45428961",2.5,2.5,2.5)
CreateWeld(star,larm,star,0,0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
starl = CreateParta(m3,0,0,"SmoothPlastic",starcolor)
CreateSpecialMesh(starl,"http://www.roblox.com/asset/?id=45428961",1.95,2.55,1.95)
CreateWeld(starl,larm,starl,0,0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--- glove2


gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,rarm,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,rarm,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))



gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,rarm,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,rarm,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gane = CreateParta(m3,0,0,"SmoothPlastic",lunacolor2)
CreateMesh(gane,"Brick",1.0625,0.2,1.0625)
CreateWeld(gane,rarm,gane,0,0.6,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

star = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateSpecialMesh(star,"http://www.roblox.com/asset/?id=45428961",2.5,2.5,2.5)
CreateWeld(star,rarm,star,0,-0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
starl = CreateParta(m3,0,0,"SmoothPlastic",starcolor)
CreateSpecialMesh(starl,"http://www.roblox.com/asset/?id=45428961",1.95,2.55,1.95)
CreateWeld(starl,rarm,starl,0,-0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--- glove3


gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,rleg,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,rleg,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))



gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,rleg,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,rleg,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gane = CreateParta(m3,0,0,"SmoothPlastic",lunacolor2)
CreateMesh(gane,"Brick",1.0625,0.2,1.0625)
CreateWeld(gane,rleg,gane,0,0.6,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

star = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateSpecialMesh(star,"http://www.roblox.com/asset/?id=45428961",2.5,2.5,2.5)
CreateWeld(star,rleg,star,0,-0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
starl = CreateParta(m3,0,0,"SmoothPlastic",starcolor)
CreateSpecialMesh(starl,"http://www.roblox.com/asset/?id=45428961",1.95,2.55,1.95)
CreateWeld(starl,rleg,starl,0,-0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

--glove4



gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,lleg,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateMesh(gan,"Brick",1.075,0.1,1.075)
CreateWeld(gan,lleg,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))



gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,lleg,gan,0,0.5,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gan = CreateParta(m2,0,0,"Neon",halocolor2)
CreateMesh(gan,"Brick",1.095,0.035,1.095)
CreateWeld(gan,lleg,gan,0,0.75,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

gane = CreateParta(m3,0,0,"SmoothPlastic",lunacolor2)
CreateMesh(gane,"Brick",1.0625,0.2,1.0625)
CreateWeld(gane,lleg,gane,0,0.6,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

star = CreateParta(m,0,0,"SmoothPlastic",wepcolor)
CreateSpecialMesh(star,"http://www.roblox.com/asset/?id=45428961",2.5,2.5,2.5)
CreateWeld(star,lleg,star,0,0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
starl = CreateParta(m3,0,0,"SmoothPlastic",starcolor)
CreateSpecialMesh(starl,"http://www.roblox.com/asset/?id=45428961",1.95,2.55,1.95)
CreateWeld(starl,lleg,starl,0,0.475,0.6,math.rad(90),math.rad(90),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

---COLORING---
for i, v in pairs(m:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Really black")
		v.Material = "Glass"
	end
end
for i, v in pairs(m2:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Crimson")
		v.Material = "Granite"
	end
end
for i, v in pairs(m3:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Really red")
		v.Material = "Neon"
	end
end
for i, v in pairs(mw2:GetChildren()) do
	if v:IsA("Part") then
		v.Transparency = 0
		v.BrickColor = BrickColor.new("Really red")
		v.Material = "Neon"
	end
end
for i, v in pairs(mw1:GetChildren()) do
	if v:IsA("Part") then
		v.Transparency = 1
		v.BrickColor = BrickColor.new("Really red")
		v.Material = "Neon"
	end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
	if v:IsA("Part") then
		v.Transparency = 1
		v.BrickColor = BrickColor.new("White")
		v.Material = "Neon"
	end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
	if v:IsA("Part") then
		v.Transparency = 1
		v.BrickColor = BrickColor.new("White")
		v.Material = "Neon"
	end
end
----lol no blood

--shadow head
FHead = New("Part",char,"FHead",{CanCollide = false,BrickColor = BrickColor.new("Really black"),Size = Vector3.new(1.20000005, 0.600000024, 1),CFrame = CFrame.new(68.5999985, 0.700013041, 9.89999962, 1, 0, 0, 0, 1, 0, 0, 0, 1),Color = Color3.new(0.0666667, 0.0666667, 0.0666667),})
Mesh = New("SpecialMesh",FHead,"Mesh",{Scale = Vector3.new(1.25999999, 1.7, 1.25999999),})
Weld = New("Weld",FHead,"mot",{Part0 = FHead,Part1 = char.Head,C1 = CFrame.new(0, 0.200000048, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),})
FHead.CanCollide = false
--ruin color for modes
local MAINRUINCOLOR = BrickColor.new("Really red")
local MAINRUINCOLOR2 = BrickColor.new("Really black")
----sword---


--armor and stuff idk--
local rarmor = CreateParta(m,1,0,"SmoothPlastic",BrickColor.new("Really black"))
local weaponweld = CreateWeld(rarmor,tors,rarmor,-3,0,-0.5,math.rad(0),math.rad(0),math.rad(-40),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local A0 = Instance.new("Attachment",rarmor)
A0.Position = Vector3.new(-2.5,0.25,0)
local A1 = Instance.new("Attachment",rarmor)
A1.Position = Vector3.new(-7.5,0.4,0)
tl1 = Instance.new('Trail',rarmor)
tl1.Attachment0 = A0
tl1.Attachment1 = A1
tl1.Texture = "http://www.roblox.com/asset/?id=0"
tl1.LightEmission = 1
tl1.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
tl1.Color = ColorSequence.new(BrickColor.new("Really black").Color)
tl1.Lifetime = 0.6
tl1.Enabled = false

---equipping the sword&stuff idk

---equipping the advanced lol
function equip1()
	attack = true
	advanced = true
		chatfunc("Advanced Attack :ON..", BrickColor.random().Color)
	hum.WalkSpeed = 0
tl1.Enabled = true
for i = 0, 9 do
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--slash(math.random(10,50)/10,3,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-360,360)),math.rad(math.random(-10,10))),vt(0.05,0.01,0.05),math.random(25,50)/250,BrickColor.new("White"))
end
CFuncs["Sound"].Create("rbxassetid://1368637781", Torso, 2.5, 1.25)
CFuncs["Sound"].Create("rbxassetid://200633077", Torso, 1, 1)
CFuncs["Sound"].Create("rbxassetid://169380495", Torso, 0.5, 1.1)
	for i = 0, 2, 0.1 do
		task.wait()
hum.CameraOffset = vt(math.random(-5,5)/50,math.random(-5,5)/50,math.random(-5,5)/50)
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--waveEff(5,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),0.05,0.015,MAINRUINCOLOR)
--waveEff(5,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(10,0.25,10),0.05,0.015,MAINRUINCOLOR)
	RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(10),math.rad(0)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-10)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(-20)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-20),math.rad(-30),math.rad(130)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(-13),math.rad(10),math.rad(-10)),.3)
end
hum.CameraOffset = vt(0,0,0)
for i = 0, 1, 0.1 do
		task.wait()
		--waveEff(5,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),0.35,0.25,MAINRUINCOLOR)
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--waveEff(5,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(10,0.25,10),0.85,0.05,MAINRUINCOLOR)
--sphere2(5,"Add",Torso.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,BrickColor.new("Cyan"),BrickColor.new("Cyan").Color)
	RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-40),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(5)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.1,0.1,0)*angles(math.rad(0),math.rad(0),math.rad(40)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(-40)),.3)
RW.C0=clerp(RW.C0,cf(1.25,0.5,-0.65)*angles(math.rad(100),math.rad(0),math.rad(-23)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(110),math.rad(0),math.rad(-85)),.3)
end
local hitb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.Random())
hitb.Anchored = true
hitb.CFrame = root.CFrame + root.CFrame.lookVector*4
MagniDamage(hitb, 4, 40,73, 0, "Normal",153092213)
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--slash(5,5,true,"Round","Add","Out",hitb.CFrame*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(0.05,0.01,0.05),0.01,BrickColor.new("White"))
CFuncs["Sound"].Create("rbxassetid://200633196", Torso, 1, 1.05)
CFuncs["Sound"].Create("rbxassetid://200633108", Torso, 1.5, 1.025)
CFuncs["Sound"].Create("rbxassetid://234365549", Torso, 1, 1)
for i = 0, 2, 0.1 do
		task.wait()
		--waveEff(3,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),0.55,0.015,MAINRUINCOLOR)
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--waveEff(3,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(10,0.25,10),0.55,0.015,MAINRUINCOLOR)
--sphere2(5,"Add",Torso.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,BrickColor.new("Cyan"),BrickColor.new("Cyan").Color)
	RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-20)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(50),math.rad(0)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(-0.1,-0.25,0)*angles(math.rad(10),math.rad(0),math.rad(-50)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(50)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(80),math.rad(0),math.rad(70)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(100),math.rad(0),math.rad(-50)),.3)
end
hitb:Destroy()
hum.WalkSpeed = 16
OWS = hum.WalkSpeed
	attack = false
end

function unequip1()
	attack = true
	advanced = false
		hum.WalkSpeed = 0
				chatfunc("Advanced Attack:OFF..", MAINRUINCOLOR.Color)
		for i = 0, 2, 0.1 do
		task.wait()
hum.CameraOffset = vt(math.random(-5,5)/50,math.random(-5,5)/50,math.random(-5,5)/50)
--waveEff(3,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(2,0.25,2),0.05,0.035,MAINRUINCOLOR)
sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
--waveEff(3,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),0.05,0.015,MAINRUINCOLOR)
	RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(10),math.rad(0)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-10)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(-20)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-20),math.rad(-30),math.rad(130)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(-13),math.rad(10),math.rad(-10)),.3)
end
hum.WalkSpeed = 16
OWS = hum.WalkSpeed
tl1.Enabled = false
CFuncs["Sound"].Create("rbxassetid://200633029", rarmor, 1, 1)
	attack = false
end
--synthezizer! :D

local handlex2 = CreateParta(m4,1,1,"Neon",maincolor)
CreateMesh(handlex2,"Brick",0,0,0)
local handlex2weld = CreateWeld(handlex2,tors,handlex2,0,-2,-2.05,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))


local rotzo = CreateParta(m4,1,1,"Neon",maincolor)
CreateMesh(rotzo,"Brick",0,0,0)
local rotingweld = CreateWeld(rotzo,handlex2,rotzo,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))
local rotzo2 = CreateParta(m4,1,1,"Neon",maincolor)
CreateMesh(rotzo2,"Brick",0,0,0)
local rotingweld2 = CreateWeld(rotzo2,handlex2,rotzo2,0,0,0,math.rad(0),math.rad(0),math.rad(0),0,0,0,math.rad(0),math.rad(0),math.rad(0))

local roterval = 0
for i = 0, 7 do
rn = CreateParta(colorizermod,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.15)
CreateWeld(rn,rotzo,rn,0,-4.25,0.1,math.rad(0),math.rad(90),math.rad(roterval),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.15)
CreateWeld(rn,rotzo,rn,0,-4.25,0.1,math.rad(0),math.rad(-90),math.rad(roterval),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.15)
CreateWeld(rn,rotzo,rn,0,3.25,0.1,math.rad(0),math.rad(90),math.rad(roterval),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.15)
CreateWeld(rn,rotzo,rn,0,3.25,0.1,math.rad(0),math.rad(-90),math.rad(roterval),0,0,0,math.rad(0),math.rad(0),math.rad(0))

rn = CreateParta(colorizermod2,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.25)
CreateWeld(rn,rotzo2,rn,0,1.5,0.2,math.rad(0),math.rad(90),math.rad(roterval + 22.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod2,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.15,1,0.25)
CreateWeld(rn,rotzo2,rn,0,1.5,0.2,math.rad(0),math.rad(-90),math.rad(roterval + 22.5),0,0,0,math.rad(0),math.rad(0),math.rad(0))
roterval = roterval + 45
end
local refec = Instance.new("ParticleEmitter",handlex2)
refec.Texture = "rbxassetid://284205403"
refec.LightEmission = 0.95
refec.Color = ColorSequence.new(MAINRUINCOLOR.Color,MAINRUINCOLOR.Color)
refec.Rate = 50
refec.Lifetime = NumberRange.new(0.5)
refec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0.5,0),NumberSequenceKeypoint.new(0.5,0.75,0),NumberSequenceKeypoint.new(1,0.1,0)})
refec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
refec.Speed = NumberRange.new(0,2)
refec.Drag = 5
refec.LockedToPart = true
refec.Rotation = NumberRange.new(-500,500)
refec.VelocitySpread = 9000
refec.RotSpeed = NumberRange.new(-500,500)
local refec2 = refec:Clone()
refec2.LightEmission = 0.75
refec2.Texture = "rbxassetid://2108979939"--2108979939 254287058 2109052855
refec2.Parent = handlex2
refec2.Rate = 15
refec2.Lifetime = NumberRange.new(0.75)
refec2.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,2.15,0),NumberSequenceKeypoint.new(0.7,2.25,0),NumberSequenceKeypoint.new(0.8,2.15,0),NumberSequenceKeypoint.new(1,1.75,0)})
refec2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.65,0),NumberSequenceKeypoint.new(1,1,0)})
refec2.Speed = NumberRange.new(0)
local refec3 = refec:Clone()
refec3.LightEmission = 0.75
refec3.Texture = "rbxassetid://2092248396"
refec3.Parent = handlex2
refec3.Rate = 25
refec3.Lifetime = NumberRange.new(1)
refec3.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,2,0),NumberSequenceKeypoint.new(0.8,4,0),NumberSequenceKeypoint.new(1,15,0)})
refec3.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.65,0),NumberSequenceKeypoint.new(1,1,0)})
refec3.Speed = NumberRange.new(0)
refec3.RotSpeed = NumberRange.new(-50,50)
local valuaring = 10
for i = 0, 35 do
	valuaring = valuaring + 10
rn = CreateParta(colorizermod2,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Brick",0.25,0.1,0.1)
CreateWeld(rn,handlex2,rn,0,2,0,math.rad(0),math.rad(0),math.rad(valuaring),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod2,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Brick",0.725,0.045,0.045)
CreateWeld(rn,handlex2,rn,0,3.8,0,math.rad(0),math.rad(0),math.rad(valuaring),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(m4,0,0,"Granite",maincolor)
CreateMesh(rn,"Brick",0.35,0.05,0.2)
CreateWeld(rn,handlex2,rn,0,1.975,0,math.rad(0),math.rad(0),math.rad(valuaring + 5),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(m4,0,0,"Granite",maincolor)
CreateMesh(rn,"Torso",0.385,0.15,0.2)
CreateWeld(rn,handlex2,rn,0,2.1,0,math.rad(0),math.rad(0),math.rad(valuaring),0,0,0,math.rad(0),math.rad(0),math.rad(0))
rn = CreateParta(colorizermod2,0,0,"Neon",BrickColor.new("Alder"))
CreateMesh(rn,"Wedge",0.5,0.5,0.15)
CreateWeld(rn,handlex2,rn,0,-2.25,0,math.rad(0),math.rad(0),math.rad(valuaring + 5),0,0,0,math.rad(0),math.rad(0),math.rad(0))
end
------Universal?

--lol guess not lol
--reason: it failed horribly..
--oof

--other functions lol--
function RemoveOutlines(part)
	part.TopSurface, part.BottomSurface, part.LeftSurface, part.RightSurface, part.FrontSurface, part.BackSurface = 10, 10, 10, 10, 10, 10
end

function createBGCircle(size,parent,color)
local bgui = Instance.new("BillboardGui",parent)
bgui.Size = UDim2.new(size, 0, size, 0)
local imgc = Instance.new("ImageLabel",bgui)
imgc.BackgroundTransparency = 1
imgc.ImageTransparency = 0
imgc.Size = UDim2.new(1,0,1,0)
imgc.Image = "rbxassetid://997291547" --997291547,521073910
imgc.ImageColor3 = color
return bgui,imgc
end

function symbolizeBlink(guipar,size,img,color,bonussize,vol,pit,soundid,spar,rotationenabled,rotsp,delay)
local bgui,imgc = createBGCircle(size,guipar,color)
bgui.AlwaysOnTop = true
imgc.Image = "rbxassetid://" ..img
local rrot = math.random(1,2)
CFuncs["Sound"].Create("rbxassetid://" ..soundid, spar, vol,pit)
coroutine.resume(coroutine.create(function()
for i = 0, 24*delay do
task.wait()
if rotationenabled == true then
if rrot == 1 then
imgc.Rotation = imgc.Rotation + rotsp
elseif rrot == 2 then
imgc.Rotation = imgc.Rotation - rotsp
end
end
bgui.Size = bgui.Size + UDim2.new(1*bonussize/delay,0,1*bonussize/delay,0)
imgc.ImageTransparency = imgc.ImageTransparency + 0.04/delay
end
bgui:Destroy()
end))
end
function RecolorThing(one,onetran,two,three,four,five,exonetran,exone,extwotran,extwo,secondaryenabled,sectrailenabled)
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = onetran
v.BrickColor = one
v.Material = "Neon"
end
end
CFuncs["EchoSound"].Create("rbxassetid://847061203", root, 1, 1,0,10,0.25,0.25,1)
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
if secondaryenabled == false then
v.Transparency = 1
elseif secondaryenabled == true then
v.Transparency = 0
end
v.BrickColor = two
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = three
v.Material = "Ice"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = four
v.Material = "Ice"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = five
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = exonetran
v.BrickColor = exone
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = extwotran
v.BrickColor = extwo
v.Material = "Neon"
end
end
end




function tbeam(col1,col2)
	local lookavec = 0 
	local mult = 1
local elocacenter = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
elocacenter.Anchored = true
elocacenter.CFrame = root.CFrame
local eloca1 = CreateParta(elocacenter,1,1,"SmoothPlastic",BrickColor.random())
eloca1.Anchored = true
eloca1.CFrame = elocacenter.CFrame
local at1 = Instance.new("Attachment",eloca1)
at1.Position = vt(0,10,0)
local at2 = Instance.new("Attachment",eloca1)
at2.Position = vt(0,-10,0)
local trl = Instance.new('Trail',eloca1)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(col1.Color)
trl.Lifetime = 4
local eff = Instance.new("ParticleEmitter",eloca1)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(col1.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,1)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
local eloca2 = eloca1:Clone()
eloca2.Parent = elocacenter
local eloca3 = CreateParta(elocacenter,1,1,"SmoothPlastic",BrickColor.random())
eloca3.Anchored = true
eloca3.CFrame = elocacenter.CFrame
local at1 = Instance.new("Attachment",eloca3)
at1.Position = vt(0,10,0)
local at2 = Instance.new("Attachment",eloca3)
at2.Position = vt(0,-10,0)
local trl = Instance.new('Trail',eloca3)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(col2.Color)
trl.Lifetime = 4
local eff = Instance.new("ParticleEmitter",eloca3)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(col2.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,1)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
local eloca4 = eloca3:Clone()
eloca4.Parent = elocacenter
elocacenter.CFrame = root.CFrame
sphere2(6,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(1,10000,1),0.9,7,0.9,col2)
sphere2(5,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(1,10000,1),0.8,7,0.8,col1)
sphere2(4,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(1,10000,1),0.6,7,0.6,col2)
sphere2(3,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(1,10000,1),0.5,7,0.5,col1)
local effx = Instance.new("ParticleEmitter",root)
effx.Texture = "rbxassetid://144580273" -- 144580273 74564879
effx.LightEmission = 1
effx.Color = ColorSequence.new(col1.Color)
effx.Rate = 500000
effx.Lifetime = NumberRange.new(0.25,0.75)
effx.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,200,0)})
effx.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.5,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effx.Speed = NumberRange.new(0,10)
effx.Drag = 5
effx.Rotation = NumberRange.new(-500,500)
effx.VelocitySpread = 9000
effx.RotSpeed = NumberRange.new(-50,50)
local effx2 = Instance.new("ParticleEmitter",root)
effx2.Texture = "rbxassetid://2273224484"
effx2.LightEmission = 1
effx2.Color = ColorSequence.new(col1.Color)
effx2.Rate = 500000
effx2.Lifetime = NumberRange.new(1,2)
effx2.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,200,0),NumberSequenceKeypoint.new(0.1,50,0),NumberSequenceKeypoint.new(0.8,25,0),NumberSequenceKeypoint.new(1,0,0)})
effx2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effx2.Speed = NumberRange.new(50,1200)
effx2.Drag = 5
effx2.Rotation = NumberRange.new(-500,500)
effx2.VelocitySpread = 9000
effx2.RotSpeed = NumberRange.new(-50,50)
local effx3 = effx2:Clone()
effx3.Parent = root
effx3.Color = ColorSequence.new(col2.Color)
symbolizeBlink(root,0,144580273,col1.Color,20,0,0,0,root,true,-5,2)
symbolizeBlink(root,0,144580273,col2.Color,25,0,0,0,root,true,-5,1)
for i = 0, 1 do
CFuncs["Sound"].Create("rbxassetid://763717897", root, 5, 1.25)
CFuncs["Sound"].Create("rbxassetid://1192402877", root, 5,0.75)
CFuncs["Sound"].Create("rbxassetid://1664711478", root, 2.5,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 5, 0.75)
end
coroutine.resume(coroutine.create(function()
	wait(0.05)
	effx.Enabled = false
	wait(0.1)
	effx2.Enabled = false
	effx3.Enabled = false
end))
coroutine.resume(coroutine.create(function()
for i = 0, 9, 0.1 do
	task.wait()
	mult = mult + 0.5
lookavec = lookavec + 0.1*mult
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/10),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(40+lookavec/5,-15+lookavec*2,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.new(-40-lookavec/5,-15+lookavec*2,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.new(0,-15+lookavec*2,40+lookavec/5)
eloca4.CFrame = elocacenter.CFrame*CFrame.new(0,-15+lookavec*2,-40-lookavec/5)
end
for i,v in pairs(elocacenter:GetDescendants()) do
	if v:IsA("ParticleEmitter") then
		v.Enabled = false
	end
end
wait(6)
effx:Destroy()
effx2:Destroy()
effx3:Destroy()
elocacenter:Destroy()
end))
end


function RecolorThing2(one,onetran,two,three,four,five,exonetran,exone,extwotran,extwo,secondaryenabled,sectrailenabled)
local keptcolor = one
local locat = Instance.new("Part", char)
locat.CanCollide = false
locat.FormFactor = 3
locat.Name = "Ring"
locat.Material = "Neon"
locat.Size = Vector3.new(1, 1, 1)
locat.Transparency = 1
locat.TopSurface = 0
locat.BottomSurface = 0
locat.Anchored = true
locat.CFrame = root.CFrame*CFrame.new(0,-3,0)
local poste = 0
local rotation = 0
local upperpos = 0
local rate = 0
local x = locat

for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = onetran
v.BrickColor = one
v.Material = "Neon"
end
end

CFuncs["Sound"].Create("rbxassetid://763717897", char, 1.2, 1)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 0.5, 0.75)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 1.2, 0.95)
sphere2(1,"Add",x.CFrame*CFrame.new(0,0,0),vt(5,50000,5),1.5,1,1.5,two)
sphere2(2,"Add",x.CFrame*CFrame.new(0,0,0),vt(5,50000,5),1.5,1,1.5,one)
sphere2(4,"Add",x.CFrame*CFrame.new(0,0,0),vt(5,50000,5),1.5,1,1.5,keptcolor)
for i = 0, 99 do
local dis = CreateParta(char,1,1,"Neon",one)
dis.CFrame = root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),math.random(-5,5))*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-25000,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(25000,0,0)
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*math.random(500,2500)
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 10)
end
coroutine.resume(coroutine.create(function()
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",x)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(one.Color)
eff.Rate = 90000
eff.Lifetime = NumberRange.new(3,8)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,120,0),NumberSequenceKeypoint.new(0.2,25,0),NumberSequenceKeypoint.new(1,0.1,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.2,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(250,1500)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-100,100)
wait(0.7)
eff.Enabled = false
end))

for i = 0, 154 do
task.wait()
rotation = rotation + 5
poste = poste + 1
upperpos = upperpos + rate
rate = rate + 0.2
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(rotation),0)*CFrame.new(0,upperpos,poste),vt(2.5+upperpos/5,2.5+upperpos/5,2.5+upperpos/5),-0.05,-0.05,-0.05,two)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(90+rotation),0)*CFrame.new(0,upperpos,poste),vt(2.5+upperpos/5,2.5+upperpos/5,2.5+upperpos/5),-0.05,-0.05,-0.05,two)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(180+rotation),0)*CFrame.new(0,upperpos,poste),vt(2.5+upperpos/5,2.5+upperpos/5,2.5+upperpos/5),-0.05,-0.05,-0.05,two)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(270+rotation),0)*CFrame.new(0,upperpos,poste),vt(2.5+upperpos/5,2.5+upperpos/5,2.5+upperpos/5),-0.05,-0.05,-0.05,two)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(2.5+upperpos/10,2.5+upperpos/10,2.5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(90-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(3.5+upperpos/10,3.5+upperpos/10,3.5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(180-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(3.5+upperpos/10,3.5+upperpos/10,3.5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(270-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(3.5+upperpos/10,3.5+upperpos/10,3.5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
end
wait(6)
x:Destroy()
end))
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
if secondaryenabled == false then
v.Transparency = 1
elseif secondaryenabled == true then
v.Transparency = 0
end
v.BrickColor = two
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = three
v.Material = "Ice"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = four
v.Material = "Ice"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = five
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = exonetran
v.BrickColor = exone
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = extwotran
v.BrickColor = extwo
v.Material = "Neon"
end
end
end
function RecolorThing3(onetran)
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
end
end
CFuncs["EchoSound"].Create("rbxassetid://847061203", root, 1, 1,0,10,0.25,0.25,1)
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Material = "Ice"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Material = "Ice"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Transparency = 1
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 1
v.Transparency = 1
v.Material = "Neon"
end
end
end


function Chunks(PART)
	for i = 1, MRANDOM(3,5) do
		coroutine.resume(coroutine.create(function()
			local CHUNK = CreateParte(3, workspace, "Neon", 0, 0.5, BrickColor.random(), "Chunk", VT(0.3,0.3,0.3)*MRANDOM(7,13)/10, false)
			CHUNK.CFrame = PART.CFrame*ANGLES(RAD(MRANDOM(0,360)),RAD(MRANDOM(0,360)),RAD(MRANDOM(0,360)))
			local CFRAME = PART.CFrame*CF(MRANDOM(-4,4)/2,MRANDOM(-4,4)/2,-6)
			CHUNK.Velocity = CF(PART.Position,CFRAME.p).lookVector*MRANDOM(15,65)
			CHUNK.BrickColor = BrickColor.random()
			wait(0.1)
			CHUNK.CanCollide = true
			wait(MRANDOM(15,25)/5)
			for i = 1, 25 do
				task.wait()
				CHUNK.Transparency = CHUNK.Transparency + 1/25
			end
			CHUNK:remove()
		end))
	end
end

Debris = game:GetService("Debris")

function CreateFlyingDebree(FLOOR,POSITION,AMOUNT,BLOCKSIZE,SWAIT,STRENGTH)
	if FLOOR ~= nil then
		for i = 1, AMOUNT do
			local DEBREE = CreateParte(3, Effects, "Neon", 0.2, 0.2, "Peal", "Debree", BLOCKSIZE, false)
			DEBREE.Material = "Neon"
			DEBREE.BrickColor = BrickColor.random()
			DEBREE.CFrame = POSITION * ANGLES(RAD(MRANDOM(-360,360)),RAD(MRANDOM(-360,360)),RAD(MRANDOM(-360,360)))
			DEBREE.Velocity = vt(MRANDOM(-STRENGTH,STRENGTH),MRANDOM(-STRENGTH,STRENGTH),MRANDOM(-STRENGTH,STRENGTH))
			coroutine.resume(coroutine.create(function()
				task.wait(15)
				DEBREE.Parent = workspace
				DEBREE.CanCollide = true
				Debris:AddItem(DEBREE,SWAIT)
			end))
		end
	end
end

	

function CreatePart(Parent, Material, Reflectance, Transparency, BColor, Name, Size)
	local Part = Instance.new("Part")
	Part.Parent = Parent
	Part.Reflectance = Reflectance
	Part.Transparency = Transparency
	Part.CanCollide = false
	Part.Locked = true
	Part.BrickColor = BrickColor.new(tostring(BColor))
	Part.Name = Name
	Part.Size = Size
	Part.Material = Material

	Part.CustomPhysicalProperties = PhysicalProperties.new(0.001, 0.001, 0.001, 0.001, 0.001)
	RemoveOutlines(Part)
	return Part
end
function CreateWeld(Parent, Part0, Part1, C0, C1)
	local Weld = Instance.new("Weld")
	Weld.Parent = Parent
	Weld.Part0 = Part0
	Weld.Part1 = Part1
	Weld.C0 = C0
	Weld.C1 = C1

	return Weld
end

Character = Player.Character
PlayerGui = Player.PlayerGui
Backpack = Player.Backpack
Torso = Character.Torso
Head = Character.Head
Humanoid = Character.Humanoid
m = Instance.new("Model", Character)
LeftArm = Character["Left Arm"]
LeftLeg = Character["Left Leg"]
RightArm = Character["Right Arm"]
RightLeg = Character["Right Leg"]
LS = Torso["Left Shoulder"]
LH = Torso["Left Hip"]
RS = Torso["Right Shoulder"]
RH = Torso["Right Hip"]
Face = Head.face
Neck = Torso.Neck
it = Instance.new
attacktype = 1
cloaked = false
necko = cf(0, 1, 0, -1, 0, 0, 0, 0, 1, 0, 1, 0)
necko2 = cf(0, -0.5, 0, -1, 0, 0, 0, 0, 1, 0, 1, 0)
LHC0 = cf(-1, -1, 0, 0, 0, -1, 0, 1, 0, 1, 0, 0)
LHC1 = cf(-0.5, 1, 0, 0, 0, -1, 0, 1, 0, 1, 0, 0)
RHC0 = cf(1, -1, 0, 0, 0, 1, 0, 1, 0, -1, 0, 0)
RHC1 = cf(0.5, 1, 0, 0, 0, 1, 0, 1, 0, -1, 0, 0)
RootPart = Character.HumanoidRootPart
RootJoint = RootPart.RootJoint
attack = false
attackdebounce = false
deb = false
hand = false
MMouse = nil
combo = 0
mana = 0
trispeed = 0.2
attackmode = "none"
local idle = 0
local Anim = "Idle"
local Effects = {}
local gun = false
local shoot = false
local change = 1
local actualrotationvalue = 0
local OVMID = 147372923
local OVMPIT = 1
local OVMVOL = 1
player = nil
local toggleTag = true
local txt = Instance.new("BillboardGui", Head)
txt.Adornee = nil
txt.Name = "NameDetect"
txt.Size = UDim2.new(4, 0, 1.2, 0)
txt.StudsOffset = Vector3.new(-8, 5.333333333333333, 0)
local text = Instance.new("TextLabel", txt)
text.Size = UDim2.new(5, 0, 3.5, 0)
text.FontSize = "Size8"
text.TextScaled = true
text.BackgroundTransparency = 1
text.TextStrokeTransparency = 0
text.Font = "Antique"
text.TextStrokeColor3 = Color3.new(1, 0, 0)
text.TextColor3 = Color3.new(0.25, 0, 0)
text.Text = "MAYHEM"

pcall(function() Character.ReaperShadowHead.Eye1.BrickColor = BrickColor.new'Really red' end)
pcall(function() Character.ReaperShadowHead.Eye2.BrickColor = BrickColor.new'Crimson' end)

function RecolorTextAndRename(name, col1, col2, font)
	text.TextStrokeColor3 = col2
	text.TextColor3 = col1
	text.Text = name
	text.Font = font
	ned.Text = name
ned.TextColor3 = col1
ned.TextStrokeColor3 = col2
ned.Font = font
end

--wainbows
local r = 255
local g = 0
local b = 0
coroutine.resume(coroutine.create(function()
while task.wait() do
	for i = 0, 254/5 do
		task.wait()
		g = g + 5
	end
	for i = 0, 254/5 do
		task.wait()
		r = r - 5
	end
	for i = 0, 254/5 do
		task.wait()
		b = b + 5
	end
	for i = 0, 254/5 do
		task.wait()
		g = g - 5
	end
	for i = 0, 254/5 do
		task.wait()
		r = r + 5
	end
	for i = 0, 254/5 do
		task.wait()
		b = b - 5
	end
end
end))
--eaeaeaeae
local disably = false
local est = {"DEATH","INSANITY","MISERY","DREAD","CRAZED","CHAOS","VOID","MAYHEM","HeLp ME","LEt Me OuT","SaVe Me!","PLEaSe","KiLl IT!","DIE","hElp!","dEaD","BaNG","OUt!","SAvE","mE","oUt PleAse","savIng!","KiLl aLl","pOp","INSANITY"}
--clothes
--save shoulders 
RSH, LSH=nil, nil 
--welds 
RW, LW=Instance.new("Weld"), Instance.new("Weld") 
RW.Name="Right Shoulder" LW.Name="Left Shoulder"
LH=Torso["Left Hip"]
RH=Torso["Right Hip"]
TorsoColor=Torso.BrickColor
function NoOutline(Part)
Part.TopSurface,Part.BottomSurface,Part.LeftSurface,Part.RightSurface,Part.FrontSurface,Part.BackSurface = 10,10,10,10,10,10
end
ch=Character
RSH=ch.Torso["Right Shoulder"] 
LSH=ch.Torso["Left Shoulder"] 
-- 
RSH.Parent=nil 
LSH.Parent=nil 
-- 
RW.Name="Right Shoulder"
RW.Part0=ch.Torso 
RW.C0=cf(1.5, 0.5, 0) --* CFrame.fromEulerAnglesXYZ(1.3, 0, -0.5) 
RW.C1=cf(0, 0.5, 0) 
RW.Part1=ch["Right Arm"] 
RW.Parent=ch.Torso 
-- 
LW.Name="Left Shoulder"
LW.Part0=ch.Torso 
LW.C0=cf(-1.5, 0.5, 0) --* CFrame.fromEulerAnglesXYZ(1.7, 0, 0.8) 
LW.C1=cf(0, 0.5, 0) 
LW.Part1=ch["Left Arm"] 
LW.Parent=ch.Torso 
--

local Stats = Instance.new("BoolValue")
Stats.Name = "Stats"
Stats.Parent = Character
local Atk = Instance.new("NumberValue")
Atk.Name = "Damage"
Atk.Parent = Stats
Atk.Value = 1
local Def = Instance.new("NumberValue")
Def.Name = "Defense"
Def.Parent = Stats
Def.Value = 1
local Speed = Instance.new("NumberValue")
Speed.Name = "Speed"
Speed.Parent = Stats
Speed.Value = 1
local Mvmt = Instance.new("NumberValue")
Mvmt.Name = "Movement"
Mvmt.Parent = Stats
Mvmt.Value = 1
local donum = 0
function part(formfactor, parent, reflectance, transparency, brickcolor, name, size)
	local fp = it("Part")
	fp.formFactor = formfactor
	fp.Parent = parent
	fp.Reflectance = reflectance
	fp.Transparency = transparency
	fp.CanCollide = false
	fp.Locked = true
	fp.BrickColor = brickcolor
	fp.Name = name
	fp.Size = size
	fp.Position = Torso.Position
	NoOutline(fp)
	fp.Material = "SmoothPlastic"
	fp:BreakJoints()
	return fp
end
function mesh(Mesh, part, meshtype, meshid, offset, scale)
	local mesh = it(Mesh)
	mesh.Parent = part
	if Mesh == "SpecialMesh" then
		mesh.MeshType = meshtype
		if meshid ~= "nil" then
			mesh.MeshId = "http://www.roblox.com/asset/?id=" .. meshid
		end
	end
	mesh.Offset = offset
	mesh.Scale = scale
	return mesh
end
function weld(parent, part0, part1, c0)
	local weld = it("Weld")
	weld.Parent = parent
	weld.Part0 = part0
	weld.Part1 = part1
	weld.C0 = c0
	return weld
end
local Color1 = Torso.BrickColor
local bodvel = Instance.new("BodyVelocity")
local bg = Instance.new("BodyGyro")


function so(id, par, vol, pit)
	coroutine.resume(coroutine.create(function()
		local sou = Instance.new("Sound", par or workspace)
		sou.Volume = vol
		sou.Pitch = pit or 1
		sou.SoundId = id
		task.wait()
		sou:play()
		game:GetService("Debris"):AddItem(sou, 6)
	end))
end
function clerp(a, b, t)
	local qa = {
		QuaternionFromCFrame(a)
	}
	local qb = {
		QuaternionFromCFrame(b)
	}
	local ax, ay, az = a.x, a.y, a.z
	local bx, by, bz = b.x, b.y, b.z
	local _t = 1 - t
	return QuaternionToCFrame(_t * ax + t * bx, _t * ay + t * by, _t * az + t * bz, QuaternionSlerp(qa, qb, t))
end

function aclerp(startCF,endCF,alpha)
    return startCF:lerp(endCF, alpha)
end
 

function QuaternionFromCFrame(cf)
	local mx, my, mz, m00, m01, m02, m10, m11, m12, m20, m21, m22 = cf:components()
	local trace = m00 + m11 + m22
	if trace > 0 then
		local s = math.sqrt(1 + trace)
		local recip = 0.5 / s
		return (m21 - m12) * recip, (m02 - m20) * recip, (m10 - m01) * recip, s * 0.5
	else
		local i = 0
		if m00 < m11 then
			i = 1
		end
		if m22 > (i == 0 and m00 or m11) then
			i = 2
		end
		if i == 0 then
			local s = math.sqrt(m00 - m11 - m22 + 1)
			local recip = 0.5 / s
			return 0.5 * s, (m10 + m01) * recip, (m20 + m02) * recip, (m21 - m12) * recip
		elseif i == 1 then
			local s = math.sqrt(m11 - m22 - m00 + 1)
			local recip = 0.5 / s
			return (m01 + m10) * recip, 0.5 * s, (m21 + m12) * recip, (m02 - m20) * recip
		elseif i == 2 then
			local s = math.sqrt(m22 - m00 - m11 + 1)
			local recip = 0.5 / s
			return (m02 + m20) * recip, (m12 + m21) * recip, 0.5 * s, (m10 - m01) * recip
		end
	end
end
function QuaternionToCFrame(px, py, pz, x, y, z, w)
	local xs, ys, zs = x + x, y + y, z + z
	local wx, wy, wz = w * xs, w * ys, w * zs
	local xx = x * xs
	local xy = x * ys
	local xz = x * zs
	local yy = y * ys
	local yz = y * zs
	local zz = z * zs
	return CFrame.new(px, py, pz, 1 - (yy + zz), xy - wz, xz + wy, xy + wz, 1 - (xx + zz), yz - wx, xz - wy, yz + wx, 1 - (xx + yy))
end
function QuaternionSlerp(a, b, t)
	local cosTheta = a[1] * b[1] + a[2] * b[2] + a[3] * b[3] + a[4] * b[4]
	local startInterp, finishInterp
	if cosTheta >= 1.0E-4 then
		if 1 - cosTheta > 1.0E-4 then
			local theta = math.acos(cosTheta)
			local invSinTheta = 1 / math.sin(theta)
			startInterp = math.sin((1 - t) * theta) * invSinTheta
			finishInterp = math.sin(t * theta) * invSinTheta
		else
			startInterp = 1 - t
			finishInterp = t
		end
	elseif 1 + cosTheta > 1.0E-4 then
		local theta = math.acos(-cosTheta)
		local invSinTheta = 1 / math.sin(theta)
		startInterp = math.sin((t - 1) * theta) * invSinTheta
		finishInterp = math.sin(t * theta) * invSinTheta
	else
		startInterp = t - 1
		finishInterp = t
	end
	return a[1] * startInterp + b[1] * finishInterp, a[2] * startInterp + b[2] * finishInterp, a[3] * startInterp + b[3] * finishInterp, a[4] * startInterp + b[4] * finishInterp
end
local CFrameFromTopBack = function(at, top, back)
	local right = top:Cross(back)
	return CFrame.new(at.x, at.y, at.z, right.x, top.x, back.x, right.y, top.y, back.y, right.z, top.z, back.z)
end
function Triangle(a, b, c)
	local edg1 = (c - a):Dot((b - a).unit)
	local edg2 = (a - b):Dot((c - b).unit)
	local edg3 = (b - c):Dot((a - c).unit)
	if edg1 <= (b - a).magnitude and edg1 >= 0 then
		a, b = a, b
	elseif edg2 <= (c - b).magnitude and edg2 >= 0 then
		a, b, c = b, c, a
	elseif edg3 <= (a - c).magnitude and edg3 >= 0 then
		a, b, c = c, a, b
	else
		assert(false, "unreachable")
	end
	local len1 = (c - a):Dot((b - a).unit)
	local len2 = (b - a).magnitude - len1
	local width = (a + (b - a).unit * len1 - c).magnitude
	local maincf = CFrameFromTopBack(a, (b - a):Cross(c - b).unit, -(b - a).unit)
	local list = {}
	if len1 > 0.01 then
		local w1 = Instance.new("WedgePart", m)
		game:GetService("Debris"):AddItem(w1, 5)
		w1.Material = "SmoothPlastic"
		w1.FormFactor = "Custom"
		w1.BrickColor = BrickColor.new("Really red")
		w1.Transparency = 0
		w1.Reflectance = 0
		w1.Material = "SmoothPlastic"
		w1.CanCollide = false
		local l1 = Instance.new("PointLight", w1)
		l1.Color = Color3.new(170, 0, 0)
		NoOutline(w1)
		local sz = Vector3.new(0.2, width, len1)
		w1.Size = sz
		local sp = Instance.new("SpecialMesh", w1)
		sp.MeshType = "Wedge"
		sp.Scale = Vector3.new(0, 1, 1) * sz / w1.Size
		w1:BreakJoints()
		w1.Anchored = true
		w1.Parent = workspace
		w1.Transparency = 0.7
		table.insert(Effects, {
			w1,
			"Disappear",
			0.01
		})
		w1.CFrame = maincf * CFrame.Angles(math.pi, 0, math.pi / 2) * CFrame.new(0, width / 2, len1 / 2)
		table.insert(list, w1)
	end
	if len2 > 0.01 then
		local w2 = Instance.new("WedgePart", m)
		game:GetService("Debris"):AddItem(w2, 5)
		w2.Material = "SmoothPlastic"
		w2.FormFactor = "Custom"
		w2.BrickColor = BrickColor.new("Really red")
		w2.Transparency = 0
		w2.Reflectance = 0
		w2.Material = "SmoothPlastic"
		w2.CanCollide = false
		local l2 = Instance.new("PointLight", w2)
		l2.Color = Color3.new(170, 0, 0)
		NoOutline(w2)
		local sz = Vector3.new(0.2, width, len2)
		w2.Size = sz
		local sp = Instance.new("SpecialMesh", w2)
		sp.MeshType = "Wedge"
		sp.Scale = Vector3.new(0, 1, 1) * sz / w2.Size
		w2:BreakJoints()
		w2.Anchored = true
		w2.Parent = workspace
		w2.Transparency = 0.7
		table.insert(Effects, {
			w2,
			"Disappear",
			0.01
		})
		w2.CFrame = maincf * CFrame.Angles(math.pi, math.pi, -math.pi / 2) * CFrame.new(0, width / 2, -len1 - len2 / 2)
		table.insert(list, w2)
	end
	return unpack(list)
end
function Damagefunc(Part, hit, minim, maxim, knockback, Type, Property, Delay, HitSound, HitPitch)
	if hit.Parent == nil then
		return
	end
	local h = hit.Parent:FindFirstChildOfClass("Humanoid")
	for _, v in pairs(hit.Parent:children()) do
		if v:IsA("Humanoid") then
			h = v
		end
	end
	if h ~= nil and hit.Parent.Name ~= Character.Name and hit.Parent:FindFirstChild("Head") ~= nil then
		if hit.Parent:findFirstChild("DebounceHit") ~= nil and hit.Parent.DebounceHit.Value == true then
			return
		end
		local c = Instance.new("ObjectValue")
		c.Name = "creator"
		c.Value = game:GetService("Players").snowygold
		c.Parent = h

		game:GetService("Debris"):AddItem(c, 0.5)
		if HitSound ~= nil and HitPitch ~= nil then
			CFuncs.Sound.Create(HitSound, hit, 1, HitPitch)
		end
		local Damage = math.random(minim, maxim)
		local blocked = false
		local block = hit.Parent:findFirstChild("Block")
		if block ~= nil and block.className == "IntValue" and block.Value > 0 then
			blocked = true
			block.Value = block.Value - 1
			print(block.Value)
		end
		if blocked == false then
			local HitHealth = h.Health
			h.Health = h.Health - Damage
			if HitHealth ~= h.Health and HitHealth ~= 0 and 0 >= h.Health and h.Parent.Name ~= "Hologram" then
				print("gained kill")
			end
			ShowDamage(Part.CFrame * CFrame.new(0, 0, Part.Size.Z / 2).p + Vector3.new(0, 1.5, 0), -Damage, 1.5, Part.BrickColor.Color)
		else
			h.Health = h.Health - Damage / 2
			ShowDamage(Part.CFrame * CFrame.new(0, 0, Part.Size.Z / 2).p + Vector3.new(0, 1.5, 0), -Damage, 1.5, Part.BrickColor.Color)
		end
		if Type == "Knockdown" then
			local hum = hit.Parent.Humanoid
			hum.PlatformStand = true
			coroutine.resume(coroutine.create(function(HHumanoid)
				task.wait(1)
				HHumanoid.PlatformStand = false
			end), hum)
			local angle = hit.Position - (Property.Position + Vector3.new(0, 0, 0)).unit
			local bodvol = Instance.new("BodyVelocity")
			bodvol.Velocity = angle * knockback
			bodvol.P = 5000
			bodvol.MaxForce = Vector3.new(8000, 8000, 8000)
			bodvol.Parent = hit

			local rl = Instance.new("BodyAngularVelocity")
			rl.P = 3000
			rl.MaxTorque = Vector3.new(500000, 500000, 500000) * 50000000000000
			rl.AngularVelocity = Vector3.new(math.random(-10, 10), math.random(-10, 10), math.random(-10, 10))
			rl.Parent = hit

			game:GetService("Debris"):AddItem(bodvol, 0.5)
			game:GetService("Debris"):AddItem(rl, 0.5)
		elseif Type == "Normal" then
			local vp = Instance.new("BodyVelocity")
			vp.P = 500
			vp.MaxForce = Vector3.new(math.huge, 0, math.huge)
			vp.Velocity = Property.CFrame.LookVector * knockback + Property.Velocity / 1.05

			if knockback > 0 then
				vp.Parent = hit.Parent.Head
			end
			game:GetService("Debris"):AddItem(vp, 0.5)
		elseif Type == "Up" then
			local bodyVelocity = Instance.new("BodyVelocity")
			bodyVelocity.Velocity = Vector3.new(0, 20, 0)
			bodyVelocity.P = 5000
			bodyVelocity.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity.Parent = hit

			game:GetService("Debris"):AddItem(bodyVelocity, 0.5)
			local bodyVelocity = Instance.new("BodyVelocity")
			bodyVelocity.Velocity = Vector3.new(0, 20, 0)
			bodyVelocity.P = 5000
			bodyVelocity.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity.Parent = hit

			game:GetService("Debris"):AddItem(bodyVelocity, 1)
		elseif Type == "Leech" then
			local hum = hit.Parent.Humanoid
			if hum ~= nil then
				for i = 0, 2 do
					Effects.Sphere.Create(BrickColor.new("Bright red"), hit.Parent.Torso.CFrame * cn(0, 0, 0) * angles(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50)), 1, 15, 1, 0, 5, 0, 0.02)
				end
				Humanoid.Health = Humanoid.Health + 10
			end
		elseif Type == "UpKnock" then
			local hum = hit.Parent.Humanoid
			hum.PlatformStand = true
			if hum ~= nil then
				hitr = true
			end
			coroutine.resume(coroutine.create(function(HHumanoid)
				task.wait(5)
				HHumanoid.PlatformStand = false
				hitr = false
			end), hum)
			local bodyVelocity = Instance.new("BodyVelocity")
			bodyVelocity.Velocity = Vector3.new(0, 20, 0)
			bodyVelocity.P = 5000
			bodyVelocity.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity.Parent = hit

			game:GetService("Debris"):AddItem(bodyVelocity, 0.5)
			local bodyVelocity = Instance.new("BodyVelocity")
			bodyVelocity.Velocity = Vector3.new(0, 20, 0)
			bodyVelocity.P = 5000
			bodyVelocity.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity.Parent = hit

			game:GetService("Debris"):AddItem(bodyVelocity, 1)
		elseif Type == "Snare" then
			local bp = Instance.new("BodyPosition")
			bp.P = 2000
			bp.D = 100
			bp.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
			bp.Position = hit.Parent.Torso.Position
			bp.Parent = hit.Parent.Torso

			game:GetService("Debris"):AddItem(bp, 1)
		elseif Type == "Slashnare" then
			Effects.Block.Create(BrickColor.new("Pastel Blue"), hit.Parent.Torso.CFrame * cn(0, 0, 0), 60, 60, 60, 12, 12, 12, 0.07)
			for i = 1, math.random(4, 5) do
				Effects.Sphere.Create(BrickColor.new("Teal"), hit.Parent.Torso.CFrame * cn(math.random(-5, 5), math.random(-5, 5), math.random(-5, 5)) * angles(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50)), 1, 15, 1, 0, 5, 0, 0.02)
			end
			local bp = Instance.new("BodyPosition")
			bp.P = 2000
			bp.D = 100
			bp.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
			bp.Position = hit.Parent.Torso.Position
			bp.Parent = hit.Parent.Torso

			game:GetService("Debris"):AddItem(bp, 1)
		elseif Type == "Spike" then
			CreateBigIceSword(hit.Parent.Torso.CFrame)
			local bp = Instance.new("BodyPosition")
			bp.P = 2000
			bp.D = 100
			bp.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
			bp.Position = hit.Parent.Torso.Position
			bp.Parent = hit.Parent.Torso

			game:GetService("Debris"):AddItem(bp, 1)
		elseif Type == "Freeze" then
			local BodPos = Instance.new("BodyPosition")
			BodPos.P = 50000
			BodPos.D = 1000
			BodPos.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
			BodPos.Position = hit.Parent.Torso.Position
			BodPos.Parent = hit.Parent.Torso

			local BodGy = Instance.new("BodyGyro")
			BodGy.MaxTorque = Vector3.new(400000, 400000, 400000) * math.huge
			BodGy.P = 20000
			BodGy.Parent = hit.Parent.Torso
			BodGy.CFrame = hit.Parent.Torso.CFrame

			hit.Parent.Torso.Anchored = true
			coroutine.resume(coroutine.create(function(Part)
				task.wait(1.5)
				Part.Anchored = false
			end), hit.Parent.Torso)
			game:GetService("Debris"):AddItem(BodPos, 3)
			game:GetService("Debris"):AddItem(BodGy, 3)
		end
		local debounce = Instance.new("BoolValue")
		debounce.Name = "DebounceHit"
		debounce.Parent = hit.Parent
		debounce.Value = true

		game:GetService("Debris"):AddItem(debounce, Delay)
		c = Instance.new("ObjectValue")
		c.Name = "creator"
		c.Value = Player
		c.Parent = h
		game:GetService("Debris"):AddItem(c, 0.5)
	end
		end

function ShowDamage(Pos, Text, Time, Color)
	local Rate = 0.03333333333333333
	local Pos = Pos or Vector3.new(0, 0, 0)
	local Text = Text or ""
	local Time = Time or 2
	local Color = Color or Color3.new(1, 0, 1)
	local EffectPart = CreatePart(workspace, "SmoothPlastic", 0, 1, BrickColor.new(Color), "Effect", Vector3.new(0, 0, 0))
	EffectPart.Anchored = true
	local BillboardGui = Instance.new("BillboardGui")
	BillboardGui.Size = UDim2.new(3, 0, 3, 0)
	BillboardGui.Adornee = EffectPart
	BillboardGui.Parent = EffectPart

	local TextLabel = Instance.new("TextLabel")
	TextLabel.BackgroundTransparency = 1
	TextLabel.Size = UDim2.new(1, 0, 1, 0)
	TextLabel.Text = Text
	TextLabel.TextColor3 = Color
	TextLabel.TextScaled = true
	TextLabel.Font = Enum.Font.ArialBold
	TextLabel.Parent = BillboardGui

	game.Debris:AddItem(EffectPart, Time + 0.1)
	EffectPart.Parent = game:GetService("Workspace")
	delay(0, function()
		local Frames = Time / Rate
		for Frame = 1, Frames do
			wait(Rate)
			local Percent = Frame / Frames
			EffectPart.CFrame = CFrame.new(Pos) + Vector3.new(0, Percent, 0)
			TextLabel.TextTransparency = Percent
		end
		if EffectPart and EffectPart.Parent then
			EffectPart:Destroy()
		end
	end)
end
function MagniDamage(Part, magni, mindam, maxdam, knock, Type)
	for _, c in pairs(workspace:children()) do
		local hum = c:findFirstChildOfClass("Humanoid")
		if hum ~= nil then
			local head = c:findFirstChild("Head")
			if head ~= nil then
				local targ = head.Position - Part.Position
				local mag = targ.magnitude
				if magni >= mag and c.Name ~= Player.Name then
					Damagefunc(head, head, mindam, maxdam, knock, Type, RootPart, 0.1, "rbxassetid://231917784", 1)
				end
			end
		end
	end
end
function MagniDamageWithEffect(Part, magni, mindam, maxdam, knock, Type)
	for _, c in pairs(workspace:children()) do
		local hum = c:findFirstChild("Humanoid")
		if hum ~= nil then
			local head = c:findFirstChild("Torso")
			if head ~= nil then
				local targ = head.Position - Part.Position
				local mag = targ.magnitude
				if magni >= mag and c.Name ~= Player.Name then
					MagicBlock(BrickColor.new("Pastel light blue"), head.CFrame, 5, 5, 5, 1, 1, 1, 0.05)
					Damagefunc(head, head, mindam, maxdam, knock, Type, RootPart, 0.1, "rbxassetid://231917784", 1)
				end
			end
		end
	end
end

function ApplyDamage(Humanoid,Damage,OneShot)
	Damage = Damage * DAMAGEMULTIPLIER
	local DEAD = false
	if Humanoid.Health < 2000 and OneShot == false then
		if Humanoid.Health - Damage > 0 then
			Humanoid.Health = Humanoid.Health - Damage
		else
			Humanoid.Parent:BreakJoints()
			DEAD = true
		end
	else
		DEAD = true
		Humanoid.Parent:BreakJoints()
	end
	if DEAD == true then
		local PARTS = {}
		for index, CHILD in pairs(Humanoid.Parent:GetChildren()) do
			if CHILD:IsA("BasePart") then
				table.insert(PARTS,CHILD)
			end
		end
		coroutine.resume(coroutine.create(function()
			wait(2)
			repeat
				task.wait()
				local PIECE = nil
				if MRANDOM(1,5) == 1 then
					for E = 1, #PARTS do
						if MRANDOM(1,5) == 1 then
							PIECE = PARTS[E]
							table.remove(PARTS,E)
							break
						end
					end
				end
				if PIECE ~= nil then
					PIECE:remove()
				end
			until #PARTS == 0
		end))
	end
end


function Raycast(POSITION, DIRECTION, RANGE, IGNOREDECENDANTS)
	return workspace:FindPartOnRay(Ray.new(POSITION, DIRECTION.unit * RANGE), IGNOREDECENDANTS)
end

function rayCast(Pos, Dir, Max, Ignore)
	return game:service("Workspace"):FindPartOnRay(Ray.new(Pos, Dir.unit * (Max or 999.999)), Ignore)
end
function SkullEffect(brickcolor, cframe, x1, y1, z1, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = mesh("SpecialMesh", prt, "FileMesh", "http://www.roblox.com/asset/?id=4770583", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 2)
	CF = prt.CFrame
	coroutine.resume(coroutine.create(function(Part, Mesh, TehCF)
		for i = 0, 1, 0.2 do
			wait()
			Part.CFrame = CF * cf(0, 0, -0.4)
		end
		for i = 0, 1, delay do
			wait()
			Mesh.Scale = Mesh.Scale
		end
		for i = 0, 1, 0.1 do
			wait()
			Part.Transparency = i
		end
		Part.Parent = nil
	end), prt, msh, CF)
end
function MagicBlock(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	prt.CFrame = prt.CFrame * euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			task.wait()
			Part.CFrame = Part.CFrame * euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicBlockSteady(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicSphere(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	prt.CFrame = prt.CFrame * euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
	msh = mesh("SpecialMesh", prt, "Sphere", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			wait()
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicBlockSteady(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicShock(brickcolor, cframe, x1, y1, x3, y3, delay, rottype)
	local prt = part(3, char, 1, 1, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	local dec = decal(prt.Color, "http://www.roblox.com/asset/?id=874580939", "Front", prt)
	local dec2 = decal(prt.Color, "http://www.roblox.com/asset/?id=874580939", "Front", prt)
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, 0.01))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			dec.Transparency = i
			dec2.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, 0)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicShockAlt(brickcolor, cframe, x1, y1, x3, y3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, 0.01))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			prt.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, 0)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicShockAltCircle(brickcolor, cframe, x1, z1, x3, z3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, 1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0.1, 0)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, -0.1, 0)
			end
			prt.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, 0, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicShockTrailAlt(brickcolor, cframe, x1, y1, z1, x3, y3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			prt.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, 0)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicShockTrailAlt2(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay, rottype)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.Material = "Neon"
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		local rtype = rottype
		for i = 0, 1, delay do
			task.wait()
			if rtype == 1 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, 0.1)
			elseif rtype == 2 then
				prt.CFrame = prt.CFrame * CFrame.Angles(0, 0, -0.1)
			end
			prt.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicBlock2(brickcolor, cframe, Parent, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, char, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = false
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	local wld = weld(prt, prt, Parent, cframe)
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh, Weld)
		for i = 0, 1, delay do
			wait()
			Weld.C0 = euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50)) * cframe
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh, wld)
end
function MagicBlock3(brickcolor, cframe, Parent, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = false
	prt.CFrame = cframe
	msh = mesh("BlockMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	local wld = weld(prt, prt, Parent, euler(0, 0, 0) * cf(0, 0, 0))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh, Weld)
		for i = 0, 1, delay do
			wait()
			Weld.C0 = euler(i * 20, 0, 0)
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh, wld)
end
function MagicCircle2(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = mesh("CylinderMesh", prt, "", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 2)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			wait()
			Part.CFrame = Part.CFrame
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
			local prt2 = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
			prt2.Anchored = true
			prt2.CFrame = cframe * euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
			local msh2 = mesh("SpecialMesh", prt2, "Sphere", "", vt(0, 0, 0), vt(0.5, 0.5, 0.5))
			game:GetService("Debris"):AddItem(prt2, 2)
			coroutine.resume(coroutine.create(function(Part, Mesh)
				for i = 0, 1, 0.1 do
					wait()
					Part.CFrame = Part.CFrame * cf(0, 0.5, 0)
				end
				Part.Parent = nil
			end), prt2, msh2)
		end
		for i = 0, 1, delay * 2 do
			wait()
			Part.CFrame = Part.CFrame
			Mesh.Scale = vt(x1 + x3 - (x1 + x3) * i, y1 + y3 - (y1 + y3) * i, z1 + z3 - (z1 + z3) * i)
		end
		Part.Parent = nil
	end), prt, msh)
end
function MagicCircle(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = mesh("SpecialMesh", prt, "Sphere", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 2)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			wait()
			Part.CFrame = Part.CFrame
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function BreakEffect(brickcolor, cframe, x1, y1, z1)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe * euler(math.random(-50, 50), math.random(-50, 50), math.random(-50, 50))
	local msh = mesh("SpecialMesh", prt, "Sphere", "", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 2)
	coroutine.resume(coroutine.create(function(Part, CF, Numbb, randnumb)
		CF = Part.CFrame
		Numbb = 0
		randnumb = math.random() / 10
		rand1 = math.random() / 10
		for i = 0, 1, rand1 do
			wait()
			CF = CF * cf(0, math.random() / 2, 0)
			Part.CFrame = CF * euler(Numbb, 0, 0)
			Part.Transparency = i
			Numbb = Numbb + randnumb
		end
		Part.Parent = nil
	end), prt, CF, Numbb, randnumb)
end
function MagicWaveThing(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	msh = mesh("SpecialMesh", prt, "FileMesh", "http://www.roblox.com/asset/?id=1051557", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			wait()
			Part.CFrame = Part.CFrame * euler(0, 0.7, 0)
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
	
	

function Magic(bonuspeed, type, pos, scale, value, color, MType)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = MType
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, scaler2 * bonuspeed)
		end
		rng:Destroy()
	end))
end
	
		
function BlockEffect(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay, Type)
	local prt = CreatePart(workspace, "Neon", 0, 0, brickcolor, "Effect", Vector3.new())
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = CreateMeshe("BlockMesh", prt, "", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 10)
	if Type == 1 or Type == nil then
		table.insert(Effects, {
			prt,
			"Block1",
			delay,
			x3,
			y3,
			z3,
			msh
		})
	elseif Type == 2 then
		table.insert(Effects, {
			prt,
			"Block2",
			delay,
			x3,
			y3,
			z3,
			msh
		})
	end
end

function SphereEffect(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = CreatePart(workspace, "Neon", 0, 0, brickcolor, "Effect", Vector3.new())
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = CreateMeshe("SpecialMesh", prt, "Sphere", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 10)
	table.insert(Effects, {
		prt,
		"Cylinder",
		delay,
		x3,
		y3,
		z3,
		msh
	})
end

function Aura(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos, MType)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = MType
	rngm.Scale = Vector3.new(x1, y1, z1)
	local scaler2 = 1
	local speeder = FastSpeed
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			speeder = speeder - 0.01 * FastSpeed * bonuspeed
			rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
		end
		rng:Destroy()
	end))
end

function RingEffect(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
local prt=CreatePart(workspace,"Neon",0,0,brickcolor,"Effect",vt(.5,.5,.5))--part(3,workspace,"SmoothPlastic",0,0,brickcolor,"Effect",vt(0.5,0.5,0.5))
prt.Anchored=true
prt.CFrame=cframe
msh=CreateMeshe("SpecialMesh",prt,"FileMesh","http://www.roblox.com/asset/?id=3270017",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,2)
coroutine.resume(coroutine.create(function(Part,Mesh,num) 
for i=0,1,delay do
task.wait()
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh,(math.random(0,1)+math.random())/5)
end

function CylinderEffect(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = CreatePart(workspace, "SmoothPlastic", 0, 0, brickcolor, "Effect", Vector3.new())
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = CreateMeshe("CylinderMesh", prt, "", "", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 10)
	table.insert(Effects, {
		prt,
		"Cylinder",
		delay,
		x3,
		y3,
		z3,
		msh
	})
end

function WaveEffecte(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = CreatePart(workspace, "Neon", 0, 0, brickcolor, "Effect", Vector3.new())
	prt.Anchored = true
	prt.CFrame = cframe
	local msh = CreateMeshe("SpecialMesh", prt, "FileMesh", "rbxassetid://20329976", Vector3.new(0, 0, 0), Vector3.new(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 10)
	table.insert(Effects, {
		prt,
		"Cylinder",
		delay,
		x3,
		y3,
		z3,
		msh
	})
end

function WaveEffect(brickcolor, cframe, x1, y1, z1, x3, y3, z3, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe
	msh = mesh("SpecialMesh", prt, "FileMesh", "rbxassetid://20329976", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 2)
	coroutine.resume(coroutine.create(function(Part, Mesh)
		for i = 0, 1, delay do
			wait()
			Part.CFrame = Part.CFrame * cf(0, y3 / 2, 0)
			Part.Transparency = i
			Mesh.Scale = Mesh.Scale + vt(x3, y3, z3)
		end
		Part.Parent = nil
	end), prt, msh)
end
function StravEffect(brickcolor, cframe, x, y, z, x1, y1, z1, delay)
	local prt = part(3, workspace, 0, 0, brickcolor, "Effect", vt(0.5, 0.5, 0.5))
	prt.Anchored = true
	prt.CFrame = cframe * cf(x, y, z)
	msh = mesh("SpecialMesh", prt, "FileMesh", "rbxassetid://168892363", vt(0, 0, 0), vt(x1, y1, z1))
	game:GetService("Debris"):AddItem(prt, 5)
	coroutine.resume(coroutine.create(function(Part, Mesh, ex, why, zee)
		local num = math.random()
		local num2 = math.random(-3, 2) + math.random()
		local numm = 0
		for i = 0, 1, delay * 2 do
			task.wait()
			Part.CFrame = cframe * euler(0, numm * num * 10, 0) * cf(ex, why, zee) * cf(-i * 10, num2, 0)
			Part.Transparency = i
			numm = numm + 0.01
		end
		Part.Parent = nil
		Mesh.Parent = nil
	end), prt, msh, x, y, z)
end

function waveEff(bonuspeed,type,typeoftrans,pos,scale,value,value2,color)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
if typeoftrans == "In" then
rng.Transparency = 1
end
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "FileMesh"
rngm.MeshId = "rbxassetid://20329976"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
end
local randomrot = math.random(1,2)
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
end
if randomrot == 1 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(5*bonuspeed/2),0)
elseif randomrot == 2 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(-5*bonuspeed/2),0)
end
if typeoftrans == "Out" then
rng.Transparency = rng.Transparency + 0.01*bonuspeed
elseif typeoftrans == "In" then
rng.Transparency = rng.Transparency - 0.01*bonuspeed
end
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2*bonuspeed)
end
rng:Destroy()
end))
end
 
 

function dmgstart(dmg, what)
	hitcon = what.Touched:connect(function(hit)
		local hum = hit.Parent:FindFirstChild("Humanoid")
		if hum and not hum:IsDescendantOf(Character) then
			hum:TakeDamage(dmg)
		end
	end)
end
function dmgstop()
	hitcon:disconnect()
end
function Cloak()
	Face.Parent = nil
	cloaked = true
	for _, v in pairs(Torso.Parent:children()) do
		if v.className == "Part" and v.Name ~= "HumanoidRootPart" then
			coroutine.resume(coroutine.create(function()
				for i = 0, 1, 0.2 do
					wait()
					v.Transparency = i
				end
				v.Transparency = 1
			end))
		end
		if v.className == "Hat" then
			hatp = v.Handle
			coroutine.resume(coroutine.create(function(derp)
				for i = 0, 1, 0.2 do
					wait()
					derp.Transparency = i
				end
				derp.Transparency = 1
			end), hatp)
		end
	end
	for _, v in pairs(m:children()) do
		if v.className == "Part" then
			coroutine.resume(coroutine.create(function()
				for i = 0, 1, 0.2 do
					wait()
					v.Transparency = i
				end
				v.Transparency = 1
			end))
		end
	end
end
function UnCloak()
	so("http://roblox.com/asset/?id=2767090", Torso, 1, 1.1)
	Face.Parent = Head
	cloaked = false
	for _, v in pairs(Torso.Parent:children()) do
		if v.className == "Part" and v.Name ~= "HumanoidRootPart" then
			coroutine.resume(coroutine.create(function()
				for i = 0, 1, 0.1 do
					wait()
					v.Transparency = v.Transparency - 0.1
				end
				v.Transparency = 0
			end))
		end
		if v.className == "Hat" then
			hatp = v.Handle
			coroutine.resume(coroutine.create(function(derp)
				for i = 0, 1, 0.1 do
					wait()
					derp.Transparency = derp.Transparency - 0.1
				end
				derp.Transparency = 0
			end), hatp)
		end
	end
	for _, v in pairs(m:children()) do
		if v.className == "Part" and v.Name ~= "hitbox" and v.Name ~= "tip" then
			coroutine.resume(coroutine.create(function()
				for i = 0, 1, 0.1 do
					wait()
					v.Transparency = v.Transparency - 0.1
				end
				v.Transparency = 0
			end))
			v.Transparency = 0
		end
	end
end
--explosions
local origcolor = BrickColor.new("Pastel light blue")
function Explode(rad, par, pitch, vol, mindam, maxdam)
	local expart = Instance.new("Part", char)
	local expart2 = Instance.new("Part", char)
	local rin = Instance.new("Part", char)
	local rin2 = Instance.new("Part", char)
	local partMesh = Instance.new("SpecialMesh", expart)
	partMesh.MeshType = "Sphere"
	local partMesh2 = Instance.new("SpecialMesh", expart2)
	partMesh2.MeshType = "Sphere"
	local partMesh3 = Instance.new("SpecialMesh", rin)
	partMesh3.MeshType = "Brick"
	local partMesh4 = Instance.new("SpecialMesh", rin2)
	partMesh4.MeshType = "Brick"
	CFuncs.Sound.Create("rbxassetid://165970126", expart, vol, pitch)
	partMesh.Scale = vt(rad, rad, rad)
	expart.Size = vt(1, 1, 1)
	expart.Transparency = 0
	expart.Anchored = true
	expart.Material = "Neon"
	expart.BrickColor = bc("White")
	expart.CFrame = par.CFrame
	partMesh2.Scale = vt(rad, rad, rad)
	expart2.Size = vt(1.15, 1.15, 1.15)
	expart2.Transparency = 0.5
	expart2.Anchored = true
	expart2.Material = "Neon"
	expart2.BrickColor = par.BrickColor
	expart2.CFrame = par.CFrame
	rin.Size = vt(1.15, 1.15, 1.15)
	rin.Transparency = 1
	rin.Anchored = true
	rin.Material = "Neon"
	rin.BrickColor = par.BrickColor
	rin.CFrame = par.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)))
	rin2.Size = vt(1.15, 1.15, 1.15)
	rin2.Transparency = 1
	rin2.Anchored = true
	rin2.Material = "Neon"
	rin2.BrickColor = par.BrickColor
	rin2.CFrame = par.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)))
	partMesh3.Scale = vt(0, 1, 0)
	partMesh4.Scale = vt(0, 1, 0)
	local dec2 = Instance.new("Decal", rin)
	dec2.Face = "Top"
	dec2.Texture = "http://www.roblox.com/asset/?id=874580939"
	dec2.Parent = rin
	local dec2b = dec2:Clone()
	dec2b.Face = "Bottom"
	dec2b.Parent = rin
	local dec2a = Instance.new("Decal", rin2)
	dec2a.Face = "Top"
	dec2a.Texture = "http://www.roblox.com/asset/?id=874580939"
	dec2a.Parent = rin2
	local dec2ab = dec2a:Clone()
	dec2ab.Face = "Bottom"
	dec2ab.Parent = rin2
	expart.CanCollide = false
	expart2.CanCollide = false
	rin.CanCollide = false
	rin2.CanCollide = false
	MagniDamage(par, rad * 5, mindam, maxdam, 0, "Normal")
	local value = 1 * rad / 6.5
	for i = 0, 199 do
		partMesh.Scale = partMesh.Scale + vt(value, value, value)
		expart.CFrame = expart.CFrame
		partMesh2.Scale = partMesh2.Scale + vt(value, value, value)
		expart2.CFrame = expart.CFrame
		value = value - 0.035 * rad / 30
		if value < 7.5 then
			partMesh3.Scale = partMesh3.Scale + vt(rad / 5, 0, rad / 5)
			rin.CFrame = rin.CFrame * CFrame.Angles(0, math.rad(1), 0)
			partMesh4.Scale = partMesh4.Scale + vt(rad / 7.5, 0, rad / 7.5)
			rin2.CFrame = rin2.CFrame * CFrame.Angles(0, math.rad(-1), 0)
		end
		if value < 0 then
			dec2.Transparency = dec2.Transparency + 0.025
			dec2a.Transparency = dec2a.Transparency + 0.025
			dec2b.Transparency = dec2b.Transparency + 0.025
			dec2ab.Transparency = dec2ab.Transparency + 0.025
			expart.Transparency = expart.Transparency + 0.025
			expart2.Transparency = expart2.Transparency + 0.025
			rin.Transparency = rin.Transparency + 0.025
			rin2.Transparency = rin2.Transparency + 0.025
		end
		task.wait()
	end
	game:GetService("Debris"):AddItem(expart, 1)
	game:GetService("Debris"):AddItem(expart2, 1)
	game:GetService("Debris"):AddItem(rin, 1)
	game:GetService("Debris"):AddItem(rin2, 1)
end
function ExplodeShort(rad, par, pitch, vol, mindam, maxdam)
	local expart = Instance.new("Part", char)
	local expart2 = Instance.new("Part", char)
	local partMesh = Instance.new("SpecialMesh", expart)
	partMesh.MeshType = "Sphere"
	local partMesh2 = Instance.new("SpecialMesh", expart2)
	partMesh2.MeshType = "Sphere"
	CFuncs.Sound.Create("http://www.roblox.com/asset/?id=142070127", expart, vol, pitch)
	partMesh.Scale = vt(rad, rad, rad)
	expart.Size = vt(1, 1, 1)
	expart.Transparency = 0
	expart.Anchored = true
	expart.Material = "Neon"
	expart.BrickColor = bc("White")
	expart.CFrame = par.CFrame
	partMesh2.Scale = vt(rad, rad, rad)
	expart2.Size = vt(1.15, 1.15, 1.15)
	expart2.Transparency = 0.5
	expart2.Anchored = true
	expart2.Material = "Neon"
	expart2.BrickColor = par.BrickColor
	expart2.CFrame = par.CFrame
	expart.CanCollide = false
	expart2.CanCollide = false
	MagniDamage(par, rad * 2.5, mindam, maxdam, 0, "Normal")
	local value = 1 * rad / 6.5
	for i = 0, 75 do
		partMesh.Scale = partMesh.Scale + vt(value, value, value)
		expart.CFrame = expart.CFrame
		partMesh2.Scale = partMesh2.Scale + vt(value, value, value)
		expart2.CFrame = expart.CFrame
		value = value - 0.035 * rad / 5
		if value < 0 then
			value = 0
			expart.Transparency = expart.Transparency + 0.05
			expart2.Transparency = expart2.Transparency + 0.05
		end
		task.wait()
	end
	game:GetService("Debris"):AddItem(expart, 1)
	game:GetService("Debris"):AddItem(expart2, 1)
end
function AreaDanger(rad, par, mindam, maxdam)
	local expart = Instance.new("Part", char)
	local partMesh = Instance.new("SpecialMesh", expart)
	CFuncs.Sound.Create("rbxassetid://231917784", expart, 1.5, 1.15)
	partMesh.MeshType = "Sphere"
	partMesh.Scale = vt(rad, rad, rad)
	expart.Size = vt(1, 1, 1)
	expart.Transparency = 0.5
	expart.Anchored = true
	expart.Material = "Neon"
	expart.CanCollide = false
	expart.BrickColor = par.BrickColor
	expart.CFrame = par.CFrame
	local value = 1 * rad / 5
	MagicBlock(origcolor, expart.CFrame, 0, 0, 0, rad / 2, rad / 2, rad / 2, 0.1)
	for i = 0, 14 do
		wait()
		partMesh.Scale = partMesh.Scale + vt(value, value, value)
		expart.CFrame = expart.CFrame
		value = value - 0.035 * rad
		if value < 0 then
			value = 0
		end
	end
	wait(0.25)
	CFuncs.Sound.Create("rbxassetid://588738544", expart, 1.5, 1)
	wait(0.5)
	CFuncs.Sound.Create("rbxassetid://588737825", expart, 1.5, 1)
	CFuncs.Sound.Create("rbxassetid://231917784", expart, 1.5, 0.75)
	MagniDamageWithEffect(par, rad, mindam, maxdam, 0, "Normal")
	MagicBlock(origcolor, expart.CFrame, rad * 2, rad * 2, rad * 2, 0.1, 0.1, 0.1, 0.025)
	for i = 0, 14 do
		wait()
		partMesh.Scale = partMesh.Scale + vt(value, value, value)
		expart.CFrame = expart.CFrame
		value = value - 0.035 * rad / 2
	end
	expart.Transparency = 1
	game:GetService("Debris"):AddItem(expart, 5)
end
function Swarmsplosions(negrad, rad, par, mindam, maxdam)
	CFuncs.Sound.Create("rbxassetid://588737825", par, 2.5, 2)
	CFuncs.Sound.Create("rbxassetid://231917784", par, 2.5, 1)
	CFuncs.Sound.Create("rbxassetid://231917744", par, 2.5, 1)
	CFuncs.Sound.Create("rbxassetid://233856106", par, 2.5, 1)
	MagniDamageWithEffect(par, 25, 5, 10, 0, "Normal")
	MagicBlock(origcolor, par.CFrame, 5, 5, 5, 5, 5, 5, 0.025)
	for i = 0, 24 do
		MagicShockTrailAlt2(origcolor, par.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 2, 2, 5, -0.01, -0.01, 25, 0.005, math.random(1, 2))
	end
	for i = 0, 24 do
		local expart = Instance.new("Part", char)
		expart.Transparency = 1
		expart.Anchored = true
		expart.CanCollide = false
		expart.CFrame = par.CFrame * CFrame.new(math.random(negrad, rad), math.random(negrad, rad), math.random(negrad, rad))
		CFuncs.Sound.Create("rbxassetid://588737825", expart, 1, 2)
		CFuncs.Sound.Create("rbxassetid://231917784", expart, 1.5, 1.15)
		MagniDamage(expart, rad / 2, mindam, maxdam, 0, "Normal")
		MagicBlock(origcolor, expart.CFrame, rad, rad, rad, 0.1, 0.1, 0.1, 0.025)
		for i = 0, 9 do
			MagicShockTrailAlt2(origcolor, expart.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 2, 2, 5, -0.01, -0.01, 5, 0.05, math.random(1, 2))
		end
		game:GetService("Debris"):AddItem(expart, 2)
		wait(0.1)
	end
end
function EXterPlosion(par)
	CFuncs.Sound.Create("rbxassetid://919941001", par, 10, 1)
	CFuncs.Sound.Create("rbxassetid://138213851", par, 5, 0.85)
	CFuncs.Sound.Create("rbxassetid://157878578", par, 5, 0.2)
	CFuncs.Sound.Create("rbxassetid://233856106", par, 2.5, 1)
	MagniDamageWithEffect(par, 500, 80, 99, 0, "Normal")
	MagicBlock(origcolor, par.CFrame, 5, 5, 5, 5, 5, 5, 0.005)
	MagicBlock(origcolor, par.CFrame, 0, 0, 0, 150, 150, 150, 0.1)
	for i = 0, 24 do
		MagicShockTrailAlt2(origcolor, par.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 50, 50, 5, -0.5, -0.5, 500, 0.1, math.random(1, 2))
	end
	for i = 0, 24 do
		MagicShockTrailAlt2(origcolor, par.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 50, 50, 5, -0.25, -0.25, 50, 0.005, math.random(1, 2))
	end
end
function ring(type, pos, scale, value)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = origcolor
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshId = "http://www.roblox.com/asset/?id=3270017"
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value
			end
			rng.Transparency = rng.Transparency + 0.01
			rngm.Scale = rngm.Scale + Vector3.new(scaler2, scaler2, 0)
		end
		rng:Destroy()
	end))
end
function wave(type, pos, scale, value)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = origcolor
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshId = "http://www.roblox.com/asset/?id=20329976"
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value
			end
			rng.Transparency = rng.Transparency + 0.01
			rngm.Scale = rngm.Scale + Vector3.new(scaler2, scaler2, scaler2)
		end
		rng:Destroy()
	end))
end
function wind(type, pos, scale, value, speed)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = origcolor
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshId = "http://www.roblox.com/asset/?id=1051557"
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value
			end
			rng.CFrame = rng.CFrame * CFrame.Angles(0, 0.025 * speed, 0)
			rng.Transparency = rng.Transparency + 0.01
			rngm.Scale = rngm.Scale + Vector3.new(scaler2, scaler2, scaler2)
		end
		rng:Destroy()
	end))
end
function groundwind(type, pos, scale, value, speed)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = origcolor
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshId = "http://www.roblox.com/asset/?id=1051557"
	rngm.Scale = scale
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10, 0.1 do
			task.wait()
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value
			end
			rng.CFrame = rng.CFrame * CFrame.Angles(0, 0.025 * speed, 0)
			rng.Transparency = rng.Transparency + 0.01
			rngm.Scale = rngm.Scale + Vector3.new(scaler2, scaler2 / 5, scaler2)
		end
		rng:Destroy()
	end))
end
function CameraManager()
	if TwoD and not CamInterrupt then
		if Humanoid.Health > 0 then
			Camera.CameraSubject = Humanoid
			Camera.CameraType = "Scriptable"
			Humanoid.AutoRotate = false
			if Booleans.GyroUse then
				Directer.MaxTorque = Vec3(0, huge, 0)
			else
				Directer.MaxTorque = Vec3(0, 0, 0)
			end
			if TargetInfo[1] ~= nil and TargetInfo[2] ~= nil then
				if Booleans.CamFollow then
					CPart.CFrame = cFrame(RootPart.Position, Vec3(TargetInfo[1].Position.X, RootPart.Position.Y, TargetInfo[1].Position.Z))
					Directer.CFrame = cFrame((RootPart.CFrame * cFrame(0, 0, 10)).p, TargetInfo[1].Position)
				else
					CPart.Position = RootPart.Position
				end
			else
				local ahead = (RootPart.CFrame * cFrame(0, 0, -3)).p
				CPart.CFrame = cFrame(RootPart.Position, Vec3(ahead.X, RootPart.Position.Y, ahead.Z))
			end
			Camera.CFrame = lerp(Camera.CFrame, CPart.CFrame * cFrame(25, 3, 0) * Euler(0, radian(90), 0), 0.2)
		else
			Camera.CameraSubject = Humanoid
			Camera.CameraType = "Custom"
		end
	end
end
function sphere(bonuspeed, type, pos, scale, value, color)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = "Sphere"
	rngm.Scale = scale
	if rainbowmode == true then
		rng.Color = Color3.new(r / 255, g / 255, b / 255)
	end
	local scaler2 = 1
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if rainbowmode == true then
				rng.Color = Color3.new(r / 255, g / 255, b / 255)
			end
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			if chaosmode == true or insanitymode == true then
				rng.BrickColor = BrickColor.random()
			end
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, scaler2 * bonuspeed)
		end
		rng:Destroy()
	end))
	end
	function sphere2(bonuspeed,type,pos,scale,value,value2,value3,color)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
if ModeOfGlitch ~= 8376532578634534 then
        rng.BrickColor = color
elseif ModeOfGlitch == 8376532578634534 then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
end
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Sphere"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
local scaler2c = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
scaler2c = 1*value3
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
scaler2c = 1/value3
end
if ModeOfGlitch == 8376532578634534 then
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rng.Parent ~= nil then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
else
break
end
end
end))
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
scaler2c = scaler2c - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
scaler2c = scaler2c - 0.01/value*bonuspeed
end
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2c*bonuspeed)
end
rng:Destroy()
end))
end


	function sphere23(bonuspeed,type,pos,scale,value,value2,value3,color)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
if ModeOfGlitch ~= 8376532578634534 then
        rng.BrickColor = color
elseif ModeOfGlitch == 8376532578634534 then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
end
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Granite"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Sphere"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
local scaler2c = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
scaler2c = 1*value3
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
scaler2c = 1/value3
end
if ModeOfGlitch == 8376532578634534 then
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rng.Parent ~= nil then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
else
break
end
end
end))
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
scaler2c = scaler2c - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
scaler2c = scaler2c - 0.01/value*bonuspeed
end
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2c*bonuspeed)
end
rng:Destroy()
end))
end

	function Block3(bonuspeed,type,pos,scale,value,value2,value3,color)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
if ModeOfGlitch ~= 8376532578634534 then
        rng.BrickColor = color
elseif ModeOfGlitch == 8376532578634534 then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
end
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
local scaler2c = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
scaler2c = 1*value3
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
scaler2c = 1/value3
end
if ModeOfGlitch == 8376532578634534 then
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rng.Parent ~= nil then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
else
break
end
end
end))
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
scaler2c = scaler2c - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
scaler2c = scaler2c - 0.01/value*bonuspeed
end
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2c*bonuspeed)
end
rng:Destroy()
end))
end

	function Block2(bonuspeed,type,pos,scale,value,value2,value3,color)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
if ModeOfGlitch ~= 8376532578634534 then
        rng.BrickColor = color
elseif ModeOfGlitch == 8376532578634534 then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
end
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
local scaler2c = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
scaler2c = 1*value3
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
scaler2c = 1/value3
end
if ModeOfGlitch == 8376532578634534 then
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if rng.Parent ~= nil then
rng.Color = Color3.new(kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000,kan.PlaybackLoudness/1000)
else
break
end
end
end))
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
scaler2c = scaler2c - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
scaler2c = scaler2c - 0.01/value*bonuspeed
end
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2c*bonuspeed)
end
rng:Destroy()
end))
end



function ragdoll(who)
	pcall(function()
	local ded = who
	local h1 = ded:FindFirstChild("Head")
	local t1 = ded:FindFirstChild("Torso") or ded:FindFirstChild("UpperTorso")
	if t1.Name == "UpperTorso" then
		r15r(ded)
		return ragdoll
	end
	local ff = ded:FindFirstChildOfClass("ForceField")
	if ff ~= nil then
		ff:Destroy()
	end
	local ra1 = ded:FindFirstChild("Right Arm")
	local la1 = ded:FindFirstChild("Left Arm")
	local rl1 = ded:FindFirstChild("Right Leg")
	local ll1 = ded:FindFirstChild("Left Leg")
	local hum1 = ded:FindFirstChildOfClass("Humanoid")
	local acc = ded:FindFirstChild("xdded")
	if acc == nil then 
	local ac = Instance.new("Glue",ded) ac.Name = "xdded"
	local rut1 = ded:FindFirstChild("HumanoidRootPart")
	hum1.PlatformStand = true
	if rut1 ~= nil then
		rut1.Parent = nil
	end
	pcall(function()
	for i,v in pairs(who:GetChildren()) do
		if v:IsA("Accessory") or v:IsA("Hat") then
			local gl = Instance.new("WeldConstraint",v.Handle)
			gl.Part0 = h1 gl.Part1 = v.Handle
		end
	end
	for i,v in pairs(who:GetChildren()) do
		if v:IsA("Script") or v:IsA("LocalScript") then
			if v.Name == "Health" then
				v.Parent = nil
			end
		end
	end
	for i,v in pairs(who:GetChildren()) do
		if v:IsA("BasePart") then
			v.Anchored = false
		end
		if v:IsA("Accessory") or v:IsA("Hat") then
			v.Handle.Anchored = false
		end
	end
	end)
	hum1.MaxHealth = 100
	hum1.Health = math.random(10,50)
	t1:BreakJoints()
	ra1:BreakJoints()
	la1:BreakJoints()
	rl1:BreakJoints()
	ll1:BreakJoints()
	--//Joints~//--
	--Neck--
	if h1 ~= nil then
	local neca = Instance.new("Glue",t1) neca.Part0 = t1 neca.Part1 = h1 neca.C0 = CFrame.new(0,t1.Size.y/2,0) neca.C1 = CFrame.new(0,-h1.Size.y/2,0) neca.Name = "yo"
	local ch = Instance.new("Part",t1) ch.Name = "yo" ch.Size = Vector3.new(h1.Size.x/2,h1.Size.y/2,h1.Size.z/2 + h1.Size.z/4) ch.TopSurface = "Smooth" ch.BottomSurface = "Smooth" ch.Transparency = 1
	local wh = Instance.new("Weld",ch) wh.Part0 = h1 wh.Part1 = ch
	end
	--Right Arm--
	if ra1 ~= nil then
	local rsa = Instance.new("Glue",t1) rsa.Part0 = t1 rsa.Part1 = ra1 rsa.C0 = CFrame.new(t1.Size.x/2 + t1.Size.x/4,t1.Size.y/4,0) rsa.C1 = CFrame.new(0,ra1.Size.y/4,0) rsa.Name = "yo"
	local cra = Instance.new("Part",t1) cra.Name = "yo" cra.Size = Vector3.new(ra1.Size.y/2 + ra1.Size.y/4,ra1.Size.y/2,ra1.Size.z) cra.TopSurface = "Smooth" cra.BottomSurface = "Smooth" cra.Transparency = 1
	local wra = Instance.new("Weld",cra) wra.Part0 = ra1 wra.Part1 = cra wra.C0 = CFrame.new(0,-ra1.Size.y/8,0) * CFrame.Angles(rad(0),rad(0),rad(90))
	end
	--Left Arm--
	if la1 ~= nil then
	local lsa = Instance.new("Glue",t1) lsa.Part0 = t1 lsa.Part1 = la1 lsa.C0 = CFrame.new(-t1.Size.x/2 - t1.Size.x/4,t1.Size.y/4,0) lsa.C1 = CFrame.new(0,la1.Size.y/4,0) lsa.Name = "yo"
	local cla = Instance.new("Part",t1) cla.Name = "yo" cla.Size = Vector3.new(la1.Size.y/2 + la1.Size.y/4,la1.Size.y/2,la1.Size.z) cla.TopSurface = "Smooth" cla.BottomSurface = "Smooth" cla.Transparency = 1
	local wla = Instance.new("Weld",cla) wla.Part0 = la1 wla.Part1 = cla wla.C0 = CFrame.new(0,-la1.Size.y/8,0) * CFrame.Angles(rad(0),rad(0),rad(90))
	end
	--Right Leg--
	if rl1 ~= nil then
	local rha = Instance.new("Glue",t1) rha.Part0 = t1 rha.Part1 = rl1 rha.C0 = CFrame.new(t1.Size.x/4,-t1.Size.y/2,0) rha.C1 = CFrame.new(0,rl1.Size.y/2,0) rha.Name = "yo"
	local crl = Instance.new("Part",t1) crl.Name = "yo" crl.Size = Vector3.new(rl1.Size.y/2 + rl1.Size.y/4,rl1.Size.y/2,rl1.Size.z) crl.TopSurface = "Smooth" crl.BottomSurface = "Smooth" crl.Transparency = 1
	local wrl = Instance.new("Weld",crl) wrl.Part0 = rl1 wrl.Part1 = crl wrl.C0 = CFrame.new(0,-rl1.Size.y/8,0) * CFrame.Angles(rad(0),rad(0),rad(90))
	end
	--Left Leg--
	if ll1 ~= nil then
	local lha = Instance.new("Glue",t1) lha.Part0 = t1 lha.Part1 = ll1 lha.C0 = CFrame.new(-t1.Size.x/4,-t1.Size.y/2,0) lha.C1 = CFrame.new(0,ll1.Size.y/2,0) lha.Name = "yo"
	local cll = Instance.new("Part",t1) cll.Name = "yo" cll.Size = Vector3.new(ll1.Size.y/2 + ll1.Size.y/4,ll1.Size.y/2,ll1.Size.z) cll.TopSurface = "Smooth" cll.BottomSurface = "Smooth" cll.Transparency = 1
	local wll = Instance.new("Weld",cll) wll.Part0 = ll1 wll.Part1 = cll wll.C0 = CFrame.new(0,-ll1.Size.y/8,0) * CFrame.Angles(rad(0),rad(0),rad(90))
	end
	--//End of Joints~//--
end
end)
end

function r15r(who)
	local ded = who
	local ac = ded:FindFirstChild("xdded")
	if ac == nil then
	Instance.new("Glue",ded).Name = "xdded"
	local h2 = ded:FindFirstChild("Head")
	local t2 = ded:FindFirstChild("UpperTorso")
	local lt2 = ded:FindFirstChild("LowerTorso")
	local rua2 = ded:FindFirstChild("RightUpperArm")
	local lua2 = ded:FindFirstChild("LeftUpperArm")
	local rla2 = ded:FindFirstChild("RightLowerArm")
	local lla2 = ded:FindFirstChild("LeftLowerArm")
	local rh2 = ded:FindFirstChild("RightHand")
	local lh2 = ded:FindFirstChild("LeftHand")
	local rul2 = ded:FindFirstChild("RightUpperLeg")
	local lul2 = ded:FindFirstChild("LeftUpperLeg")
	local rll2 = ded:FindFirstChild("RightLowerLeg")
	local lll2 = ded:FindFirstChild("LeftLowerLeg")
	local rf2 = ded:FindFirstChild("RightFoot")
	local lf2 = ded:FindFirstChild("LeftFoot")
	local rut1 = ded:FindFirstChild("HumanoidRootPart")
	if rut1 ~= nil then
		rut1:Destroy()
	end
	for i,v in pairs(who:GetChildren()) do
		if v:IsA("Script") or v:IsA("LocalScript") then
			if v.Name == "Health" then
				v.Parent = nil
			end
		end
	end
	local hum1 = ded:FindFirstChildOfClass("Humanoid")
	hum1.PlatformStand = true
	hum1.MaxHealth = 100
	hum1.Health = math.random(10,50)
	local trans = 1
	if h2 ~= nil then
		h2:BreakJoints()
		local nc = Instance.new("Glue",t2) nc.Name = "yo" nc.C0 = CFrame.new(0,t2.Size.y/2,0) nc.C1 = CFrame.new(0,-h2.Size.y/2,0) nc.Part0 = t2 nc.Part1 = h2
		local ncc = Instance.new("Part",t2) ncc.Name = "yo" ncc.Transparency = trans ncc.Size = Vector3.new(h2.Size.x/2 + h2.Size.x/4,h2.Size.y/2,h2.Size.z)
		local ncw = Instance.new("Weld",t2) ncw.Name = "yo" ncw.Part0 = h2 ncw.Part1 = ncc
	end
	for i,v in pairs(who:GetChildren()) do
		if v:IsA("BasePart") then
			v.Anchored = false
		end
		if v:IsA("Accessory") or v:IsA("Hat") then
			v.Handle.Anchored = false
			local aw = Instance.new("WeldConstraint",v) aw.Part0 = h2 aw.Part1 = v.Handle
		end
	end
	hum1.PlatformStand = true
	if lt2 ~= nil then
		lt2:BreakJoints()
		local tc = Instance.new("Glue",t2) tc.Name = "yo" tc.C0 = CFrame.new(0,-t2.Size.y/2,0) tc.C1 = CFrame.new(0,lt2.Size.y/2,0) tc.Part0 = t2 tc.Part1 = lt2
		local tcc = Instance.new("Part",t2) tcc.Name = "yo" tcc.Transparency = trans tcc.Size = Vector3.new(lt2.Size.x/2,lt2.Size.y/2,lt2.Size.z)
		local tcw = Instance.new("Weld",t2) tcw.Name = "yo" tcw.Part0 = lt2 tcw.Part1 = tcc
	end
	if rua2 ~= nil then
		rua2:BreakJoints()
		local ruac = Instance.new("Glue",t2) ruac.Name = "yo" ruac.C0 = CFrame.new(t2.Size.x/2 + t2.Size.y/4,t2.Size.y/4,0) ruac.C1 = CFrame.new(0,rua2.Size.y/4.6666,0) ruac.Part0 = t2 ruac.Part1 = rua2
		local ruacc = Instance.new("Part",t2) ruacc.Name = "yo" ruacc.Transparency = trans ruacc.Size = Vector3.new(rua2.Size.x/1.2,rua2.Size.y/4,rua2.Size.z/1.2)
		local ruacw = Instance.new("Weld",t2) ruacw.Name = "yo" ruacw.Part0 = rua2 ruacw.Part1 = ruacc ruacw.C0 = CFrame.new(0,rua2.Size.y/7,0)
	end
	if lua2 ~= nil then
		lua2:BreakJoints()
		local luac = Instance.new("Glue",t2) luac.Name = "yo" luac.C0 = CFrame.new(-t2.Size.x/2 + -t2.Size.y/4,t2.Size.y/4,0) luac.C1 = CFrame.new(0,lua2.Size.y/4.6666,0) luac.Part0 = t2 luac.Part1 = lua2
		local luacc = Instance.new("Part",t2) luacc.Name = "yo" luacc.Transparency = trans luacc.Size = Vector3.new(lua2.Size.x/1.2,lua2.Size.y/4,lua2.Size.z/1.2)
		local luacw = Instance.new("Weld",t2) luacw.Name = "yo" luacw.Part0 = lua2 luacw.Part1 = luacc luacw.C0 = CFrame.new(0,lua2.Size.y/7,0)
	end
	if rla2 ~= nil then
		rla2:BreakJoints()
		local rlac = Instance.new("Glue",t2) rlac.Name = "yo" rlac.C0 = CFrame.new(0,-rua2.Size.y/4.6666,0) rlac.C1 = CFrame.new(0,rla2.Size.y/8,0) rlac.Part0 = rua2 rlac.Part1 = rla2
		local rlacc = Instance.new("Part",t2) rlacc.Name = "yo" rlacc.Transparency = trans rlacc.Size = Vector3.new(rla2.Size.x/1.2,rla2.Size.y/4,rla2.Size.z/1.2)
		local rlacw = Instance.new("Weld",t2) rlacw.Name = "yo" rlacw.Part0 = rla2 rlacw.Part1 = rlacc rlacw.C0 = CFrame.new(0,-rla2.Size.y/7,0)
	end
	if lla2 ~= nil then
		lla2:BreakJoints()
		local llac = Instance.new("Glue",t2) llac.Name = "yo" llac.C0 = CFrame.new(0,-lua2.Size.y/4.6666,0) llac.C1 = CFrame.new(0,lla2.Size.y/8,0) llac.Part0 = lua2 llac.Part1 = lla2
		local llacc = Instance.new("Part",t2) llacc.Name = "yo" llacc.Transparency = trans llacc.Size = Vector3.new(lla2.Size.x/1.2,lla2.Size.y/4,lla2.Size.z/1.2)
		local llacw = Instance.new("Weld",t2) llacw.Name = "yo" llacw.Part0 = lla2 llacw.Part1 = llacc llacw.C0 = CFrame.new(0,-lla2.Size.y/7,0)
	end
	if rh2 ~= nil then
		rh2:BreakJoints()
		local rhc = Instance.new("Glue",t2) rhc.Name = "yo" rhc.C0 = CFrame.new(0,-rla2.Size.y/2,0) rhc.C1 = CFrame.new(0,rh2.Size.y/3,0) rhc.Part0 = rla2 rhc.Part1 = rh2
		local rhcc = Instance.new("Part",t2) rhcc.Name = "yo" rhcc.Transparency = trans rhcc.Size = Vector3.new(rh2.Size.x/1.2,rh2.Size.y,rh2.Size.z/1.2)
		local rhcw = Instance.new("Weld",t2) rhcw.Name = "yo" rhcw.Part0 = rh2 rhcw.Part1 = rhcc rhcw.C0 = CFrame.new(0,0,0)
	end
	if lh2 ~= nil then
		lh2:BreakJoints()
		local lhc = Instance.new("Glue",t2) lhc.Name = "yo" lhc.C0 = CFrame.new(0,-lla2.Size.y/2,0) lhc.C1 = CFrame.new(0,lh2.Size.y/3,0) lhc.Part0 = lla2 lhc.Part1 = lh2
		local lhcc = Instance.new("Part",t2) lhcc.Name = "yo" lhcc.Transparency = trans lhcc.Size = Vector3.new(lh2.Size.x/1.2,lh2.Size.y,lh2.Size.z/1.2)
		local lhcw = Instance.new("Weld",t2) lhcw.Name = "yo" lhcw.Part0 = lh2 lhcw.Part1 = lhcc lhcw.C0 = CFrame.new(0,0,0)
	end
	if rul2 ~= nil then
		rul2:BreakJoints()
		local rulc = Instance.new("Glue",t2) rulc.Name = "yo" rulc.C0 = CFrame.new(lt2.Size.x/4,-lt2.Size.y/2,0) rulc.C1 = CFrame.new(0,rul2.Size.y/3,0) rulc.Part0 = lt2 rulc.Part1 = rul2
		local rulcc = Instance.new("Part",t2) rulcc.Name = "yo" rulcc.Transparency = trans rulcc.Size = Vector3.new(rul2.Size.x/1.2,rul2.Size.y/4,rul2.Size.z/1.2)
		local rulcw = Instance.new("Weld",t2) rulcw.Name = "yo" rulcw.Part0 = rul2 rulcw.Part1 = rulcc rulcw.C0 = CFrame.new(0,rul2.Size.y/7,0)
	end
	if lul2 ~= nil then
		lul2:BreakJoints()
		local lulc = Instance.new("Glue",t2) lulc.Name = "yo" lulc.C0 = CFrame.new(-lt2.Size.x/4,-lt2.Size.y/2,0) lulc.C1 = CFrame.new(0,lul2.Size.y/3,0) lulc.Part0 = lt2 lulc.Part1 = lul2
		local lulcc = Instance.new("Part",t2) lulcc.Name = "yo" lulcc.Transparency = trans lulcc.Size = Vector3.new(lul2.Size.x/1.2,lul2.Size.y/4,lul2.Size.z/1.2)
		local lulcw = Instance.new("Weld",t2) lulcw.Name = "yo" lulcw.Part0 = lul2 lulcw.Part1 = lulcc lulcw.C0 = CFrame.new(0,lul2.Size.y/7,0)
	end
	if rll2 ~= nil then
		rll2:BreakJoints()
		local rllc = Instance.new("Glue",t2) rllc.Name = "yo" rllc.C0 = CFrame.new(0,-rll2.Size.y/6,0) rllc.C1 = CFrame.new(0,rll2.Size.y/5,0) rllc.Part0 = rul2 rllc.Part1 = rll2
		local rllcc = Instance.new("Part",t2) rllcc.Name = "yo" rllcc.Transparency = trans rllcc.Size = Vector3.new(rll2.Size.x/1.2,rll2.Size.y/3.5,rll2.Size.z/1.2)
		local rllcw = Instance.new("Weld",t2) rllcw.Name = "yo" rllcw.Part0 = rll2 rllcw.Part1 = rllcc rllcw.C0 = CFrame.new(0,-rll2.Size.y/7,0)
	end
	if lll2 ~= nil then
		lll2:BreakJoints()
		local lllc = Instance.new("Glue",t2) lllc.Name = "yo" lllc.C0 = CFrame.new(0,-lll2.Size.y/6,0) lllc.C1 = CFrame.new(0,lll2.Size.y/5,0) lllc.Part0 = lul2 lllc.Part1 = lll2
		local lllcc = Instance.new("Part",t2) lllcc.Name = "yo" lllcc.Transparency = trans lllcc.Size = Vector3.new(lll2.Size.x/1.2,lll2.Size.y/3.5,lll2.Size.z/1.2)
		local lllcw = Instance.new("Weld",t2) lllcw.Name = "yo" lllcw.Part0 = lll2 lllcw.Part1 = lllcc lllcw.C0 = CFrame.new(0,-lll2.Size.y/7,0)
	end
	if rf2 ~= nil then
		rf2:BreakJoints()
		local rfc = Instance.new("Glue",t2) rfc.Name = "yo" rfc.C0 = CFrame.new(0,-rul2.Size.y/2.7,0) rfc.C1 = CFrame.new(0,rll2.Size.y/6,0) rfc.Part0 = rll2 rfc.Part1 = rf2
		local rfcc = Instance.new("Part",t2) rfcc.Name = "yo" rfcc.Transparency = trans rfcc.Size = Vector3.new(rf2.Size.x/1,rf2.Size.y,rf2.Size.z/1)
		local rfcw = Instance.new("Weld",t2) rfcw.Name = "yo" rfcw.Part0 = rf2 rfcw.Part1 = rfcc
	end
	if lf2 ~= nil then
		lf2:BreakJoints()
		local lfc = Instance.new("Glue",t2) lfc.Name = "yo" lfc.C0 = CFrame.new(0,-lul2.Size.y/2.7,0) lfc.C1 = CFrame.new(0,lll2.Size.y/6,0) lfc.Part0 = lll2 lfc.Part1 = lf2
		local lfcc = Instance.new("Part",t2) lfcc.Name = "yo" lfcc.Transparency = trans lfcc.Size = Vector3.new(lf2.Size.x/1,lf2.Size.y,lf2.Size.z/1)
		local lfcw = Instance.new("Weld",t2) lfcw.Name = "yo" lfcw.Part0 = lf2 lfcw.Part1 = lfcc
	end
	end
end
-------------slash down here

	function slash(bonuspeed,rotspeed,rotatingop,typeofshape,type,typeoftrans,pos,scale,value,color)
local type = type
local rotenable = rotatingop
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
if typeoftrans == "In" then
rng.Transparency = 1
end
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "FileMesh"
if typeofshape == "Normal" then
rngm.MeshId = "rbxassetid://662586858"
elseif typeofshape == "Round" then
rngm.MeshId = "rbxassetid://662585058"
end
rngm.Scale = scale
local scaler2 = 1/10
if type == "Add" then
scaler2 = 1*value/10
elseif type == "Divide" then
scaler2 = 1/value/10
end
local randomrot = math.random(1,2)
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed/10
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed/10
end
if rotenable == true then
if randomrot == 1 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(rotspeed*bonuspeed/2),0)
elseif randomrot == 2 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(-rotspeed*bonuspeed/2),0)
end
end
if typeoftrans == "Out" then
rng.Transparency = rng.Transparency + 0.01*bonuspeed
elseif typeoftrans == "In" then
rng.Transparency = rng.Transparency - 0.01*bonuspeed
end
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed/10, 0, scaler2*bonuspeed/10)
end
rng:Destroy()
end))
end


function slash2(bonuspeed,rotspeed,rotatingop,typeofshape,type,typeoftrans,pos,scale,value,color)
local type = type
local rotenable = rotatingop
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
if typeoftrans == "In" then
rng.Transparency = 1
end
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "FileMesh"
if typeofshape == "Normal" then
rngm.MeshId = "rbxassetid://662586858"
elseif typeofshape == "Round" then
rngm.MeshId = "rbxassetid://662585058"
end
rngm.Scale = scale
local scaler2 = 1/10
if type == "Add" then
scaler2 = 1*value/10
elseif type == "Divide" then
scaler2 = 1/value/10
end
local randomrot = math.random(1,2)
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed/10
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed/10
end
if rotenable == true then
if randomrot == 1 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(rotspeed*bonuspeed/2),0)
elseif randomrot == 2 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(-rotspeed*bonuspeed/2),0)
end
end
if typeoftrans == "Out" then
rng.Transparency = rng.Transparency + 0.01*bonuspeed
elseif typeoftrans == "In" then
rng.Transparency = rng.Transparency - 0.01*bonuspeed
end
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed/10, 0, scaler2*bonuspeed/10)
end
rng:Destroy()
end))
end

	function slash3(bonuspeed,rotspeed,rotatingop,typeofshape,type,typeoftrans,pos,scale,value,color)
local type = type
local rotenable = rotatingop
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
if typeoftrans == "In" then
rng.Transparency = 1
end
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "FileMesh"
if typeofshape == "Normal" then
rngm.MeshId = "rbxassetid://13425802"
elseif typeofshape == "Round" then
rngm.MeshId = "rbxassetid://13425802"
end
rngm.Scale = scale
local scaler2 = 1/10
if type == "Add" then
scaler2 = 1*value/10
elseif type == "Divide" then
scaler2 = 1/value/10
end
local randomrot = math.random(1,2)
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed/10
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed/10
end
if rotenable == true then
if randomrot == 1 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(rotspeed*bonuspeed/2),0)
elseif randomrot == 2 then
rng.CFrame = rng.CFrame*CFrame.Angles(0,math.rad(-rotspeed*bonuspeed/2),0)
end
end
if typeoftrans == "Out" then
rng.Transparency = rng.Transparency + 0.01*bonuspeed
elseif typeoftrans == "In" then
rng.Transparency = rng.Transparency - 0.01*bonuspeed
end
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed/10, 0, scaler2*bonuspeed/10)
end
rng:Destroy()
end))
end


function PixelBlock(bonuspeed,FastSpeed,type,pos,x1,y1,z1,value,color,outerpos)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*outerpos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = vt(x1,y1,z1)
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
local scaler2 = 1
local speeder = FastSpeed/10
if type == "Add" then
scaler2 = 1*value
elseif type == "Divide" then
scaler2 = 1/value
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
end
if chaosmode == true then
rng.BrickColor = BrickColor.random()
end
speeder = speeder - 0.01*FastSpeed*bonuspeed/10
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*speeder*bonuspeed
--rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale - Vector3.new(scaler2*bonuspeed, scaler2*bonuspeed, scaler2*bonuspeed)
end
rng:Destroy()
end))
end

function PixelBlockX(bonuspeed,FastSpeed,type,pos,x1,y1,z1,value,color,outerpos)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*outerpos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = vt(x1,y1,z1)
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
local scaler2 = 1
local speeder = FastSpeed/10
if type == "Add" then
scaler2 = 1*value
elseif type == "Divide" then
scaler2 = 1/value
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
end
if chaosmode == true then
rng.BrickColor = BrickColor.random()
end
speeder = speeder - 0.01*FastSpeed*bonuspeed/10
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*speeder*bonuspeed
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale - Vector3.new(scaler2*bonuspeed, scaler2*bonuspeed, scaler2*bonuspeed)
end
rng:Destroy()
end))
end

function PixelBlockNeg(bonuspeed,FastSpeed,type,pos,x1,y1,z1,value,color,outerpos)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*outerpos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = vt(x1,y1,z1)
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
local scaler2 = 0
local speeder = FastSpeed/10
if type == "Add" then
scaler2 = 1*value
elseif type == "Divide" then
scaler2 = 1/value
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
end
if chaosmode == true then
rng.BrickColor = BrickColor.random()
end
speeder = speeder + 0.01*FastSpeed*bonuspeed/10
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*speeder*bonuspeed
--rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale - Vector3.new(scaler2*bonuspeed, scaler2*bonuspeed, scaler2*bonuspeed)
end
rng:Destroy()
end))
end

function block(bonuspeed,type,pos,scale,value,value2,value3,color,color3)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.Color = color3
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Brick"
rngm.Scale = scale
local scaler2 = 1
local scaler2b = 1
local scaler2c = 1
if type == "Add" then
scaler2 = 1*value
scaler2b = 1*value2
scaler2c = 1*value3
elseif type == "Divide" then
scaler2 = 1/value
scaler2b = 1/value2
scaler2c = 1/value3
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
scaler2b = scaler2b - 0.01*value/bonuspeed
scaler2c = scaler2c - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
scaler2b = scaler2b - 0.01/value*bonuspeed
scaler2c = scaler2c - 0.01/value*bonuspeed
end
rng.CFrame = rng.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2b*bonuspeed, scaler2c*bonuspeed)
end
rng:Destroy()
end))
end
function sphereMK(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = "Sphere"
	rngm.Scale = vt(x1, y1, z1)
	if rainbowmode == true then
		rng.Color = Color3.new(r / 255, g / 255, b / 255)
	end
	local scaler2 = 1
	local speeder = FastSpeed
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if rainbowmode == true then
				rng.Color = Color3.new(r / 255, g / 255, b / 255)
			end
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			if chaosmode == true or insanitymode == true then
				rng.BrickColor = BrickColor.random()
			end
			speeder = speeder - 0.01 * FastSpeed * bonuspeed
			rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
		end
		rng:Destroy()
	end))
	end
	function blockMK(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 0
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = "Brick"
	rngm.Scale = vt(x1, y1, z1)
	if rainbowmode == true then
		rng.Color = Color3.new(r / 255, g / 255, b / 255)
	end
	local scaler2 = 1
	local speeder = FastSpeed
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if rainbowmode == true then
				rng.Color = Color3.new(r / 255, g / 255, b / 255)
			end
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			if chaosmode == true or insanitymode == true then
				rng.BrickColor = BrickColor.random()
			end
			speeder = speeder - 0.01 * FastSpeed * bonuspeed
			rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
			rng.Transparency = rng.Transparency + 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
		end
		rng:Destroy()
	end))
	end
	
	

function Chat(text)
	--if(game.PlaceId ~= 843468296)then
		coroutine.wrap(function()
			if(char:FindFirstChild'ChatGUI')then char.ChatGUI:destroy() end
			local BBG = NewInstance("BillboardGui",char,{Name='ChatGUI',Size=UDim2.new(0,100,0,40),StudsOffset=V3.N(0,2,0),Adornee=Head})
			local Txt = NewInstance("TextLabel",BBG,{Text = "",BackgroundTransparency=1,TextColor3=MAINRUINCOLOR,BorderSizePixel=0,Font=Enum.Font.Antique,TextSize=50,TextStrokeTransparency=1,Size=UDim2.new(1,0,.5,0)})
			local SND = Sound(Head,418252437,M.RNG(9,11)/10,3,false,false,true)
			for i = 1, #text do
				delay(i/25, function()
					SND.Pitch = M.RNG(9,11)/10
					SND.Volume = 3
					SND.Parent = FXFolder
					SND:Play()
					Txt.Text = text:sub(1,i)
				end)
			end
			delay((#text/25)+2.5, function()
				for i = 0, 1, .025 do
					Txt.TextTransparency=i
					Txt.Rotation = M.RNG(-25,25)
					Txt.Position = UDim2.new(0,M.RNG(-15,15),0,M.RNG(-15,15))
					task.wait()
				end
				BBG:destroy()
			end)
		end)()
	--else
	--	Chat2(text)
	--end
end

function sphereMK3(bonuspeed,FastSpeed,type,pos,x1,y1,z1,value,color,color3,outerpos)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.Color = color3
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*outerpos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Sphere"
rngm.Scale = vt(x1,y1,z1)
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
local scaler2 = 1
local speeder = FastSpeed
if type == "Add" then
scaler2 = 1*value
elseif type == "Divide" then
scaler2 = 1/value
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
end
if chaosmode == true then
rng.BrickColor = BrickColor.random()
end
speeder = speeder - 0.01*FastSpeed*bonuspeed
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*speeder*bonuspeed
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2*bonuspeed, 0)
end
rng:Destroy()
end))
end

function sphereMK2(bonuspeed,FastSpeed,type,pos,x1,y1,z1,value,color,color3,outerpos)
local type = type
local rng = Instance.new("Part", char)
        rng.Anchored = true
        rng.BrickColor = color
        rng.Color = color3
        rng.CanCollide = false
        rng.FormFactor = 3
        rng.Name = "Ring"
        rng.Material = "Neon"
        rng.Size = Vector3.new(1, 1, 1)
        rng.Transparency = 0
        rng.TopSurface = 0
        rng.BottomSurface = 0
        rng.CFrame = pos
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*outerpos
        local rngm = Instance.new("SpecialMesh", rng)
        rngm.MeshType = "Sphere"
rngm.Scale = vt(x1,y1,z1)
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
local scaler2 = 1
local speeder = FastSpeed
if type == "Add" then
scaler2 = 1*value
elseif type == "Divide" then
scaler2 = 1/value
end
coroutine.resume(coroutine.create(function()
for i = 0,10/bonuspeed,0.1 do
task.wait()
if rainbowmode == true then
rng.Color = Color3.new(r/255,g/255,b/255)
end
if type == "Add" then
scaler2 = scaler2 - 0.01*value/bonuspeed
elseif type == "Divide" then
scaler2 = scaler2 - 0.01/value*bonuspeed
end
if chaosmode == true then
rng.BrickColor = BrickColor.random()
end
speeder = speeder - 0.01*FastSpeed*bonuspeed
rng.CFrame = rng.CFrame + rng.CFrame.lookVector*speeder*bonuspeed
rng.Transparency = rng.Transparency + 0.01*bonuspeed
rngm.Scale = rngm.Scale + Vector3.new(scaler2*bonuspeed, scaler2*bonuspeed, 0)
end
rng:Destroy()
end))
end

	
	
	function RandomMaterial()
    local getRandom;
    local material;
    local function IsTerrainMaterial(mat)
        local isMaterial = pcall(function() workspace:FindFirstChildOfClass'Terrain':GetMaterialColor(mat) end)
        return isMaterial
    end
    getRandom = function()
        local mat = Enum.Material:GetEnumItems()[math.random(1,#Enum.Material:GetEnumItems())]
        if(not IsTerrainMaterial(mat))then material = mat else getRandom() end
    end
    getRandom()
    repeat wait() until material
    return material
	end
	

function RandomCaps(str)
    local new = ""
    for i = 1, #str do
        if(math.random(1,2) == 1)then
            new = new .. (str:sub(i,i):upper())
        else
            new = new .. str:sub(i,i)
        end
    end
    return new
end
 
function sphereMKCharge(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos)
	local type = type
	local rng = Instance.new("Part", char)
	rng.Anchored = true
	rng.BrickColor = color
	rng.CanCollide = false
	rng.FormFactor = 3
	rng.Name = "Ring"
	rng.Material = "Neon"
	rng.Size = Vector3.new(1, 1, 1)
	rng.Transparency = 1
	rng.TopSurface = 0
	rng.BottomSurface = 0
	rng.CFrame = pos
	rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
	local rngm = Instance.new("SpecialMesh", rng)
	rngm.MeshType = "Sphere"
	rngm.Scale = vt(x1, y1, z1)
	if rainbowmode == true then
		rng.Color = Color3.new(r / 255, g / 255, b / 255)
	end
	local scaler2 = 1
	local speeder = FastSpeed
	if type == "Add" then
		scaler2 = 1 * value
	elseif type == "Divide" then
		scaler2 = 1 / value
	end
	coroutine.resume(coroutine.create(function()
		for i = 0, 10 / bonuspeed, 0.1 do
			task.wait()
			if rainbowmode == true then
				rng.Color = Color3.new(r / 255, g / 255, b / 255)
			end
			if type == "Add" then
				scaler2 = scaler2 - 0.01 * value / bonuspeed
			elseif type == "Divide" then
				scaler2 = scaler2 - 0.01 / value * bonuspeed
			end
			if chaosmode == true or insanitymode == true then
				rng.BrickColor = BrickColor.random()
			end
			speeder = speeder - 0.01 * FastSpeed * bonuspeed
			rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
			rng.Transparency = rng.Transparency - 0.01 * bonuspeed
			rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
		end
		rng:Destroy()
	end))
	end
	
function Eviscerate(dude)
	if dude.Name ~= char then
		local bgf = IT("BodyGyro", dude.Head)
		bgf.CFrame = bgf.CFrame * CFrame.fromEulerAnglesXYZ(Rad(-90), 0, 0)
		local val = IT("BoolValue", dude)
		val.Name = "IsHit"
		local ds = coroutine.wrap(function()
			dude:WaitForChild("Head"):BreakJoints()
			wait(0.5)
			target = nil
			coroutine.resume(coroutine.create(function()
				for i, v in pairs(dude:GetChildren()) do
					if v:IsA("Accessory") then
						v:Destroy()
					end
					if v:IsA("Humanoid") then
						v:Destroy()
					end
					if v:IsA("CharacterMesh") then
						v:Destroy()
					end
					if v:IsA("Model") then
						v:Destroy()
					end
					if v:IsA("Part") or v:IsA("MeshPart") then
						for x, o in pairs(v:GetChildren()) do
							if o:IsA("Decal") then
								o:Destroy()
							end
						end
						coroutine.resume(coroutine.create(function()
							v.Material = "Granite"
							v.CanCollide = false
							local PartEmmit1 = IT("ParticleEmitter", v)
							PartEmmit1.LightEmission = 1
							PartEmmit1.Texture = "rbxassetid://284205403"
							PartEmmit1.Color = ColorSequence.new(MAINRUINCOLOR.Color)
							PartEmmit1.Rate = 150
							PartEmmit1.Lifetime = NumberRange.new(1)
							PartEmmit1.Size = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0.75, 0),
								NumberSequenceKeypoint.new(1, 0, 0)
							})
							PartEmmit1.Transparency = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0, 0),
								NumberSequenceKeypoint.new(1, 1, 0)
							})
							PartEmmit1.Speed = NumberRange.new(0, 0)
							PartEmmit1.VelocitySpread = 30000
							PartEmmit1.Rotation = NumberRange.new(-500, 500)
							PartEmmit1.RotSpeed = NumberRange.new(-500, 500)
							local BodPoss = IT("BodyPosition", v)
							BodPoss.P = 3000
							BodPoss.D = 1000
							BodPoss.maxForce = Vector3.new(50000000000, 50000000000, 50000000000)
							BodPoss.position = v.Position + Vector3.new(Mrandom(-15, 15), Mrandom(-15, 15), Mrandom(-15, 15))
							v.Color = MAINRUINCOLOR.Color
							coroutine.resume(coroutine.create(function()
								for i = 0, 49 do
									task.wait(1)
									v.Transparency = v.Transparency + 0.08
								end
								wait(0.5)
								PartEmmit1.Enabled = false
								wait(3)
								v:Destroy()
								dude:Destroy()
							end))
						end))
					end
				end
			end))
		end)
		ds()
	end
end
	
function dmg(dude)
	if dude.Name ~= Character then
		local bgf = Instance.new("BodyGyro", dude.Head)
		bgf.CFrame = bgf.CFrame * CFrame.fromEulerAnglesXYZ(math.rad(-90), 0, 0)
		local val = Instance.new("BoolValue", dude)
		val.Name = "IsHit"
		local ds = coroutine.wrap(function()
			dude:WaitForChild("Head"):BreakJoints()
			wait(0.5)
			targetted = nil
			CFuncs.Sound.Create("rbxassetid://2487119609", char, 1, 2)
			coroutine.resume(coroutine.create(function()
				for i, v in pairs(dude:GetChildren()) do
					if v:IsA("Accessory") then
						v:Destroy()
					end
					if v:IsA("Humanoid") then
						v:Destroy()
					end
					if v:IsA("CharacterMesh") then
						v:Destroy()
					end
					if v:IsA("Model") then
						v:Destroy()
					end
					if v:IsA("Part") or v:IsA("MeshPart") then
						for x, o in pairs(v:GetChildren()) do
							if o:IsA("Decal") then
								o:Destroy()
							end
						end
						coroutine.resume(coroutine.create(function()
							v.Material = "Neon"
							v.CanCollide = false
							local bld = Instance.new("ParticleEmitter", v)
							bld.LightEmission = 1
							bld.Texture = "rbxassetid://0"
							bld.Color = ColorSequence.new(Color3.new(1, 1, 1))
							bld.Rate = 50
							bld.Lifetime = NumberRange.new(1)
							bld.Size = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0.75, 0),
								NumberSequenceKeypoint.new(1, 0, 0)
							})
							bld.Transparency = NumberSequence.new({
								NumberSequenceKeypoint.new(0, 0, 0),
								NumberSequenceKeypoint.new(1, 1, 0)
							})
							bld.Speed = NumberRange.new(0, 0)
							bld.VelocitySpread = 50000
							bld.Rotation = NumberRange.new(-500, 500)
							bld.RotSpeed = NumberRange.new(-500, 500)
							local sbs = Instance.new("BodyPosition", v)
							sbs.P = 3000
							sbs.D = 1000
							sbs.maxForce = Vector3.new(50000000000, 50000000000, 50000000000)
							sbs.position = v.Position + Vector3.new(math.random(-5, 5), math.random(-5, 5), math.random(-5, 5))
							v.Color = Color3.new(1, 1, 1)
							coroutine.resume(coroutine.create(function()
								for i = 0, 49 do
									task.wait(1)
									v.Transparency = v.Transparency + 0.02
								end
								CFuncs.Sound.Create("rbxassetid://0", v, 0.25, 1)
								bld.Speed = NumberRange.new(1, 5)
								bld.Acceleration = vt(0, 10, 0)
								wait(0.5)
								bld.Enabled = false
								wait(3)
								v:Destroy()
								dude:Destroy()
							end))
						end))
					end
				end
			end))
		end)
		ds()
	end
end
function FindNearestHead(Position, Distance, SinglePlayer)
	if SinglePlayer then
		return Distance > (SinglePlayer.Torso.CFrame.p - Position).magnitude
	end
	local List = {}
	for i, v in pairs(workspace:GetChildren()) do
		if v:IsA("Model") and v:findFirstChild("Head") and v ~= Character and Distance >= (v.Head.Position - Position).magnitude then
			table.insert(List, v)
		end
	end
	return List
end


function FindNearestTorso(Position, Distance, SinglePlayer)
	if SinglePlayer then
		return (SinglePlayer.Torso.CFrame.p - Position).magnitude < Distance
	end
	local List = {}
	for i, v in pairs(workspace:GetChildren()) do
		if v:IsA("Model") then
			if v:findFirstChild("Torso") or v:findFirstChild("UpperTorso") then
				if v ~= Character then
					if (v.Head.Position - Position).magnitude <= Distance then
						table.insert(List, v)
					end 
				end 
			end 
		end 
	end
	return List
end

function SphereAura(bonuspeed, FastSpeed, type, pos, x1, y1, z1, value, color, outerpos)
    local type = type
    local rng = Instance.new("Part", char)
    rng.Anchored = true
    rng.BrickColor = color
    rng.CanCollide = false
    rng.FormFactor = 3
    rng.Name = "Ring"
    rng.Material = "Neon"
    rng.Size = Vector3.new(1, 1, 1)
    rng.Transparency = 0
    rng.TopSurface = 0
    rng.BottomSurface = 0
    rng.CFrame = pos
    rng.CFrame = rng.CFrame + rng.CFrame.lookVector * outerpos
    local rngm = Instance.new("SpecialMesh", rng)
    rngm.MeshType = "Sphere"
    rngm.Scale = Vector3.new(x1, y1, z1)
    local scaler2 = 1
    local speeder = FastSpeed
    if type == "Add" then
        scaler2 = 1 * value
    elseif type == "Divide" then
        scaler2 = 1 / value
    end
    coroutine.resume(coroutine.create(function()
        for i = 0, 10 / bonuspeed, 0.1 do
            task.wait()
            if type == "Add" then
                scaler2 = scaler2 - 0.01 * value / bonuspeed
            elseif type == "Divide" then
                scaler2 = scaler2 - 0.01 / value * bonuspeed
            end
                        rng.BrickColor = BrickColor.random()
            speeder = speeder - 0.01 * FastSpeed * bonuspeed
            rng.CFrame = rng.CFrame + rng.CFrame.lookVector * speeder * bonuspeed
            rng.Transparency = rng.Transparency + 0.01 * bonuspeed
            rngm.Scale = rngm.Scale + Vector3.new(scaler2 * bonuspeed, scaler2 * bonuspeed, 0)
        end
        rng:Destroy()
    end))
end

function SoulSteal(dude)
if dude.Name ~= char then
local bgf = IT("BodyGyro", dude.Head)
bgf.CFrame = bgf.CFrame * CFrame.fromEulerAnglesXYZ(Rad(-90), 0, 0)
local val = IT("BoolValue", dude)
val.Name = "IsHit"
local torso = (dude:FindFirstChild'Head' or dude:FindFirstChild'Torso' or dude:FindFirstChild'UpperTorso' or dude:FindFirstChild'LowerTorso' or dude:FindFirstChild'HumanoidRootPart')
local soulst = coroutine.wrap(function()
local soul = Instance.new("Part",dude)
soul.Size = Vector3.new(1,1,1)
soul.CanCollide = false
soul.Anchored = false
soul.Position = torso.Position
soul.Transparency = 1
local PartEmmit1 = IT("ParticleEmitter", soul)
PartEmmit1.LightEmission = 1
PartEmmit1.Texture = "rbxassetid://569507414"
PartEmmit1.Color = ColorSequence.new(maincolor.Color)
PartEmmit1.Rate = 250
PartEmmit1.Lifetime = NumberRange.new(1.6)
PartEmmit1.Size = NumberSequence.new({
    NumberSequenceKeypoint.new(0, 1, 0),
    NumberSequenceKeypoint.new(1, 0, 0)
})
PartEmmit1.Transparency = NumberSequence.new({
    NumberSequenceKeypoint.new(0, 0, 0),
    NumberSequenceKeypoint.new(1, 1, 0)
})
PartEmmit1.Speed = NumberRange.new(0, 0)
PartEmmit1.VelocitySpread = 30000
PartEmmit1.Rotation = NumberRange.new(-360, 360)
PartEmmit1.RotSpeed = NumberRange.new(-360, 360)
local BodPoss = IT("BodyPosition", soul)
BodPoss.P = 3000
BodPoss.D = 1000
BodPoss.maxForce = Vector3.new(50000000000, 50000000000, 50000000000)
BodPoss.position = torso.Position + Vector3.new(Mrandom(-15, 15), Mrandom(-15, 15), Mrandom(-15, 15))
wait(1.6)
soul.Touched:connect(function(hit)
    if hit.Parent == char then
    soul:Destroy()
    end
end)
wait(1.2)
while soul do
    task.wait()
    PartEmmit1.Color = ColorSequence.new(maincolor.Color)
    BodPoss.Position = tors.Position
end
end)
    soulst()
    end
end


--Face Mouse
function FaceMouse()
	Cam = workspace.CurrentCamera
	return {
		CFrame.new(char.Torso.Position, Vector3.new(mouse.Hit.p.x, char.Torso.Position.y, mouse.Hit.p.z)),
		Vector3.new(mouse.Hit.p.x, mouse.Hit.p.y, mouse.Hit.p.z)
	}
end
function FaceMouse2()
	Cam = workspace.CurrentCamera
	return {
		CFrame.new(char.Torso.Position, Vector3.new(mouse.Hit.p.x, mouse.Hit.p.y, mouse.Hit.p.z)),
		Vector3.new(mouse.Hit.p.x, mouse.Hit.p.y, mouse.Hit.p.z)
	}
end
--
local ModeOfGlitch = 1 -- ModeOfGlitch
local storehumanoidWS = 16 --Walkspeed
function ExtinctiveHeartbreak()
	local targetted
	if mouse.Target.Parent ~= Character and mouse.Target.Parent.Parent ~= Character and mouse.Target.Parent:FindFirstChildOfClass("Humanoid") ~= nil then
		targetted = mouse.Target.Parent
	end
	if targetted ~= nil then
		attack = true
		CFuncs.Sound.Create("rbxassetid://847061203", root, 2.5, 1)
		for i = 0, 9 do
			sphereMK(3, 0.25, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 1, 1, 10, -0.01, BrickColor.new("Really black"), 0)
		end
		sphere(3, "Add", root.CFrame, vt(0, 0, 0), 0.25, BrickColor.new("Really black"))
		local originalpos = root.CFrame
		RootPart.CFrame = targetted.Head.CFrame * CFrame.new(0, -2, 2)
		for i = 0, 9 do
			sphereMK(3, 0.25, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 1, 1, 10, -0.01, BrickColor.new("Really black"), 0)
		end
		hum.WalkSpeed = 0
		targetted.Head.Anchored = true
		sphere(3, "Add", root.CFrame, vt(0, 0, 0), 0.25, BrickColor.new("Really black"))
		for i = 0, 2, 0.1 do
			task.wait()
			RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0)), 0.4)
			LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0)), 0.4)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.05 * math.cos(sine / 28)) * angles(math.rad(0), math.rad(0), math.rad(80)), 0.4)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(10)), 0.8)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5 + 0.1 * math.cos(sine / 28), 0) * angles(math.rad(20), math.rad(0), math.rad(10)), 0.4)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5 + 0.1 * math.cos(sine / 28), 0) * angles(math.rad(90), math.rad(0), math.rad(60)), 0.4)
		end
		coroutine.resume(coroutine.create(function()
			bld = Instance.new("ParticleEmitter", targetted:WaitForChild("Torso"))
			bld.LightEmission = 0.1
			bld.Texture = "rbxassetid://0"
			bld.Color = ColorSequence.new(Color3.new(0.5, 0, 0))
			bld.Rate = 500
			bld.Lifetime = NumberRange.new(1)
			bld.Size = NumberSequence.new({
				NumberSequenceKeypoint.new(0, 2, 0),
				NumberSequenceKeypoint.new(1, 0, 0)
			})
			bld.Acceleration = vt(0, -25, 0)
			bld.Transparency = NumberSequence.new({
				NumberSequenceKeypoint.new(0, 0, 0),
				NumberSequenceKeypoint.new(1, 0, 0)
			})
			bld.Speed = NumberRange.new(10, 50)
			bld.EmissionDirection = "Front"
			bld.VelocitySpread = 25
			bld.Rotation = NumberRange.new(-500, 500)
			bld.RotSpeed = NumberRange.new(-500, 500)
		end))
		coroutine.resume(coroutine.create(function()
			bld = Instance.new("ParticleEmitter", targetted:WaitForChild("UpperTorso"))
			bld.LightEmission = 0.1
			bld.Texture = "rbxassetid://0"
			bld.Color = ColorSequence.new(Color3.new(0.5, 0, 0))
			bld.Rate = 500
			bld.Lifetime = NumberRange.new(1)
			bld.Size = NumberSequence.new({
				NumberSequenceKeypoint.new(0, 2, 0),
				NumberSequenceKeypoint.new(1, 0, 0)
			})
			bld.Acceleration = vt(0, -25, 0)
			bld.Transparency = NumberSequence.new({
				NumberSequenceKeypoint.new(0, 0, 0),
				NumberSequenceKeypoint.new(1, 0, 0)
			})
			bld.Speed = NumberRange.new(10, 50)
			bld.EmissionDirection = "Front"
			bld.VelocitySpread = 25
			bld.Rotation = NumberRange.new(-500, 500)
			bld.RotSpeed = NumberRange.new(-500, 500)
		end))
CamShakeAll(50,58,Character)
		game:GetService("Debris"):AddItem(bld, 3)
		dmg(targetted)
		CFuncs.Sound.Create("rbxassetid://429400881", targetted.Head, 1, 1)
		for i = 0, 1, 0.1 do
			task.wait()
			RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0)), 0.8)
			LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0)), 0.8)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0.25, 0 + 0.05 * math.cos(sine / 28)) * angles(math.rad(0), math.rad(0), math.rad(-80)), 0.8)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(80)), 0.8)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5 + 0.1 * math.cos(sine / 28), 0) * angles(math.rad(20), math.rad(0), math.rad(10)), 0.8)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5 + 0.1 * math.cos(sine / 28), 0) * angles(math.rad(90), math.rad(0), math.rad(-80)), 0.8)
		end
		CFuncs.Sound.Create("rbxassetid://847061203", root, 2.5, 1)
		for i = 0, 9 do
			sphereMK(3, 0.25, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 1, 1, 10, -0.01, BrickColor.new("Really black"), 0)
		end
		sphere(3, "Add", root.CFrame, vt(0, 0, 0), 0.25, BrickColor.new("Really black"))
		root.CFrame = originalpos
		for i = 0, 9 do
			sphereMK(3, 0.25, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 1, 1, 10, -0.01, BrickColor.new("Really black"), 0)
		end
		sphere(3, "Add", root.CFrame, vt(0, 0, 0), 0.25, BrickColor.new("Really black"))
		bld.Enabled = false
		attack = false
		hum.WalkSpeed = storehumanoidWS
	end
end
function PureBomb()
	attack = true
	local orb = Instance.new("Part", char)
	orb.Anchored = true
	orb.BrickColor = BrickColor.new("Toothpaste")
	orb.CanCollide = false
	orb.FormFactor = 3
	orb.Name = "Ring"
	orb.Material = "Neon"
	orb.Size = Vector3.new(1, 1, 1)
	orb.Transparency = 0
	orb.TopSurface = 0
	orb.BottomSurface = 0
	local orbm = Instance.new("SpecialMesh", orb)
	orbm.MeshType = "Sphere"
	orbm.Name = "SizeMesh"
	orbm.Scale = vt(0, 0, 0)
	local scaled = 0.1
	local posid = 0
	CFuncs.Sound.Create("rbxassetid://136007472", orb, 1, 1)
	for i = 0, 5, 0.1 do
		task.wait()
		scaled = scaled - 0.001
		posid = posid - scaled
		orb.CFrame = rarm.CFrame * CFrame.new(0, -0.1 + posid / 1.05, 0)
		orbm.Scale = orbm.Scale + vt(scaled, scaled, scaled)
		sphereMKCharge(5, -0.25, "Add", orb.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 0.5, 0.5, 5, -0.005, BrickColor.new("Toothpaste"), 10)
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(-2 - 1 * math.cos(sine / 32))), 0.1)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-3 + 1 * math.cos(sine / 32)), math.rad(0), math.rad(-10)), 0.1)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.1 * math.cos(sine / 32)) * angles(math.rad(0), math.rad(0), math.rad(0)), 0.1)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(0)), 0.1)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(180), math.rad(20), math.rad(0)), 0.1)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(-30 + 5 * math.cos(sine / 30)), math.rad(-20)), 0.1)
	end
	for i = 0, 2, 0.1 do
		task.wait()
		orb.CFrame = rarm.CFrame * CFrame.new(0, -0.1 + posid / 1.05, 0)
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(-2 - 1 * math.cos(sine / 32))), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-3 + 1 * math.cos(sine / 32)), math.rad(0), math.rad(-10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.1 * math.cos(sine / 32)) * angles(math.rad(0), math.rad(0), math.rad(-50)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(20)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(220), math.rad(20), math.rad(0)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(-30 + 5 * math.cos(sine / 30)), math.rad(-20)), 0.4)
	end
	coroutine.resume(coroutine.create(function()
		orb.Anchored = false
		CFuncs.Sound.Create("rbxassetid://260433768", root, 1.25, 1)
		local a = Instance.new("Part", workspace)
		a.Name = "Direction"
		a.Anchored = true
		a.BrickColor = bc("Bright red")
		a.Material = "Neon"
		a.Transparency = 1
		a.CanCollide = false
		local ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 500)
		local ignore = orb
		local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
		a.BottomSurface = 10
		a.TopSurface = 10
		local distance = (orb.CFrame.p - position).magnitude
		a.Size = Vector3.new(0.1, 0.1, 0.1)
		a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, 0)
		orb.CFrame = a.CFrame
		a:Destroy()
		local bv = Instance.new("BodyVelocity")
		bv.maxForce = Vector3.new(1000000000, 1000000000, 1000000000)
		bv.velocity = orb.CFrame.lookVector * 125
		bv.Parent = orb
		local hitted = false
		game:GetService("Debris"):AddItem(orb, 15)
		wait()
		local hit = orb.Touched:connect(function(hit)
			if hitted == false then
				hitted = true
CamShakeAll(42,44,Character)
				CFuncs.Sound.Create("rbxassetid://151304356", orb, 5, 1)
				MagniDamage(orb, 65, 65, 90, 0, "Normal")
				sphere(1, "Add", orb.CFrame, vt(orbm.Scale.x, orbm.Scale.y, orbm.Scale.z), 1, BrickColor.new("Toothpaste"))
				sphere(2, "Add", orb.CFrame, vt(orbm.Scale.x, orbm.Scale.y, orbm.Scale.z), 2, BrickColor.new("Toothpaste"))
				for i = 0, 9 do
					sphereMK(1, 2.5, "Add", orb.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 5, 5, 50, -0.05, BrickColor.new("Toothpaste"), 0)
					sphereMK(2, 5, "Add", orb.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 5, 5, 50, -0.05, BrickColor.new("Toothpaste"), 0)
				end
				orb.Anchored = true
				orb.Transparency = 1
				wait(8)
				orb:Destroy()
			end
		end)
	end))
	for i = 0, 1, 0.1 do
		task.wait()
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(-2 - 1 * math.cos(sine / 32))), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.1 * math.cos(sine / 32), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-3 + 1 * math.cos(sine / 32)), math.rad(0), math.rad(-10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.1 * math.cos(sine / 32)) * angles(math.rad(0), math.rad(0), math.rad(50)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(-50)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(60), math.rad(20), math.rad(50)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(-30 + 5 * math.cos(sine / 30)), math.rad(-20)), 0.4)
	end
	attack = false
end



function Fanta()
attack = true
hum.WalkSpeed = 0
bosschatfunc("HAHAHAHA!...",MAINRUINCOLOR.Color,2) -- AHAH SO FUNNY! xddd
CFuncs["Sound"].Create("rbxassetid://165487479", char, 50,0.5)
for i = 0, 9, 0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1, -1 - 0.025 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
LH.C0=clerp(LH.C0,cf(-1, -1 - 0.05 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(-83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0, 0, 0 + 0.05 * math.cos(sine / 12))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(-30 - 2.5 * Sin(sine / 2)), Rad(0), Rad(0)), 0.3)
RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 2), 0.025 * Cos(sine / 2)) * angles(Rad(-35 - 7.5 * Sin(sine / 2)), Rad(0), Rad(15 - 7.5 * Sin(sine / 2))), 0.1)
LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 2), 0.025 * Cos(sine / 2)) * angles(Rad(-35 - 7.5 * Sin(sine / 2)), Rad(0), Rad(-15 - 7.5 * Sin(sine / 2))), 0.1)
end
hum.WalkSpeed = storehumanoidWS
attack = false
end



function ChaosGroundStrikeop()
attack = true
CFuncs["Sound"].Create("rbxassetid://438666141", root, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://1208650519", root, 7.5, 1)
CameraEnshaking(4,12)
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 52.5)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
sphere(5,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(0,0,0),1,BrickColor.random())
sphere(10,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(0,0,0),2,BrickColor.random())
sphere(1,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(100,0.1,100),0.01,BrickColor.random())
attack = false
end


function ChaosBegoneOP()
attack = true
local speedearn = 0
CFuncs["Sound"].Create("rbxassetid://1208650519", char, 10, 0.75)
CFuncs["Sound"].Create("rbxassetid://438666141", char, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://1208650519", char, 7.5, 1)
CameraEnshaking(5,25)
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 1234567890)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
sphere(5,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(0,0,0),1*1000,BrickColor.random())
sphere(10,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(0,0,0),2*1000,BrickColor.random())
sphere(1,"Add",root.CFrame*CFrame.new(0,-2.9,0),vt(100*1000,0.1,100*1000),0.01,BrickColor.random())
attack = false
end


function annihilation3()
attack = true
hum.WalkSpeed = 0
for i = 0, 3, 0.1 do
task.wait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(40)),0.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-10),math.rad(0),math.rad(-40)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(10)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(6), math.rad(20), math.rad(-10)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(-20),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(0)),.3)
end
local cent = CreateParta(char,1,1,"Neon",MRCL)
cent.CFrame = root.CFrame*CFrame.new(math.random(-6,6),math.random(3,9),math.random(-6,6))
shakes(0.5,1)
	local lva = 1
	local ica = 0
local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    cent.CFrame.p,                           -- origin
	    (mouse.Hit.p - cent.CFrame.p).unit * 500 -- direction
	) 
	local ignore = cent
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (cent.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(cent.CFrame.p, position) * CFrame.new(0, 0, 0)
cent.CFrame = a.CFrame
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(10, 10, 10)
bv.velocity = cent.CFrame.lookVector*0
bv.Parent = cent
game:GetService("Debris"):AddItem(cent, 20)
local hitted = false
coroutine.resume(coroutine.create(function()
	while true do
		task.wait(1)
		if hitted == false and cent.Parent ~= nil then
	ica = ica + 4*lva
	lva = lva + 0.01
	bv.velocity = cent.CFrame.lookVector*ica
	sphere2(3,"Add",cent.CFrame,vt(5,5,5),-0.05,-0.05,-0.05,BrickColor.new("Really blue"))
	sphere2(5,"Add",cent.CFrame*CFrame.Angles(0,0,math.rad(ica))*CFrame.new(0,-5,0),vt(4,4,4),-0.04,-0.04,-0.04,BrickColor.new("Really blue"))
	sphere2(5,"Add",cent.CFrame*CFrame.Angles(0,0,math.rad(ica))*CFrame.new(0,5,0),vt(4,4,4),-0.04,-0.04,-0.04,BrickColor.new("Really red"))
		elseif hitted == true or cent.Parent == nil then
			break
		end
	end
end))
--[[local e = script.redness:Clone()
e.Parent = game:GetService("Lighting")]]--
coroutine.resume(coroutine.create(function()
cent.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
	cent.Anchored = true
	CFuncs["Sound"].Create("rbxassetid://782353443", cent, 10, 1)
	CFuncs["Sound"].Create("rbxassetid://1368637781", cent, 8, 1)
	CFuncs["Sound"].Create("rbxassetid://763717897", cent, 5, 1)
	CFuncs["EchoSound"].Create("rbxassetid://1177785010", cent, 8, 1.1,0,10,0.15,0.5,1)
	MagniDamage(cent, 150, 50,99999, 0, "Normal")
	sphere2(2,"Add",cent.CFrame,vt(3,3,3),1,1,1,BrickColor.new("Really blue"),BrickColor.new("Really blue").Color)
	sphere2(3,"Add",cent.CFrame,vt(3,3,3),1.2,1.2,1.2,BrickColor.new("Really red"),BrickColor.new("Really red").Color)
	for i = 0, 99 do
	sphere2(2,"Add",cent.CFrame,vt(3,3,3),1,1,1,BrickColor.new("Really blue"),BrickColor.new("Really blue").Color)
	sphere2(3,"Add",cent.CFrame,vt(3,3,3),1.2,1.2,1.2,BrickColor.new("Really red"),BrickColor.new("Really red").Color)
		slash(math.random(10,50)/10,5,true,"Round","Add","Out",cent.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.02,0.02,0.02),math.random(200,400)/250,BrickColor.new("Really blue"))
		slash(math.random(10,50)/10,5,true,"Round","Add","Out",cent.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.02,0.02,0.01),math.random(150,300)/250,BrickColor.new("Really red"))
	end
CFuncs["Sound"].Create("rbxassetid://763717897", cent, 3, 0.5)
CFuncs["Sound"].Create("rbxassetid://239000203", cent, 3, 0.9)
CFuncs["Sound"].Create("rbxassetid://1192402877", cent, 2,0.75)
CFuncs["Sound"].Create("rbxassetid://1664711478", cent, 2,1)
CFuncs["Sound"].Create("rbxassetid://763718160", cent, 2, 0.75)
	coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",cent)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(BrickColor.new("Really red").Color)
eff.Rate = 1000000000
eff.Enabled = true
--eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(5)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.1,40,0),NumberSequenceKeypoint.new(0.8,60,0),NumberSequenceKeypoint.new(1,80,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(350)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
local eff2 = eff:Clone()
eff2.Parent = cent
eff2.Speed = NumberRange.new(250) 
eff2.Color = ColorSequence.new(BrickColor.new("Bright green").Color)
wait(0.2)
eff.Enabled = false
eff2.Enabled = false
	end))
end
shakes(3,3)
end)
end))
--e:Destroy()
attack = false
hum.WalkSpeed = storehumanoidWS
end


function shdnontwist()
attack = true
hum.WalkSpeed = 2
CFuncs["Sound"].Create("rbxassetid://136007472", rarm, 1.5,1.25)
local obj1 = Instance.new("Part")
obj1.Parent = char
obj1.Transparency = 1
obj1.Size = vt(1,1,1)
obj1.Color = BrickColor.new("Alder").Color
	local mesh = Instance.new("SpecialMesh",obj1)
	mesh.MeshType = Enum.MeshType.FileMesh
	mesh.MeshId = "rbxassetid://432993411"
local obj2 =  Instance.new("Part")
obj2.Parent = char
obj2.Transparency = 1
obj2.Size = vt(1,1,1)
obj2.Color = MRCL.Color
	local mesh = Instance.new("SpecialMesh",obj2)
	mesh.MeshType = Enum.MeshType.FileMesh
	mesh.MeshId = "rbxassetid://991320318"
local cfor = CreateParta(char,1,1,"Neon",MRCL)
cfor.Anchored = true
cfor.CFrame = obj2.CFrame
local cef = Instance.new("ParticleEmitter",cfor)
cef.Texture = "rbxassetid://2344870656"
cef.LightEmission = 1
cef.Color = ColorSequence.new(obj2.Color)
cef.Rate = 150
cef.Lifetime = NumberRange.new(0.25)
cef.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.5,1,0),NumberSequenceKeypoint.new(1,0,0)})
cef.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
cef.Speed = NumberRange.new(0)
local rval = 0
local eval = 1
for i = 0,7,0.1 do
task.wait()
rval = rval + math.random(30,40)
eval = eval + 0.45
obj1.Transparency = obj1.Transparency - 0.005
obj1.Size = obj1.Size + vt(0.3,0.3,0.1)
obj1.CFrame = root.CFrame*CFrame.new(0,1,-5)*CFrame.Angles(math.rad(0),math.rad(0),math.rad(rval))
obj2.Transparency = obj2.Transparency - 0.007
obj2.Size = obj2.Size + vt(0.15,0.15,0.15)
cef.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.5,eval,0),NumberSequenceKeypoint.new(1,0,0)})
obj2.CFrame = root.CFrame*CFrame.new(0,1,-7)*CFrame.Angles(math.rad(rval),math.rad(rval),math.rad(-rval))
cfor.CFrame = obj2.CFrame
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Pastel light blue"),BrickColor.new("Pastel light blue").Color)
sphere2(10,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.15,-0.01,BrickColor.new("Pink"),BrickColor.new("Pink").Color)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 32))),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 2 * math.cos(sine / 32))),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),1 + 0.15 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(-50)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 2 * math.cos(sine / 37)),math.rad(10 + 1 * math.cos(sine / 58)),math.rad(50 + 2 * math.cos(sine / 53))),.3)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(10 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(5 + 2 * math.cos(sine / 45))),.3)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(90 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(-50 - 4 * math.cos(sine / 45))),.3)
end
shakes(0.25,0.25)
cef.Enabled = false
coroutine.resume(coroutine.create(function()
for i = 0,49 do
task.wait()
rval = rval + 100
obj2.CFrame = obj2.CFrame*CFrame.Angles(math.rad(rval),math.rad(rval),math.rad(-rval))
obj2.Transparency = obj2.Transparency + 0.02
obj2.Size = obj2.Size + vt(5,5,5)
obj1.Transparency = obj1.Transparency + 0.02
obj1.Size = obj1.Size + vt(0,-0.5,-0.5)
end
obj1:Destroy()
obj2:Destroy()
cfor:Destroy()
end))
local lva = 1
local ica = 0
local cent = CreateParta(char,1,1,"Neon",MRCL)
CFuncs["Sound"].Create("rbxassetid://1177785010", cent, 10, 1)
cent.CFrame = root.CFrame*CFrame.Angles(0,0,0) + root.CFrame.lookVector*5
sphere2(2,"Add",cent.CFrame,vt(1,1,1),0.5,0.5,0.5,BrickColor.new("Pastel light blue"),BrickColor.new("Pastel light blue").Color)
sphere2(3,"Add",cent.CFrame,vt(1,1,1),0.5,0.5,0.5,BrickColor.new("Alder"),BrickColor.new("Alder").Color)

local a = Instance.new("Part",workspace)
a.Name = "Direction" 
a.Anchored = true
a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
a.CanCollide = false
local ray = Ray.new(
	cent.CFrame.p, -- origin
	(mouse.Hit.p - cent.CFrame.p).unit * 500 -- direction
	) 
local ignore = cent
local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
a.BottomSurface = 10
a.TopSurface = 10
local distance = (cent.CFrame.p - position).magnitude
a.Size = Vector3.new(0.1, 0.1, 0.1)
a.CFrame = CFrame.new(cent.CFrame.p, position) * CFrame.new(0, 0, 0)
cent.CFrame = a.CFrame
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = cent.CFrame.lookVector*0
bv.Parent = cent
game:GetService("Debris"):AddItem(cent, 20)
local hitted = false
coroutine.resume(coroutine.create(function()
while true do
task.wait(1)
if hitted == false and cent.Parent ~= nil then
ica = ica + 4*lva
lva = lva + 0.1
bv.velocity = cent.CFrame.lookVector*ica
sphere2(3,"Add",cent.CFrame,vt(5,5,5),-0.05,-0.05,-0.05,BrickColor.new("Pastel light blue"))
sphere2(3,"Add",cent.CFrame,vt(7,7,7),-0.05,-0.05,-0.05,BrickColor.new("Alder"))
elseif hitted == true or cent.Parent == nil then
break
end
end
end))
coroutine.resume(coroutine.create(function()
cent.Touched:connect(function(hit) 
if hitted == false and hit.Parent ~= char then
hitted = true
cent.Anchored = true
shakes(0.5,0.5)
CFuncs["Sound"].Create("rbxassetid://782353443", cent, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1368637781", cent, 8, 1)
CFuncs["EchoSound"].Create("rbxassetid://1177785010", cent, 8, 1.1,0,10,0.15,0.5,1)
RootPart.CFrame = cent.CFrame
sphere2(2,"Add",cent.CFrame,vt(1,1,1),1,1,1,BrickColor.new("Pastel light blue"),BrickColor.new("Pastel light blue").Color)
sphere2(3,"Add",cent.CFrame,vt(1,1,1),1.2,1.2,1.2,BrickColor.new("Alder"),BrickColor.new("Alder").Color)
for i = 0, 19 do
slash(math.random(10,50)/10,5,true,"Round","Add","Out",cent.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(200,400)/250,BrickColor.new("Pink"))
slash(math.random(10,50)/10,5,true,"Round","Add","Out",cent.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(150,300)/250,BrickColor.new("Pastel light blue"))
end
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",cent)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(BrickColor.new("Pastel light blue").Color)
eff.Rate = 10000000
eff.Enabled = true
--eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(5)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.1,40,0),NumberSequenceKeypoint.new(0.8,60,0),NumberSequenceKeypoint.new(1,80,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(350)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
local eff2 = eff:Clone()
eff2.Parent = cent
eff2.Speed = NumberRange.new(250) 
eff2.Color = ColorSequence.new(BrickColor.new("Pink").Color)
wait(0.2)
eff.Enabled = false
eff2.Enabled = false
end))
end
end)
end))
attack = false
hum.WalkSpeed = storehumanoidWS
end



function ChaosGroundStrike()
	attack = true
	for i = 0, 2, 0.1 do
		task.wait()
		RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(-20)), 0.2)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(20)), 0.2)
	end
	CFuncs.Sound.Create("rbxassetid://438666141", root, 7.5, 1)
	CFuncs.Sound.Create("rbxassetid://1208650519", root, 7.5, 1)
CamShakeAll(31,32,Character)
	for i, v in pairs(FindNearestHead(Torso.CFrame.p, 52.5)) do
		if v:FindFirstChild("Head") then
			dmg(v)
		end
	end
	sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
	sphere(10, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 2, BrickColor.random())
	sphere(1, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(100, 0.1, 100), 0.01, BrickColor.random())
	for i = 0, 2, 0.1 do
		task.wait()
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		RH.C0 = clerp(RH.C0, cf(1, -1, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(30)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(-30)), 0.4)
	end
	attack = false
end
function ChaosGroundStrike2()
	attack = true
    local valu = math.random(1,255)
    local coloru = Color3.fromRGB(valu,valu,valu)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = coloru end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = coloru end)
    MAINRUINCOLOR2 = BrickColor.new(coloru)
    local val = math.random(1,34)
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
	MAINRUINCOLOR = BrickColor.new(color)
	CFuncs.Sound.Create("rbxassetid://438666141", root, 7.5, 1)
	CFuncs.Sound.Create("rbxassetid://2487119609", root, 10, 1)
CamShakeAll(31,32,Character)
	for i, v in pairs(FindNearestHead(Torso.CFrame.p, 52.5)) do
		if v:FindFirstChild("Head") then
			dmg(v)
		end
	end
	sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, MAINRUINCOLOR)
	sphere(10, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 2, MAINRUINCOLOR2)
	sphere(1, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(100, 0.1, 100), 0.01, MAINRUINCOLOR)
	for i = 0, 2, 0.1 do
		task.wait()
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, MAINRUINCOLOR, 0)
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, MAINRUINCOLOR2, 0)
		RH.C0 = clerp(RH.C0, cf(1, -1, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(30)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(-30)), 0.4)
	end
	attack = false
end
function ChaosBegone()
	attack = true
	chatfunc("WHY WONT YOU PEOPLE...", BrickColor.random().Color)
	for i = 0, 10, 0.1 do
		task.wait()
		RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(-20)), 0.2)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(20)), 0.2)
	end
	chatfunc("DIE!!", BrickColor.random().Color)
	CFuncs.Sound.Create("rbxassetid://438666141", char, 7.5, 1)
	CFuncs.Sound.Create("rbxassetid://1208650519", char, 7.5, 1)
CamShakeAll(42,44,Character)
	for i, v in pairs(FindNearestHead(Torso.CFrame.p, 1234567890)) do
		if v:FindFirstChild("Head") then
			dmg(v)
		end
	end
	sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1000, BrickColor.random())
	sphere(10, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 2000, BrickColor.random())
	sphere(1, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(100000, 0.1, 100000), 0.01, BrickColor.random())
	for i = 0, 3, 0.1 do
		task.wait()
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-525, 525), -5, math.random(-525, 525)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-525, 525), -5, math.random(-525, 525)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-525, 525), -5, math.random(-525, 525)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		sphereMK(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-525, 525), -5, math.random(-525, 525)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		RH.C0 = clerp(RH.C0, cf(1, -1, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(30)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(-30)), 0.4)
	end
	attack = false
end
function orb_spawn_norm(positted, timer, color, MagniBoost, min, max, volEx, ShakePower, volSummon)
	local orb = Instance.new("Part", char)
	orb.Anchored = true
	orb.BrickColor = color
	orb.CanCollide = false
	orb.FormFactor = 3
	orb.Name = "Ring"
	orb.Material = "Neon"
	orb.Size = Vector3.new(1, 1, 1)
	orb.Transparency = 0
	orb.TopSurface = 0
	orb.BottomSurface = 0
	local orbm = Instance.new("SpecialMesh", orb)
	orbm.MeshType = "Sphere"
	orb.CFrame = positted
	orbm.Name = "SizeMesh"
	orbm.Scale = vt(1, 1, 1)
	CFuncs.Sound.Create("rbxassetid://183763506", orb, volSummon, 1)
	sphere(2.5, "Add", orb.CFrame, vt(1, 1, 1), 0.05, orb.BrickColor)
	coroutine.resume(coroutine.create(function()
		wait(timer)
CamShakeAll(42,44,Character)
		orb.Transparency = 1
		MagniDamage(orb, 3.5 * MagniBoost, min, max, 0, "Normal")
		sphere(5, "Add", orb.CFrame, vt(1, 1, 1), 0.1 * MagniBoost, orb.BrickColor)
		CFuncs.Sound.Create("rbxassetid://192410089", orb, volEx, 0.7)
		wait(3)
		orb:Destroy()
	end))
end
function orb_spawn(positted, timer)
	local randomcol = math.random(1, 2)
	local orb = Instance.new("Part", char)
	orb.Anchored = true
	if randomcol == 1 then
		orb.BrickColor = BrickColor.new("White")
	elseif randomcol == 2 then
		orb.BrickColor = BrickColor.new("Really black")
	end
	orb.CanCollide = false
	orb.FormFactor = 3
	orb.Name = "Ring"
	orb.Material = "Neon"
	orb.Size = Vector3.new(1, 1, 1)
	orb.Transparency = 0
	orb.TopSurface = 0
	orb.BottomSurface = 0
	local orbm = Instance.new("SpecialMesh", orb)
	orbm.MeshType = "Sphere"
	orb.CFrame = positted
	orbm.Name = "SizeMesh"
	orbm.Scale = vt(1, 1, 1)
	CFuncs.Sound.Create("rbxassetid://183763506", orb, 1.5, 1)
	sphere(2.5, "Add", orb.CFrame, vt(1, 1, 1), 0.025, orb.BrickColor)
	for i = 0, 2 do
		sphereMK(5, 0.15, "Add", orb.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 1.5, 1.5, 7.5, -0.015, orb.BrickColor, 0)
	end
	coroutine.resume(coroutine.create(function()
		wait(timer)
		CamShakeAll(42,44,Character)

		orb.Transparency = 1
		MagniDamage(orb, 17.5, 10, 50, 0, "Normal")
		sphere(5, "Add", orb.CFrame, vt(1, 1, 1), 0.5, orb.BrickColor)
		for i = 0, 4 do
			sphereMK(5, 0.65, "Add", orb.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 2.5, 2.5, 15, -0.025, orb.BrickColor, 0)
		end
		CFuncs.Sound.Create("rbxassetid://192410089", orb, 2, 0.7)
		wait(3)
		orb:Destroy()
	end))
	end
	
	

function balancedmode()
	attack = true
	Humanoid.WalkSpeed = 0
	newTheme("rbxassetid://2027652726",0,1,1.25)
	local orb = Instance.new("Part", char)
        orb.Anchored = true
        orb.BrickColor = BrickColor.new("Black")
        orb.CanCollide = false
        orb.FormFactor = 3
        orb.Name = "Ring"
        orb.Material = "Neon"
        orb.Size = Vector3.new(1, 1, 1)
        orb.Transparency = 0
        orb.TopSurface = 0
        orb.BottomSurface = 0
        local orbm = Instance.new("SpecialMesh", orb)
        orbm.MeshType = "Sphere"
orbm.Name = "SizeMesh"
orbm.Scale = vt(0,0,0)
	local orb2 = Instance.new("Part", char)
        orb2.Anchored = true
        orb2.BrickColor = BrickColor.new("White")
        orb2.CanCollide = false
        orb2.FormFactor = 3
        orb2.Name = "Ring"
        orb2.Material = "Neon"
        orb2.Size = Vector3.new(1, 1, 1)
        orb2.Transparency = 0
        orb2.TopSurface = 0
        orb2.BottomSurface = 0
        local orbm2 = Instance.new("SpecialMesh", orb2)
        orbm2.MeshType = "Sphere"
orbm2.Name = "SizeMesh"
orbm2.Scale = vt(0,0,0)
local scaled = 0.1
local posid = 0
local posid2 = 0
CFuncs["Sound"].Create("rbxassetid://136007472", orb, 1,1)
CFuncs["Sound"].Create("rbxassetid://136007472", orb2, 1,1)
	for i = 0, 5, 0.1 do
	task.wait()
	scaled = scaled - 0.001
	posid = posid - scaled
	orb.CFrame = larm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)
	orbm.Scale = orbm.Scale + vt(scaled,scaled,scaled)
	sphereMKCharge(5,-0.25,"Add",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.5,0.5,5,-0.005,BrickColor.new("Black"),10)
	PixelBlockNeg(2,1,"Add",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.01,BrickColor.new("Black"),0)

	orb2.CFrame = rarm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)
	orbm2.Scale = orbm2.Scale + vt(scaled,scaled,scaled)
	sphereMKCharge(5,-0.25,"Add",orb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.5,0.5,5,-0.005,BrickColor.new("White"),10)
	PixelBlockNeg(2,1,"Add",orb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.01,BrickColor.new("White"),0)


	RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
	LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
	RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
	Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(0)),.1)
	RW.C0=clerp(RW.C0,cf(1.45,0.5,0)*angles(math.rad(0),math.rad(0),math.rad(90 + 2.5 * math.cos(sine / 28))),.1)
	LW.C0=clerp(LW.C0,cf(-1.45,0.5,0)*angles(math.rad(0),math.rad(0),math.rad(-90 - 2.5 * math.cos(sine / 28))),.1)
	end
	for i = 0, 2, 0.1 do
	task.wait()
	orb2.CFrame = rarm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)
	orb.CFrame = larm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)

	RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
	LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
	RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
	Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(0)),.1)
	RW.C0=clerp(RW.C0,cf(1.45,0.5,0)*angles(math.rad(0),math.rad(0),math.rad(90 + 2.5 * math.cos(sine / 28))),.1)
	LW.C0=clerp(LW.C0,cf(-1.45,0.5,0)*angles(math.rad(0),math.rad(0),math.rad(-90 - 2.5 * math.cos(sine / 28))),.1)
	end
	for i = 0, .7, 0.1 do
	task.wait()
	orb2.CFrame = rarm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)
	orb.CFrame = larm.CFrame*CFrame.new(0,-0.1+posid/1.05,0)

	RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
	LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
	RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
	Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(0)),.1)
	RW.C0=clerp(RW.C0,cf(1.45,0.5,0)*angles(math.rad(0),math.rad(90),math.rad(90 + 2.5 * math.cos(sine / 28))),.4)
	LW.C0=clerp(LW.C0,cf(-1.45,0.5,0)*angles(math.rad(0),math.rad(-90),math.rad(-90 - 2.5 * math.cos(sine / 28))),.4)
	end
CFuncs["Sound"].Create("rbxassetid://151304356", orb, 5,1)
	CFuncs["Sound"].Create("rbxassetid://151304356", orb2, 5,1)
               ModeOfGlitch = 10101010
storehumanoidWS = 150
hum.WalkSpeed = 150
rainbowmode = false
chaosmode = false
RecolorTextAndRename("BALANCED",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
MAINRUINCOLOR = BrickColor.new("White")
orb.Transparency = 1
orb2.Transparency = 1 
	sphere2(1,"Add",tors.CFrame,vt(1.8,1.8,1.8),1,1,1,BrickColor.new'Black')
sphere2(2,"Add",tors.CFrame,vt(2,2,2),.9,.9,.9,BrickColor.new'White')

game:service'Debris':AddItem(orb,8)
game:service'Debris':AddItem(orb2,8)
for i = 0, 49 do
PixelBlock(1,math.random(8,16),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),10,10,10,0.2,MAINRUINCOLOR,0)
PixelBlock(2,math.random(16,32),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),5,5,5,0.05,BrickColor.new'Black',0)
end
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = MAINRUINCOLOR
v.Material = "Neon"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new'Black'
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new("White")
v.Material = "Ice"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new'Black'
v.Material = "Ice"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new("White")
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new'Black'
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("White")
v.Material = "Neon"
end
end
attack = false
end

	
	
	function DETERMINED()
attack = true
newThemeCust("rbxassetid://1180273873",0,1,1.25)
kan.TimePosition = 44
repeat task.wait() until kan.IsLoaded
wait(8)
bosschatfunc("We don't care what they say,",MAINRUINCOLOR.Color,1)
	for i = 0, 16, .1 do
		CameraEnshaking(0.07, 0.1)
		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
		end
bosschatfunc("We will be here all day,",MAINRUINCOLOR.Color,1)
	for i = 0, 16, .1 do
		CameraEnshaking(0.07, 0.1)

		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
	end
	
bosschatfunc("We’ll stay here 'till it’s over...",MAINRUINCOLOR.Color,1)
	for i = 0, 14, .1 do
		CameraEnshaking(0.1, 0.1)

		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(0,0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
	end
	wait(1)
bosschatfunc("Till the world’s out of sight,",MAINRUINCOLOR.Color,1)
	for i = 0, 16, .1 do
		CameraEnshaking(0.07, 0.1)
		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
		end
bosschatfunc("We will stand, We will fight,",MAINRUINCOLOR.Color,1)
	for i = 0, 16, .1 do
		CameraEnshaking(0.07, 0.1)
		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
	end
	
bosschatfunc("IT'S NOT OVER 'TILL IT'S OVER...",Color3.new(0.5,0,0),1)
Face.Texture = "rbxassetid://15471076"
	for i = 0, 16, .1 do
		CameraEnshaking(0.2, 0.1)
		task.wait()
		RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
		LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)	
		Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
	end
	wait(1)
sphere(1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(1,100000,1),0.6,BrickColor.new("Maroon"))
sphere(1,"Add",root.CFrame,vt(1,1,1),0.8,BrickColor.new("Really red"))
for i = 0, 49 do
	CameraEnshaking(0.6, 0.5)
PixelBlockX(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),8,8,8,0.16,BrickColor.new("Maroon"),0)
sphereMK(2.5,-1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,BrickColor.new("Really red"),0)
slash(math.random(10,20)/10,5,true,"Round","Add","Out",Torso.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-30, 30)), math.rad(math.random(-30, 30)), math.rad(math.random(-40, 40))),vt(0.05,0.01,0.05),math.random(50,60)/250,BrickColor.new("Really red"))
end
CFuncs["Sound"].Create("rbxassetid://239000203", root, 4, 1)
CFuncs["Sound"].Create("rbxassetid://1042716828", root, 2, 1)
CFuncs["Sound"].Create("rbxassetid://847061203", root, 3, 1)
attack = false
               ModeOfGlitch = 699
storehumanoidWS = 100
hum.WalkSpeed = 100
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("DETERMINED",Color3.new(0.5,0,0),BrickColor.new("Really red").Color,"Arcade")
MAINRUINCOLOR = BrickColor.new("Really red")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,BrickColor.new("Really red"),MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
	
	

	
function BigBoy()
attack = true
hum.WalkSpeed = 0 
CFuncs["EchoSound"].Create("rbxassetid://1448033299", char, 5, 1,0,10,0.15,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://1448033299", root, 60, 1,0,10,0.15,0.5,1)
local radm = math.random(1,3)
if radm == 1 then
bosschatfunc("YOU CAN'T ESCAPE THIS!!",MAINRUINCOLOR.Color,1)
elseif radm == 2 then
bosschatfunc("HOW DO YOU LIKE THIS?!",MAINRUINCOLOR.Color,1)
elseif radm == 3 then
bosschatfunc("You make the choice..",MAINRUINCOLOR.Color,1)
end
local rsiz = math.random(1,15)
	local hb = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
	hb.Anchored = true
	hb.CFrame = sorb.CFrame*CFrame.new(0,-3,0)
	local hb2 = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
	hb2.Anchored = true
	hb2.CFrame = sorb.CFrame*CFrame.new(0,-3,0)
	CFuncs["Sound"].Create("rbxassetid://1042700914", sorb, 8,0.25)
	for i = 0, 14, 0.1 do
		task.wait()
rsiz = math.random(5,15)
hb.CFrame = sorb.CFrame*CFrame.new(0,-3,0)
hb2.CFrame = sorb2.CFrame*CFrame.new(0,-3,0)
sphereMK(math.random(3,9),0.25,"Add",sorb.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,MAINRUINCOLOR,-15)	
sphere2(5,"Add",sorb.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(4,4,4),0.01,0.01,0.01,MAINRUINCOLOR)
sphereMK(math.random(3,9),0.25,"Add",sorb2.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,BrickColor.new("Lime green"),-15)	
sphere2(5,"Add",sorb2.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(4,4,4),0.01,0.01,0.01,BrickColor.new("Lime green"))
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-4 - 2 * math.cos(sine / 53)),math.rad(0 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(9 - 2 * math.cos(sine / 53)),math.rad(0 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0.3 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(10)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(90),math.rad(0),math.rad(120)),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(90),math.rad(0),math.rad(-120)),.1)
	end
	CFuncs["Sound"].Create("rbxassetid://1042693018", sorb, 10,0.6)
	CFuncs["Sound"].Create("rbxassetid://1042695469", sorb, 10,0.5)
	CFuncs["Sound"].Create("rbxassetid://1042693018", sorb2, 10,0.6)
	CFuncs["Sound"].Create("rbxassetid://1042695469", sorb2, 10,0.5)
	CFuncs["Sound"].Create("rbxassetid://1042696115", sorb, 10,1)
	CFuncs["Sound"].Create("rbxassetid://1042696115", sorb2, 10,1)
sphere2(3,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(6,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(9,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(3,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,BrickColor.new("Lime green"))
sphere2(6,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,BrickColor.new("Lime green"))
sphere2(9,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,BrickColor.new("Lime green"))
for i = 0, 49 do 
local rsiza = math.random(1,15)
sphereMK(math.random(1,5),0.75,"Add",sorb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiza/10,rsiza/10,rsiza/10,0,MAINRUINCOLOR,0)	
sphereMK(math.random(1,5),0.75,"Add",sorb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiza/10,rsiza/10,rsiza/10,0,MAINRUINCOLOR,0)
end
local a = Instance.new("Part",Character)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = MAINRUINCOLOR
a.Material = "Neon"
a.Transparency = 0
a.Shape = "Cylinder"
	a.CanCollide = false
local a2 = Instance.new("Part",Character)
	a2.Name = "Direction"	
	a2.Anchored = true
	a2.BrickColor = MAINRUINCOLOR
a2.Material = "Neon"
a2.Transparency = 0
a2.Shape = "Cylinder"
	a2.CanCollide = false
local ba = Instance.new("Part",Character)
	ba.Name = "HitDirect"	
	ba.Anchored = true
	ba.BrickColor = MAINRUINCOLOR
ba.Material = "Neon"
ba.Transparency = 1
	ba.CanCollide = false
local ba2 = Instance.new("Part",Character)
	ba2.Name = "HitDirect"	
	ba2.Anchored = true
	ba2.BrickColor = MAINRUINCOLOR
ba2.Material = "Neon"
ba2.Transparency = 1
	ba2.CanCollide = false
	local ray = Ray.new(
	    hb.CFrame.p,                           -- origin
	    (mouse.Hit.p - hb.CFrame.p).unit * 1000 -- direction
	) 
	local ignore = Character
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	local ray2 = Ray.new(
	    hb2.CFrame.p,                           -- origin
	    (mouse.Hit.p - hb2.CFrame.p).unit * 1000 -- direction
	) 
	local hit2, position2, normal2 = workspace:FindPartOnRay(ray2, ignore)
	local distance2 = (hb2.CFrame.p - position).magnitude

	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (hb.CFrame.p - position).magnitude
	a.Size = Vector3.new(distance, 1, 1)
	a.CFrame = CFrame.new(hb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
	a2.BottomSurface = 10
	a2.TopSurface = 10
	a2.Size = Vector3.new(distance2, 1, 1)
	a2.CFrame = CFrame.new(hb2.CFrame.p, position) * CFrame.new(0, 0, -distance2/2)
ba.CFrame = CFrame.new(hb.CFrame.p, position) * CFrame.new(0, 0, -distance)
ba2.CFrame = CFrame.new(hb2.CFrame.p, position) * CFrame.new(0, 0, -distance2)
a.CFrame = a.CFrame*CFrame.Angles(0,math.rad(90),0)
a2.CFrame = a2.CFrame*CFrame.Angles(0,math.rad(90),0)
local msh = Instance.new("SpecialMesh",a)
msh.MeshType = "Cylinder"
msh.Scale = vt(1,4,4)
local msh2 = Instance.new("SpecialMesh",a2)
msh2.MeshType = "Cylinder"
msh2.Scale = vt(1,4,4)
game:GetService("Debris"):AddItem(a, 30)
game:GetService("Debris"):AddItem(a2, 30)
game:GetService("Debris"):AddItem(ba, 30)
game:GetService("Debris"):AddItem(ba2, 30)
	for i = 0, 20, 0.1 do
		task.wait()
hb.CFrame = sorb.CFrame*CFrame.new(0,-3,0)
hb2.CFrame = sorb2.CFrame*CFrame.new(0,-3,0)
ray = Ray.new(
	    hb.CFrame.p,                           -- origin
	    (mouse.Hit.p - hb.CFrame.p).unit * 1000 -- direction
	) 
hit, position, normal = workspace:FindPartOnRay(ray, ignore)
distance = (hb.CFrame.p - position).magnitude
ray2 = Ray.new(
	    hb2.CFrame.p,                           -- origin
	    (mouse.Hit.p - hb2.CFrame.p).unit * 1000 -- direction
	) 
hit2, position2, normal2 = workspace:FindPartOnRay(ray2, ignore)
distance2 = (hb2.CFrame.p - position).magnitude
	a.Size = Vector3.new(distance, 1, 1)
	a.CFrame = CFrame.new(hb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
	a2.Size = Vector3.new(distance2, 1, 1)
	a2.CFrame = CFrame.new(hb2.CFrame.p, position) * CFrame.new(0, 0, -distance2/2)
ba.CFrame = CFrame.new(hb.CFrame.p, position) * CFrame.new(0, 0, -distance)
ba2.CFrame = CFrame.new(hb2.CFrame.p, position) * CFrame.new(0, 0, -distance2)
a.CFrame = a.CFrame*CFrame.Angles(0,math.rad(90),0)
a2.CFrame = a2.CFrame*CFrame.Angles(0,math.rad(90),0)
rsiz = math.random(5,25)
	MagniDamage(ba, 12, 800,18000, 0, "Normal")
	MagniDamage(ba2, 12, 800,18000, 0, "Normal")
for i, v in pairs(FindNearestHead(ba.CFrame.p, 4)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
coroutine.resume(coroutine.create(function()
local bx = Instance.new("Part",Character)
bx.Name = "Location"	
bx.Anchored = true
bx.BrickColor = MAINRUINCOLOR
bx.Material = "Neon"
bx.Transparency = 1
bx.CanCollide = false
bx.Position = ba.Position
sphere2(2,"Add",bx.CFrame,vt(20,0.5,20),0.001,0,0.001,MAINRUINCOLOR)
wait(math.random(1,2))
sphere2(4,"Add",bx.CFrame,vt(5,10000,5),0.1,0,0.1,bc("Lime green"))
sphere2(4,"Add",bx.CFrame,vt(5,10000,5),0.25,0,0.25,MAINRUINCOLOR)
sphere2(6,"Add",bx.CFrame,vt(10,10,10),0.5,0.5,0.5,bc("Lime green"))
	CFuncs["Sound"].Create("rbxassetid://1042693018", bx, 5,0.7)
	CFuncs["Sound"].Create("rbxassetid://1042695469", bx, 5,0.8)
	MagniDamage(bx, 20, 80000,900000, 0, "Normal")
for i, v in pairs(FindNearestHead(bx.CFrame.p, 15)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
wait(5)
bx:Destroy()
end))
sphereMK(math.random(4,8),0.25,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/5,rsiz/5,rsiz/5,0,BrickColor.new("Lime green"),0)
sphereMK(math.random(4,8),0.25,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/5,rsiz/5,rsiz/5,0,BrickColor.new("Lime green"),0)
for c = 0, 2 do	
sphereMK(math.random(3,6),0.5,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/5,rsiz/5,rsiz/5,0,BrickColor.new("Lime green"),2)
end
sphere2(5,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(4.2,4.2,4.2),0.01,0.01,0.01,MAINRUINCOLOR)
sphere2(5,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(12,12,12),0.05,0.05,0.05,MAINRUINCOLOR)
sphere2(5,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(4.2,4.2,4.2),0.01,0.01,0.01,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-4 - 2 * math.cos(sine / 53)),math.rad(0 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(9 - 2 * math.cos(sine / 53)),math.rad(0 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0.3 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.05)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(10)),.05)
RW.C0=clerp(RW.C0,cf(1.25,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-15)),.05)
LW.C0=clerp(LW.C0,cf(-1.25,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(15)),.05)
	end
for i = 0, 1 do
	CFuncs["Sound"].Create("rbxassetid://1042693018", sorb, 5,0.8)
	CFuncs["Sound"].Create("rbxassetid://1042695469", sorb, 5,0.9)
	CFuncs["Sound"].Create("rbxassetid://1042693018", ba, 10,0.8)
	CFuncs["Sound"].Create("rbxassetid://1042695469", ba, 10,0.9)
end
	MagniDamage(ba, 30, 8000,180000, 0, "Normal")
	MagniDamage(ba2, 30, 8000,180000, 0, "Normal")
for i, v in pairs(FindNearestHead(ba.CFrame.p, 10)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
sphere2(1,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0,0,0),1,1,1,MAINRUINCOLOR)
sphere2(2,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0,0,0),1,1,1,MAINRUINCOLOR)
sphere2(3,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0,0,0),1,1,1,MAINRUINCOLOR)
sphere2(3,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(6,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(9,"Add",hb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,MAINRUINCOLOR)
sphere2(3,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,bc("Lime green"))
sphere2(6,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,bc("Lime green"))
sphere2(9,"Add",hb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),0.3,0.3,0.3,bc("Lime green"))
for i = 0, 49 do 
local rsiza = math.random(1,15)
sphereMK(math.random(1,5),0.75,"Add",sorb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiza/10,rsiza/10,rsiza/10,0,bc("Lime green"),0)
sphereMK(math.random(1,5),0.75,"Add",sorb2.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiza/10,rsiza/10,rsiza/10,0,bc("Lime green"),0)	
end
for i = 0, 49 do
rsiz = math.random(1,8)	
sphereMK(math.random(1,3),1,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz,rsiz,rsiz,0,bc("Lime green"),2)
end
coroutine.resume(coroutine.create(function()
for i = 0, 99 do
task.wait()
a.Transparency = a.Transparency + 0.01
a2.Transparency = a2.Transparency + 0.01
end
a:Destroy()
ba:Destroy()
a2:Destroy()
ba2:Destroy()
end))
hum.WalkSpeed = storehumanoidWS
hb:Destroy()
hb2:Destroy()
attack = false
end

	
	
	
function NuclearJump()
attack = true
local keptcolor = BrickColor.new("Forest green")
CFuncs["Sound"].Create("rbxassetid://1295446488", root, 10, 1)
CFuncs["EchoSound"].Create("rbxassetid://1657242236", char, 4, 1,0,10,0.15,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://1657242236", root, 10, 1,0,10,0.15,0.5,1)
for i = 0, 5 do
task.wait()
waveEff(math.random(10,100)/10,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(15,0.25,15),math.random(25,250)/250,0.25,BrickColor.new("White"))
slash(math.random(10,100)/10,3,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-360,360)),math.rad(math.random(-10,10))),vt(0.01,0.01,0.01),math.random(50,500)/250,BrickColor.new("White"))
end
CamShakeAll(20,100,char)
root.Velocity = vt(0,250,0) + root.CFrame.lookVector*250
wait(0.3)
repeat
task.wait()
for i = 0, 1, 0.6 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(90),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(180),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(270),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
end
hfr,pfr=rayCast(root.Position,(CFrame.new(root.Position,root.Position - vt(0,1,0))).lookVector,4,char)
until hfr ~= nil
if hfr ~= nil then
local locat = Instance.new("Part", char)
locat.CanCollide = false
locat.FormFactor = 3
locat.Name = "Ring"
locat.Material = "Neon"
locat.Size = Vector3.new(1, 1, 1)
locat.Transparency = 1
locat.TopSurface = 0
locat.BottomSurface = 0
locat.Anchored = true
locat.CFrame = root.CFrame*CFrame.new(0,-3,0)
local poste = 0
local rotation = 0
local upperpos = 0
local rate = 0
local x = locat
CamShakeAll(50,100,char)
CFuncs["Sound"].Create("rbxassetid://847061203", char, 1,1)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 2.5, 1)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 2.5, 0.5)
sphere(1.25,"Add",root.CFrame,vt(0,0,0),16,MAINRUINCOLOR)
sphere(0.85,"Add",root.CFrame,vt(0,0,0),19,MAINRUINCOLOR)
for i = 0, 49 do
slash(math.random(10,13)/10,2,false,"Round","Add","Out",root.CFrame*CFrame.new(0,3,0)*CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))),vt(0.05,0.01,0.05),math.random(9,14),MAINRUINCOLOR)
end
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 280)) do
if v:FindFirstChild('Torso') then
dmg(v)
end
end
coroutine.resume(coroutine.create(function()
coroutine.resume(coroutine.create(function()
for i = 0, 119 do
sphere2(math.random(1,2),"Add",x.CFrame*CFrame.new(math.random(-350,350),0,math.random(-350,350)),vt(5,1,5),-0.05,math.random(50,250)/50,-0.05,keptcolor)
end
end))
for i = 0, 158 do
task.wait()
rotation = rotation + 5
poste = poste + 1
upperpos = upperpos + rate
rate = rate + 0.1
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(5+upperpos/10,5+upperpos/10,5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(90-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(5+upperpos/10,5+upperpos/10,5+upperpos/10),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(180-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(5+upperpos/10,5+upperpos/10,5+upperpos/10),-0.025,-0.025,-0.025,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,math.rad(270-rotation),0)*CFrame.new(0,upperpos/2,poste*2),vt(5+upperpos/10,5+upperpos/10,5+upperpos/10),-0.025,-0.025,-0.025,keptcolor)
end
x:Destroy()
end))
end
attack = false
end

	
	
function ExquisiteDisk()
attack = true
hum.WalkSpeed = 2
local keptcolor = MAINRUINCOLOR
local radm = math.random(1,3)
if radm == 1 then
bosschatfunc("Dont make this too easy for you.",MAINRUINCOLOR.Color,1)
elseif radm == 2 then
bosschatfunc("Exquisite Disk!",MAINRUINCOLOR.Color,1)
elseif radm == 3 then
bosschatfunc("Take it!",MAINRUINCOLOR.Color,1)
end
CFuncs["Sound"].Create("rbxassetid://847061203", root, 2, 1)
CFuncs["EchoSound"].Create("rbxassetid://1625448638", root, 4, 1,0,10,0.15,0.5,1)
sphere2(5,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(1,1,1),0.1,0.1,0.1,keptcolor,keptcolor.Color)
sphere2(5,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(1,1,1),0.2,0.2,0.2,keptcolor,keptcolor.Color)
for i = 0, 14 do
PixelBlock(1,math.random(1,3),"Add",larm.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.02,BrickColor.new("Toothpaste"),0)
end
for i = 0,2,0.1 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-60)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(30)),.3)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.3)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(60)),.3)
end
CFuncs["Sound"].Create("rbxassetid://763755889", root, 2.5,1.1)
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(30)),.6)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(60)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(90)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(30)),.6)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(60)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(180)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(30)),.6)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(60)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(270)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(30)),.6)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(60)),.6)
end
local rot = 15
for i = 0, 2 do
local dis = CreateParta(char,0.5,1,"Neon",BrickColor.new("Toothpaste"))
CFuncs["EchoSound"].Create("rbxassetid://763718160", dis, 3, 1.1,0,10,0.15,0.5,1)
dis.CFrame = root.CFrame*CFrame.new(0,2,-3)
CreateMesh(dis,"Sphere",10,1,10)
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-5,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(5,0,0)
local trl = Instance.new('Trail',wed)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(dis.Color)
trl.Lifetime = 0.6
local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    dis.CFrame.p,                           -- origin
	    (mouse.Hit.p - dis.CFrame.p).unit * 500 -- direction
	) 
	local ignore = dis
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (dis.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(dis.CFrame.p, position) * CFrame.new(0, 0, 0)
dis.CFrame = a.CFrame
dis.CFrame = dis.CFrame*CFrame.Angles(0,math.rad(rot),0)
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*250
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 5)
local hitted = false
coroutine.resume(coroutine.create(function()
dis.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
    CamShakeAll(20,35,Character)
	CFuncs["EchoSound"].Create("rbxassetid://782200047", dis, 7, 1.1,0,10,0.15,0.5,1)
	MagniDamage(dis, 30, 82,34575, 0, "Normal")
	sphere2(8,"Add",dis.CFrame,vt(10,1,10),1,0.1,1,keptcolor,keptcolor.Color)
	sphere2(4,"Add",dis.CFrame,vt(1,1,1),0.5,0.5,0.5,keptcolor,keptcolor.Color)
	sphere2(3,"Add",dis.CFrame,vt(1,1,1),0.5,0.5,0.5,BrickColor.new("White"),Color3.new(1,1,1))
	coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(dis.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(1)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.1,20,0),NumberSequenceKeypoint.new(0.8,40,0),NumberSequenceKeypoint.new(1,60,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(150)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
	end))
	coroutine.resume(coroutine.create(function()
		for i = 0, 9 do
local disr = CreateParta(char,1,1,"Neon",keptcolor)
disr.CFrame = dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",disr)
at1.Position = vt(-2,0,0)
local at2 = Instance.new("Attachment",disr)
at2.Position = vt(2,0,0)
local trl = Instance.new('Trail',disr)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://2342682798"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(Color3.new(0.3,1,1))
trl.Lifetime = 0.5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = disr.CFrame.lookVector*math.random(50,200)
bv.Parent = disr
local val = 0
coroutine.resume(coroutine.create(function()
	task.wait(30)
	for i = 0, 9 do
		task.wait()
		val = val + 0.1
		trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, val),NumberSequenceKeypoint.new(1, 1)})
	end
game:GetService("Debris"):AddItem(disr, 3)
end))
end
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(Color3.new(0.3,1,1))
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.25)
eff.Enabled = false
end))
	for i = 0, 9 do
		slash(math.random(10,20)/10,5,true,"Round","Add","Out",dis.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(100,200)/250,BrickColor.new("White"))
	end
for i = 0, 19 do
PixelBlock(1,math.random(5,20),"Add",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),4,4,4,0.08,BrickColor.new("Toothpaste"),0)
end
dis.Anchored = true
dis.Transparency = 1
wait(8)
dis:Destroy()
end
end)
end))
rot = rot - 15
end
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(-30),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(5)),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(60)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(-50)),.3)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(10)),.3)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(90),math.rad(0),math.rad(-60)),.3)
end
attack = false
hum.WalkSpeed = storehumanoidWS
end
	

function EternalChaosOrb()
attack = true
hum.WalkSpeed = 1
local keptcolor = MAINRUINCOLOR
CFuncs["Sound"].Create("rbxassetid://1042700914", root, 5, 0.25)
for i = 0,14,0.1 do
		task.wait()
slash(math.random(25,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,6,1)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.2,0.01,0.2),-0.2,BrickColor.random())
sphere2(3,"Add",root.CFrame*CFrame.new(0,6,0) + root.CFrame.lookVector*1,vt(3,3,3),0.06,0.06,0.06,MAINRUINCOLOR)
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-35),math.rad(0),math.rad(0)),.1)
RW.C0 = clerp(RW.C0, CFrame.new(1.25, 1, -0.5) * angles(math.rad(170), math.rad(0), math.rad(-20)), 0.1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.25, 1, -0.5) * angles(math.rad(170), math.rad(0), math.rad(20)), 0.1)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(0),math.rad(0)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0)),.1)
end
local dis = CreateParta(char,0,1,"Neon",BrickColor.new("Black"))
for i = 0, 4 do
CFuncs["Sound"].Create("rbxassetid://335657174", dis, 10, 0.5)
end
dis.CFrame = root.CFrame*CFrame.new(0,2,-3)
CreateMesh(dis,"Sphere",10,10,10)
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-5,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(5,0,0)
local trl = Instance.new('Trail',dis)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.FaceCamera = true
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(dis.Color)
trl.Lifetime = 3
local efec = Instance.new("ParticleEmitter",dis)
efec.Texture = "rbxassetid://2109052855"
efec.LightEmission = 1
efec.Color = ColorSequence.new(Color3.new(0.5,0,1))
efec.Rate = 5
efec.Lifetime = NumberRange.new(3)
efec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,25,0),NumberSequenceKeypoint.new(0.2,50,0),NumberSequenceKeypoint.new(0.6,35,0),NumberSequenceKeypoint.new(0.8,50,0),NumberSequenceKeypoint.new(1,75,0)})
efec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.25,0),NumberSequenceKeypoint.new(0.6,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
efec.Drag = 5
efec.LockedToPart = true
efec.Rotation = NumberRange.new(-500,500)
efec.VelocitySpread = 9000
efec.RotSpeed = NumberRange.new(-500,500)
local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    dis.CFrame.p,                           -- origin
	    (mouse.Hit.p - dis.CFrame.p).unit * 500 -- direction
	) 
	local ignore = dis
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (dis.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(dis.CFrame.p, position) * CFrame.new(0, 0, 0)
dis.CFrame = a.CFrame
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*100
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 15)
local hitted = false
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if hitted == false and dis.Parent ~= nil then
			PixelBlock(3,math.random(0,2),"Add",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),5,5,5,0.05,BrickColor.random(),0)
			trl.Color = ColorSequence.new(BrickColor.random().Color)
			efec.Color = ColorSequence.new(BrickColor.random().Color)
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestHead(dis.CFrame.p, 50)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
		elseif hitted == true and dis.Parent == nil then
			break
		end
	end
end))
coroutine.resume(coroutine.create(function()
dis.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
	shakes(1,1)
	efec.Enabled = false
	for i = 0, 3 do
	CFuncs["Sound"].Create("rbxassetid://1368637781", dis, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://763718160", dis, 10, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", dis, 10, 1)
CFuncs["Sound"].Create("rbxassetid://335657174", dis, 10, 1)
end
MagniDamage(dis, 125, 82000,345700005, 0, "Normal")
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestHead(dis.CFrame.p, 100)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
	sphere2(2,"Add",dis.CFrame,vt(1,1,1),3,3,3,keptcolor,keptcolor.Color)
	sphere2(3,"Add",dis.CFrame,vt(1,1,1),3,3,3,BrickColor.random(),keptcolor.Color)
	sphere2(4,"Add",dis.CFrame,vt(1,1,1),4,4,4,BrickColor.random(),keptcolor.Color)
	sphere2(5,"Add",dis.CFrame,vt(1,1,1),4,4,4,BrickColor.random(),keptcolor.Color)
	coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(dis.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(3)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.1,20,0),NumberSequenceKeypoint.new(0.8,40,0),NumberSequenceKeypoint.new(1,60,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(350)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
	end))
	coroutine.resume(coroutine.create(function()
		for i = 0, 9 do
local disr = CreateParta(char,1,1,"Neon",keptcolor)
disr.CFrame = dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",disr)
at1.Position = vt(-30,0,0)
local at2 = Instance.new("Attachment",disr)
at2.Position = vt(30,0,0)
local trl = Instance.new('Trail',disr)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://2342682798"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(BrickColor.random().Color)
trl.Lifetime = 0.5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = disr.CFrame.lookVector*math.random(150,350)
bv.Parent = disr
local val = 0
coroutine.resume(coroutine.create(function()
	task.wait(30)
	for i = 0, 9 do
		task.wait()
		val = val + 0.1
		trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, val),NumberSequenceKeypoint.new(1, 1)})
	end
game:GetService("Debris"):AddItem(disr, 3)
end))
end
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(BrickColor.random().Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,5,0),NumberSequenceKeypoint.new(0.8,4,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(100,400)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.25)
eff.Enabled = false
end))
	for i = 0, 19 do
		slash(math.random(10,20)/10,5,true,"Round","Add","Out",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(200,800)/250,BrickColor.new("White"))
	end
for i = 0, 49 do
PixelBlock(1,math.random(5,40),"Add",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),10,10,10,0.2,BrickColor.random(),0)
end
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/70,math.random(-10,10)/70,math.random(-10,10)/70)
end
hum.CameraOffset = vt(0,0,0)
end))
dis.Anchored = true
dis.Transparency = 1
wait(8)
dis:Destroy()
end
end)
end))
for i = 0,2,0.1 do
		task.wait()
              RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,-0.3,-0.5)* angles(math.rad(30),math.rad(0),math.rad(0)),0.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(0)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.25, 0.5, -0.5) * angles(math.rad(40), math.rad(0), math.rad(-10)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.25, 0.5, -0.5) * angles(math.rad(40), math.rad(0), math.rad(10)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-0.75 - 0.05 * math.cos(sine / 25),-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(0),math.rad(30)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.3)
	end
attack = false
hum.WalkSpeed = storehumanoidWS
end


function uselessnuke()
attack = true
local vel = Instance.new("BodyPosition", root)
vel.P = 25000
vel.D = 1000
vel.maxForce = Vector3.new(50000000000, 10e10, 50000000000)
vel.position = root.CFrame.p + vt(0,250,0)
CFuncs["Sound"].Create("rbxassetid://1295446488", char, 1.5, 0.8)
for i = 0, 49 do
coroutine.resume(coroutine.create(function()
slash(math.random(10,100)/10,3,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-360,360)),math.rad(math.random(-10,10))),vt(0.05,0.01,0.05),math.random(25,500)/250,BrickColor.new("White"))
end))
end
for i = 0, 4, 0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.35,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-25)),.8)
LH.C0=clerp(LH.C0,cf(-1,-0.45,-0.5)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(25)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(35),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-57)),.8)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,-0.5)*angles(math.rad(83),math.rad(0),math.rad(58)),.8)
end
wait(2)
local efec = Instance.new("ParticleEmitter",root)
efec.Texture = "rbxassetid://2109052855"
efec.LightEmission = 1
efec.Color = ColorSequence.new(BrickColor.new("Pastel light blue").Color)
efec.Rate = 15
efec.Lifetime = NumberRange.new(1)
efec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,100,0),NumberSequenceKeypoint.new(0.2,50,0),NumberSequenceKeypoint.new(0.6,125,0),NumberSequenceKeypoint.new(0.8,175,0),NumberSequenceKeypoint.new(1,20,0)})
efec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.25,0),NumberSequenceKeypoint.new(0.6,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
efec.Drag = 5
efec.LockedToPart = true
efec.Rotation = NumberRange.new(-500,500)
efec.VelocitySpread = 9000
efec.RotSpeed = NumberRange.new(-500,500)
local efec2 = efec:Clone()
efec2.LightEmission = 1
efec2.Texture = "rbxassetid://2092248396"
efec2.Parent = root
efec2.Rate = 30
efec2.Lifetime = NumberRange.new(1)
efec2.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,175,0),NumberSequenceKeypoint.new(0.5,150,0),NumberSequenceKeypoint.new(0.8,500,0),NumberSequenceKeypoint.new(1,1000,0)})
efec2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
efec2.Speed = NumberRange.new(0)
efec2.RotSpeed = NumberRange.new(-100,100)
sphere2(1,"Add",root.CFrame,vt(500,500,500),-10,-10,-10,BrickColor.new("Alder"))
sphere2(1,"Add",root.CFrame,vt(750,750,750),-15,-15,-15,BrickColor.new("Pastel light blue"))
CFuncs["LongSound"].Create("rbxassetid://1930483671", char, 10, 1)
wait(2)
CameraEnshaking(20,50)
CFuncs["Sound"].Create("rbxassetid://1368605755", char, 10, 1)
CFuncs["Sound"].Create("rbxassetid://763718160", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://763718160", char, 5, 0.25)
CFuncs["Sound"].Create("rbxassetid://782353443", char, 10, 1)
CFuncs["Sound"].Create("rbxassetid://782353443", char, 10, 0.75)
CFuncs["LongSound"].Create("rbxassetid://782353443", char, 10, 0.5)
CFuncs["LongSound"].Create("rbxassetid://782353443", char, 10, 0.25)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 10, 1)
CFuncs["Sound"].Create("rbxassetid://239000203", char, 10, 1)
coroutine.resume(coroutine.create(function()
for i = 0, 74, 0.1 do
task.wait()
MagniDamage(root, 1500000, 999999,99999999, 0, "Normal")
coroutine.resume(coroutine.create(function()
for i = 0, 2 do
slash(math.random(10,40)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(250,2500)/250,BrickColor.new("White"))
end
slash(math.random(30,90)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.01,0.1),math.random(2,5)/250,BrickColor.new("Alder"))
sphere2(10,"Add",root.CFrame,vt(30,100000,30),2.5,100,2.5,BrickColor.new("Alder"))
sphere2(10,"Add",root.CFrame,vt(50,100000,50),3,100,3,BrickColor.new("Pastel light blue"))
sphere2(10,"Add",root.CFrame,vt(10,10,10),5,5,5,BrickColor.new("Alder"))
sphere2(10,"Add",root.CFrame,vt(10,10,10),10,10,10,BrickColor.new("Pastel light blue"))
end))
end
vel:Destroy()
attack = false
efec.Enabled = false
efec2.Enabled = false
game:GetService("Debris"):AddItem(efec, 5)
game:GetService("Debris"):AddItem(efec2, 5)
end))
end


function Laserbeamy()
attack = true
hum.WalkSpeed = 0
CFuncs["Sound"].Create("rbxassetid://289315275", handlex2, 7.5, 1)
CFuncs["Sound"].Create("rbxassetid://1521621176", handlex2, 5,1)
CFuncs["Sound"].Create("rbxassetid://418302853", handlex2, 6.5, 1)
CFuncs["TimeSound"].Create("rbxassetid://184173042", handlex2, 5, 1,0,2.75)
CFuncs["Sound"].Create("rbxassetid://898407368", handlex2, 1.75, 1.2)
CFuncs["Sound"].Create("rbxassetid://1930016365", handlex2, 1.75, 1.1)
CFuncs["Sound"].Create("rbxassetid://1752639888", handlex2, 1.5, 1)
local efec = Instance.new("ParticleEmitter",handlex2)
efec.Texture = "rbxassetid://2109052855"
efec.LightEmission = 1
efec.Color = ColorSequence.new(BrickColor.new("Alder").Color)
efec.Rate = 10
efec.Lifetime = NumberRange.new(0.75)
efec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,5,0),NumberSequenceKeypoint.new(0.8,7.5,0),NumberSequenceKeypoint.new(1,0,0)})
efec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.25,0),NumberSequenceKeypoint.new(0.6,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
efec.Drag = 5
efec.LockedToPart = true
efec.Rotation = NumberRange.new(-500,500)
efec.VelocitySpread = 9000
efec.Speed = NumberRange.new(0)
efec.RotSpeed = NumberRange.new(-500,500)
local efec2 = efec:Clone()
efec2.LightEmission = 1
efec2.Texture = "rbxassetid://2092248396"
efec2.Parent = handlex2
efec2.Rate = 10
efec2.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,17.5,0),NumberSequenceKeypoint.new(0.5,15,0),NumberSequenceKeypoint.new(0.8,50,0),NumberSequenceKeypoint.new(1,100,0)})
efec2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
efec2.RotSpeed = NumberRange.new(-100,100)
	for i = 0,10,0.1 do
		task.wait()
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
actualrotationvalue = actualrotationvalue + 14
handlex2weld.C0=clerp(handlex2weld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlex2weld.C1=clerp(handlex2weld.C1,cf(0,-2,5)*angles(math.rad(-5),math.rad(60),math.rad(0)),.3)
sphere2(5,"Add",handlex2.CFrame,vt(4,4,0.1),0.005,0.005,0.005,BrickColor.new("Alder"))
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,-0.05)* angles(math.rad(5),math.rad(0),math.rad(60)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(5),math.rad(-5),math.rad(-60)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(95), math.rad(0), math.rad(60)), 0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-30)), 0.5)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(-30),math.rad(15)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-4.5),math.rad(0),math.rad(10)),.5)
	end
efec.Enabled = false
efec2.Enabled = false
game:GetService("Debris"):AddItem(efec, 5)
game:GetService("Debris"):AddItem(efec2, 5)
CFuncs["Sound"].Create("rbxassetid://919941001", handlex2, 8, 1.1)
sphere2(5,"Add",handlex2.CFrame,vt(4,4,0.1),0.5,0.5,0.005,BrickColor.new("Alder"))
sphere2(4,"Add",handlex2.CFrame,vt(4,4,0.1),0.5,0.5,0.005,BrickColor.new("Alder"))
sphere2(3,"Add",handlex2.CFrame,vt(4,4,0.1),0.5,0.5,0.005,BrickColor.new("Alder"))
for i = 0, 14 do
	slash(math.random(10,40)/10,5,true,"Round","Add","Out",handlex2.CFrame*CFrame.Angles(math.rad(90 + math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(30,70)/250,BrickColor.new("White"))
end
for i = 0, 24 do
	for i = 0,1,0.6 do
		task.wait()
hum.CameraOffset = vt(math.random(-10,10)/60,math.random(-10,10)/60,math.random(-10,10)/60)
actualrotationvalue = actualrotationvalue + 14
handlex2weld.C0=clerp(handlex2weld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlex2weld.C1=clerp(handlex2weld.C1,cf(0,-2,5)*angles(math.rad(-5),math.rad(60),math.rad(0)),.3)
sphere2(5,"Add",handlex2.CFrame,vt(4,4,0.1),0.005,0.005,0.005,BrickColor.new("Alder"))
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,-0.05)* angles(math.rad(5),math.rad(0),math.rad(60)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(5),math.rad(-5),math.rad(-60)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(95), math.rad(0), math.rad(60)), 0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-30)), 0.5)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(-30),math.rad(15)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-4.5),math.rad(0),math.rad(10)),.5)
	end
local orb = Instance.new("Part", char)
CFuncs["Sound"].Create("rbxassetid://1146690130", handlex2, 2,1.25)
orb.BrickColor = BrickColor.new("Alder")
orb.CanCollide = false
orb.FormFactor = 3
orb.Name = "Ring"
orb.Material = "Neon"
orb.Size = Vector3.new(1, 1, 1)
orb.Transparency = 1
orb.TopSurface = 0
orb.BottomSurface = 0
orb.Anchored = true
orb.CFrame = handlex2.CFrame*CFrame.new(math.random(-2,2),math.random(-2,2),math.random(0,1))
local a = Instance.new("Part",char)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = BrickColor.new("Alder")
a.Material = "Neon"
a.Transparency = 0.25
a.Shape = "Cylinder"
	local ht = Instance.new("Part",char)
	ht.Name = "DirectionHit"	
	ht.Anchored = true
	ht.BrickColor = BrickColor.new("Alder")
ht.CanCollide = false
ht.Transparency = 1
ht.Size = vt(0.1,0.1,0.1)
CFuncs["Sound"].Create("rbxassetid://206049428", ht, 3, 1)
CFuncs["Sound"].Create("rbxassetid://824687369", ht, 6, 1)
CFuncs["Sound"].Create("rbxassetid://698224146", ht, 4, 1)
CFuncs["Sound"].Create("rbxassetid://183763487", ht, 4, 1.1)
	a.CanCollide = false
	local ray = Ray.new(
	    orb.CFrame.p,                           -- origin
	    (mouse.Hit.p - orb.CFrame.p).unit * 500 -- direction
	) 
	local ignore = char
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (orb.CFrame.p - position).magnitude
	a.Size = Vector3.new(distance,1,1)
	a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
	ht.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
sphere2(3,"Add",ht.CFrame,vt(1.25,1.25,1.25),0.35,0.35,0.35,BrickColor.new("Alder"))
sphere2(4,"Add",ht.CFrame,vt(1.25,1.25,1.25),0.35,0.35,0.35,BrickColor.new("Alder"))
MagniDamage(ht, 15, 70,95, 0, "Normal")
for i = 0, 4 do
slash(math.random(10,60)/10,5,true,"Round","Add","Out",ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(40,80)/250,BrickColor.new("White"))
sphere2(4,"Add",ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(3,1,3),-0.015,1.5,-0.015,BrickColor.new("Alder"))
local rsiz = math.random(30,60)
sphereMK(math.random(2,4),0.75,"Add",ht.CFrame*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,BrickColor.new("Alder"),0)
end
a.CFrame = a.CFrame*CFrame.Angles(0,math.rad(90),0)
local msh = Instance.new("SpecialMesh",a)
msh.MeshType = "Cylinder"
msh.Scale = vt(1,2,2)
coroutine.resume(coroutine.create(function()
for i = 0, 49 do
task.wait()
msh.Scale = msh.Scale - vt(0,0.04,0.04)
a.Transparency = a.Transparency + 0.02
end
a:Destroy()
ht:Destroy()
orb:Destroy()
end))
end
hum.WalkSpeed = 16
attack = false
end




function cyberstomp()
	attack = true
	hum.WalkSpeed = 0
	CFuncs["Sound"].Create("rbxassetid://1368598393", root, 5, 1)
	for i = 0,4,0.1 do
		task.wait()
		hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
		block(10,"Add",rleg.CFrame*CFrame.new(0,-1,0),vt(1,1,1),0.01,0.01,0.01,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
		RH.C0=clerp(RH.C0,cf(1,-0.15,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5),math.rad(-20)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(20)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.25,-0.05)*angles(math.rad(-20),math.rad(0),math.rad(10)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-10)),.1)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-5),math.rad(-10),math.rad(20)),.1)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-5),math.rad(10),math.rad(-20)),.1)
	end
	local bgui,imgc = createBGCircle(0,root,MAINRUINCOLOR.Color)
	bgui.AlwaysOnTop = true
for i = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://1368637781", root, 3,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 4, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 6, 1)
CFuncs["Sound"].Create("rbxassetid://335657174", root, 10, 0.75)
end
local scl= 0.1
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),1,0.01,1,BrickColor.new("Toothpaste"),BrickColor.new("Toothpaste").Color)
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),2,0.01,2,BrickColor.new("Toothpaste"),BrickColor.new("Toothpaste").Color)
		for i = 0,5,0.1 do
		task.wait()
		scl = scl + 0.1*scl
		bgui.Size = UDim2.new(scl*5,0,scl*5,0)
MagniDamage(root,scl*3,99999,9999999,0,"Normal",153092213)
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestTorso(root.CFrame.p, scl*3)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
		hum.CameraOffset = vt(math.random(-2*scl,2*scl)/25,math.random(-2*scl,2*scl)/25,math.random(-2*scl,2*scl)/25)
		waveEff(5,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),scl/10,0.1,BrickColor.new("Cyan"))
		slash(5,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3.25,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-360,360)),math.rad(math.random(-10,10))),vt(0.05,0.01,0.05),scl/10,BrickColor.new("Navy blue"))
		for i = 0, 2 do
		sphereMK2(5,math.random(15,65)/45,"Add",root.CFrame*CFrame.new(math.random(-scl*5,scl*5),-10,math.random(-scl*3,scl*3))*CFrame.Angles(math.rad(90 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),0.75,0.75,10,-0.0075,BrickColor.new("Toothpaste"),Color3.new(0,1,1),0)
		end
		sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),scl/10,0.01,scl/10,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
		RH.C0=clerp(RH.C0,cf(1,-1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(10)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.25,-0.05)*angles(math.rad(10),math.rad(0),math.rad(0)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(40),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-35),math.rad(-10),math.rad(60)),.8)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-35),math.rad(10),math.rad(-50)),.8)
		end
		coroutine.resume(coroutine.create(function()
			for i = 0, 24 do
				task.wait()
				bgui.Size = bgui.Size + UDim2.new(scl,0,scl,0)
				imgc.ImageTransparency = imgc.ImageTransparency + 0.04
			end
			bgui:Destroy()
		end))
		hum.CameraOffset = vt(0,0,0)
	attack = false
	hum.WalkSpeed = 16
end


function blink()
for i = 0, 14 do
slash(math.random(30,90)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(50,100)/250,BrickColor.new("Cyan"))
end
block(10,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.25,0.25,0.25,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
block(10,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
coroutine.resume(coroutine.create(function()
for i = 0, 24 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
end
end))
CFuncs["Sound"].Create("rbxassetid://335657174", root, 10, 1)
root.CFrame = root.CFrame + root.CFrame.lookVector*100
for i = 0, 14 do
slash(math.random(30,90)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(50,100)/250,BrickColor.new("Cyan"))
end
block(10,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.25,0.25,0.25,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
block(10,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
end

function RapidBurst()
attack = true
hum.WalkSpeed = 0
CFuncs["Sound"].Create("rbxassetid://1368598393", char, 2.5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 0.5)
CFuncs["EchoSound"].Create("rbxassetid://1718412034", char, 4, 1,0,10,0.15,0.5,1)
bosschatfunc("SHATTER!",MAINRUINCOLOR.Color,1.8)
bosschatfunc("SHATTER!",MAINRUINCOLOR.Color,1.9)
bosschatfunc("SHATTER!",MAINRUINCOLOR.Color,2)
local keptcolor = MAINRUINCOLOR
for i = 0,8,0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
slash3(math.random(25,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,25,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(2,0.01,2),-2,BrickColor.random())
block(10,"Add",root.CFrame*CFrame.new(0,25,0),vt(0,0,0),0.5,0.5,0.5,BrickColor.random(),BrickColor.random().Color)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-15 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.15 + 0.02 * math.cos(sine / 32),-0.1 + 0.05 * math.cos(sine / 32))*angles(math.rad(-15 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-25 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.35,1 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(165 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(-10 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.35,1 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(165 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(13 - 3 * math.cos(sine / 45))),.1)
end
shakes(2,4)
for i = 0, 99 do
local dis = CreateParta(char,1,1,"Neon",MAINRUINCOLOR)
dis.CFrame = root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),math.random(-5,5))*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-25000,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(25000,0,0)
local trl = Instance.new('Trail',dis)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(BrickColor.random().Color)
trl.Lifetime = 5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*math.random(500,2500)
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 5)
end
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,1)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,1.5)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,3)
Block2(2,"Add",root.CFrame,vt(1,1,1),1,1,1,BrickColor.random(),BrickColor.random().Color)
Block2(2,"Add",root.CFrame,vt(1,1,1),2,2,2,BrickColor.random(),BrickColor.random().Color)
Block2(2,"Add",root.CFrame,vt(1,1,1),4,4,4,BrickColor.random(),BrickColor.random().Color)
Block2(2,"Add",root.CFrame,vt(1,1,1),8,8,8,BrickColor.random(),BrickColor.random().Color)
CFuncs["Sound"].Create("rbxassetid://1841058541", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://2095993595", char, 5,0.8)
CFuncs["Sound"].Create("rbxassetid://1841058541", char, 5,1)
hum.CameraOffset = vt(0,0,0)
for i = 0, 24 do
slash3(math.random(10,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,1500)/250,BrickColor.random())
end
local distam = 0
coroutine.resume(coroutine.create(function()
for i = 0, 99 do
	wait()
distam = distam + 1
local xa = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xa.Anchored = true
xa.CFrame = root.CFrame*CFrame.new(math.random(-distam,distam),math.random(-distam,distam),math.random(-distam,distam))
game:GetService("Debris"):AddItem(xa, 5)
for i = 0, 4 do
slash(math.random(25,50)/10,5,true,"Round","Add","Out",xa.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(200,500)/250,BrickColor.random())
end
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",xa)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(BrickColor.random().Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(1,3)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,30,0),NumberSequenceKeypoint.new(0.2,5,0),NumberSequenceKeypoint.new(0.8,5,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(50,500)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.25)
eff.Enabled = false
end))
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/10,math.random(-10,10)/10,math.random(-10,10)/10)
end
hum.CameraOffset = vt(0,0,0)
end))
CFuncs["Sound"].Create("rbxassetid://675172759", xa, 7,math.random(100,200)/200)
Block2(5,"Add",xa.CFrame,vt(1,1,1),1,1,1,BrickColor.random(),BrickColor.random().Color)
Block2(5,"Add",xa.CFrame,vt(1,1,1),2,2,2,BrickColor.random(),BrickColor.random().Color)
MagniDamage(xa, 60, 9999,99999, 0, "Normal")
end
end))
attack = false
hum.WalkSpeed = storehumanoidWS
end

function Cybersplosion()
attack = true
hum.WalkSpeed = 3
local truescale = 0
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 1)
for i = 0,4,0.1 do
task.wait()
truescale = truescale + 0.2
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
slash(5,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,8,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.01,0.1),-0.1,BrickColor.new("Cyan"))
block(10,"Add",root.CFrame*CFrame.new(0,8,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(truescale,truescale,truescale),0.01,0.01,0.01,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-20),math.rad(0)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(0)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-0.05)*angles(math.rad(0),math.rad(0),math.rad(40)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-40)),.5)
RW.C0=clerp(RW.C0,cf(1.45,1,0.1)*angles(math.rad(180),math.rad(-30),math.rad(-5)),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(-5),math.rad(10),math.rad(-10)),.5)
end
hum.CameraOffset = vt(0,0,0)
CFuncs["Sound"].Create("rbxassetid://260411131", rarm, 7.5, 1)
for i = 0,2,0.1 do
task.wait()
block(10,"Add",rarm.CFrame*CFrame.new(0,-1.5,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.01,0.01,0.01,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-25),math.rad(0)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(0)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-0.05)*angles(math.rad(0),math.rad(0),math.rad(55)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(-55)),.5)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.6)*angles(math.rad(90),math.rad(0),math.rad(-50)),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(-5),math.rad(10),math.rad(-10)),.5)
end
local orb = Instance.new("Part", char)
for i = 0, 4 do
CFuncs["Sound"].Create("rbxassetid://335657174", orb, 10, 0.75)
end
        orb.BrickColor = BrickColor.new("Toothpaste")
        orb.CanCollide = false
        orb.FormFactor = 3
        orb.Name = "Ring"
        orb.Material = "Neon"
        orb.Size = Vector3.new(1, 1, 1)
        orb.Transparency = 0
        orb.TopSurface = 0
        orb.BottomSurface = 0
        local orbm = Instance.new("SpecialMesh", orb)
        orbm.MeshType = "Sphere"
orbm.Name = "SizeMesh"
orbm.Scale = vt(10,10,10)
orb.CFrame = root.CFrame + root.CFrame.lookVector*3
	local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    orb.CFrame.p,                           -- origin
	    (mouse.Hit.p - orb.CFrame.p).unit * 500 -- direction
	) 
	local ignore = orb
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (orb.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, 0)
orb.CFrame = a.CFrame
a:Destroy()
local over = false
local bgui,imgc = createBGCircle(50,orb,MAINRUINCOLOR.Color)
bgui.AlwaysOnTop = true
imgc.Image = "rbxassetid://2059444669"
local at1a = Instance.new("Attachment",orb)
at1a.Position = Vector3.new(0,5,0)
local at2a = Instance.new("Attachment",orb)
at2a.Position = Vector3.new(0,5,0)
local at1b = Instance.new("Attachment",orb)
at1b.Position = Vector3.new(5,0,0)
local at2b = Instance.new("Attachment",orb)
at2b.Position = Vector3.new(-5,0,0)
local tl1 = Instance.new('Trail',orb)
tl1.Attachment0 = at1a
tl1.Attachment1 = at2a
tl1.Texture = "http://www.roblox.com/asset/?id=1049219073"
tl1.LightEmission = 1
tl1.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
tl1.Color = ColorSequence.new(BrickColor.new('Toothpaste').Color)
tl1.Lifetime = 3
local tl2 = tl1:Clone()
tl2.Parent = orb
tl2.Attachment0 = at1b
tl2.Attachment1 = at2b
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if over == false then
hum.CameraOffset = vt(math.random(-10,10)/250,math.random(-10,10)/250,math.random(-10,10)/250)
MagniDamage(orb,25,99999,9999999,0,"Normal",153092213)
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestTorso(orb.CFrame.p, 25)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
slash(10,5,true,"Round","Add","Out",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.15,0.01,0.15),-0.05,BrickColor.new("Toothpaste"))
imgc.ImageTransparency = 0.25 + 0.25 * math.cos(sine / 10)
imgc.Rotation = imgc.Rotation + 10
bgui.Size = UDim2.new(50 + 25 * math.cos(sine / 10),0, 50 + 25 * math.cos(sine / 10),0)
elseif over == true then
break
end
end
end))
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = orb.CFrame.lookVector*350
bv.Parent = orb
coroutine.resume(coroutine.create(function()
wait(1)
over = true
orb.Anchored = true
MagniDamage(orb,125,99999,9999999,0,"Normal",153092213)
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestTorso(orb.CFrame.p, 125)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
for i = 0, 4 do
CFuncs["Sound"].Create("rbxassetid://1368637781", orb, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://763718160", orb, 10, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", orb, 10, 1)
CFuncs["Sound"].Create("rbxassetid://335657174", orb, 10, 1)
end
for i = 0, 2 do
block(3,"Add",orb.CFrame,vt(1,1,1),2.5,2.5,2.5,BrickColor.new("Navy blue"),Color3.new(0,0,0.5))
block(2,"Add",orb.CFrame,vt(1,1,1),2,2,2,BrickColor.new("Cyan"),Color3.new(0,0.5,1))
block(1,"Add",orb.CFrame,vt(1,1,1),1.5,1.5,1.5,BrickColor.new("Toothpaste"),Color3.new(0,1,1))
end
for i = 0, 19 do
slash(math.random(10,55)/10,5,true,"Round","Add","Out",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(50,500)/250,BrickColor.new("Cyan"))
end
imgc.ImageTransparency = 0
for i = 0, 49 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/25,math.random(-10,10)/25,math.random(-10,10)/25)
orbm.Scale = orbm.Scale + vt(1,1,1)
orb.Transparency = orb.Transparency + 0.02
imgc.Rotation = imgc.Rotation + 20
imgc.ImageTransparency = imgc.ImageTransparency + 0.02
bgui.Size = bgui.Size + UDim2.new(15,0,15,0)
end
hum.CameraOffset = vt(0,0,0)
game:GetService("Debris"):AddItem(orb, 10)
end))
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(5),math.rad(-10)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(20),math.rad(-10)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.3,-0.1)*angles(math.rad(5),math.rad(0),math.rad(-45)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(45)),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0)*angles(math.rad(90),math.rad(0),math.rad(50)),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(20),math.rad(10),math.rad(-30)),.5)
end
attack = false
hum.WalkSpeed = 16
end


function CoredOmega()
attack = true
hum.WalkSpeed = 0
bosschatfunc("THIS IS IT!",MAINRUINCOLOR.Color,1)
CFuncs["Sound"].Create("rbxassetid://838392947", root, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 1)
CFuncs["EchoSound"].Create("rbxassetid://1690475123", root, 10, 1,0,10,0.15,0.5,1)
CFuncs["Sound"].Create("rbxassetid://1368598393", char, 2.5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 0.5)
CFuncs["EchoSound"].Create("rbxassetid://1718412034", char, 4, 1,0,10,0.15,0.5,1)
local keptcolor = MAINRUINCOLOR
for i = 0,8,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-20 + 2 * math.cos(sine / 0.2))),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(20 - 2 * math.cos(sine / 0.2))),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3,5 + 0.05 * math.cos(sine / 24))*angles(math.rad(15),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(50 - 2 * math.cos(sine / 12)),math.rad(0 - 2 * math.cos(sine / 12)),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(150),math.rad(80 + 2 * math.cos(sine / 0.2))),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(-150),math.rad(-80 - 2 * math.cos(sine / 0.2))),.5)
end
for i = 0,8,0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
block(10,"Add",root.CFrame*CFrame.new(0,25,0),vt(0,0,0),0.5,0.5,0.5,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-15 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3,5 + 0.05 * math.cos(sine / 24))*angles(math.rad(15),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-25 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.35,1 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(165 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(-10 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.35,1 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(165 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(13 - 3 * math.cos(sine / 45))),.1)
end
shakes(2,4)
for i = 0, 99 do
local dis = CreateParta(char,1,1,"Neon",MAINRUINCOLOR)
dis.CFrame = root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),math.random(-5,5))*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-25000,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(25000,0,0)
local trl = Instance.new('Trail',dis)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(MAINRUINCOLOR.Color)
trl.Lifetime = 5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*math.random(500,2500)
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 5)
end
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,1)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,1.5)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,125,0,0,0,root,false,0,3)
CFuncs["Sound"].Create("rbxassetid://1841058541", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://2095993595", char, 5,0.8)
CFuncs["Sound"].Create("rbxassetid://1841058541", char, 5,1)
hum.CameraOffset = vt(0,0,0)
local distam = 0
coroutine.resume(coroutine.create(function()
for i = 0, 99 do
	wait()
distam = distam + 1
local xa = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xa.Anchored = true
xa.CFrame = root.CFrame*CFrame.new(math.random(-distam,distam),math.random(-distam,distam),math.random(-distam,distam))
game:GetService("Debris"):AddItem(xa, 5)
coroutine.resume(coroutine.create(function()
CamShakeAll(40,100,Character)
local eff = Instance.new("ParticleEmitter",cen)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,120,0),NumberSequenceKeypoint.new(0.1,40,0),NumberSequenceKeypoint.new(0.8,80,0),NumberSequenceKeypoint.new(1,140,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(500)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
wait(5)
eff:Destroy()
end))
for i = 0, 24 do
slash(math.random(15,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(200,300)/150,MAINRUINCOLOR)
end
local rrot = 0
local xam = 1
coroutine.resume(coroutine.create(function()
for i = 0, 14 do
task.wait()
rrot = rrot + 40*xam
xam = xam + 0.25
local bonus = xam
local xa = CreateParta(char,0.5,1,"Neon",BrickColor.random())
xa.Anchored = true
xa.Color = Color3.new(0,0,0)
xa.CFrame = root.CFrame*CFrame.new(0,-3,-rrot/1.75)
local xc = 0
coroutine.resume(coroutine.create(function()
for i = 0, 99 do
	task.wait()
	xc = xc + 0.01
	xa.Color = Color3.new(xc,0,0)
end
xa.Transparency = 1
MagniDamage(xa, 30*bonus, 78*bonus,99*bonus, 0, "Normal")

CamShakeAll(20,100,xa)
end))
end
end))
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/10,math.random(-10,10)/10,math.random(-10,10)/10)
end
hum.CameraOffset = vt(0,0,0)
end))
MagniDamage(xa, 60, 9999,99999, 0, "Normal")
end
end))
attack = false
hum.WalkSpeed = storehumanoidWS
end

	
	
	
	function Krabbo()
attack = true
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
hum.WalkSpeed = 0
MAINRUINCOLOR = BrickColor.new("White")
newThemeCust("rbxassetid://1953265096",0,1,3)
Chat('Yes hello')
bosschatfunc("Yes hello",MAINRUINCOLOR.Color,3)
for i = 0, 14, .1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 - 3 * math.cos(sine / 34))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(20 - 3 * math.cos(sine / 56)),math.rad(0 + 3 * math.cos(sine / 34))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.03 * math.cos(sine / 34),0 + 0.05 * math.cos(sine / 28))*angles(math.rad(0 - 3 * math.cos(sine / 34)),math.rad(0),math.rad(-20 + 3 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3.5 * math.cos(sine / 33)),math.rad(0 + 4 * math.cos(sine / 63)),math.rad(20 - 3 * math.cos(sine / 56))),.1)
RW.C0 = clerp(RW.C0, cf(0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(90 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(-100 - 1 * math.cos(sine / 28))), 0.1)
LW.C0 = clerp(LW.C0, cf(-0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(100 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(90 + 2.5 * math.cos(sine / 28))), 0.1)
end
Chat('I was wondering if you could play that song again')
bosschatfunc("I was wondering if you could play that song again",MAINRUINCOLOR.Color,3)
for i = 0, 10, .1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 - 3 * math.cos(sine / 34))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(20 - 3 * math.cos(sine / 56)),math.rad(0 + 3 * math.cos(sine / 34))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.03 * math.cos(sine / 34),0 + 0.05 * math.cos(sine / 28))*angles(math.rad(0 - 3 * math.cos(sine / 34)),math.rad(0),math.rad(-20 + 3 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3.5 * math.cos(sine / 33)),math.rad(0 + 4 * math.cos(sine / 63)),math.rad(20 - 3 * math.cos(sine / 56))),.1)
RW.C0 = clerp(RW.C0, cf(0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(90 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(-100 - 2.5 * math.cos(sine / 28))), 0.1)
LW.C0 = clerp(LW.C0, cf(-0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(100 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(90 + 2.5 * math.cos(sine / 28))), 0.1)
end
chatfunc("Hmm, which one man?", BrickColor.new("Black").Color)
bosschatfunc("Hmm, which one man?",MAINRUINCOLOR.Color,3)
for i = 0, 10, .1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 - 3 * math.cos(sine / 34))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(20 - 3 * math.cos(sine / 56)),math.rad(0 + 3 * math.cos(sine / 34))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.03 * math.cos(sine / 34),0 + 0.05 * math.cos(sine / 28))*angles(math.rad(0 - 3 * math.cos(sine / 34)),math.rad(0),math.rad(-20 + 3 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3.5 * math.cos(sine / 33)),math.rad(0 + 4 * math.cos(sine / 63)),math.rad(20 - 3 * math.cos(sine / 56))),.1)
RW.C0 = clerp(RW.C0, cf(0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(90 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(-100 - 2.5 * math.cos(sine / 28))), 0.1)
LW.C0 = aclerp(LW.C0,CFrame.new(-1.20745349, 0.562693655, 0.156515986, 0.841866791, -0.539501786, -0.014077506, -0.490290582, -0.753652692, -0.43774724, 0.225555882, 0.375426948, -0.898987949),Alpha)
end
Chat('The one that goes..')
bosschatfunc("The one that goes..",MAINRUINCOLOR.Color,3)
for i = 0, 6, .1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 - 3 * math.cos(sine / 34))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(20 - 3 * math.cos(sine / 56)),math.rad(0 + 3 * math.cos(sine / 34))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.03 * math.cos(sine / 34),0 + 0.05 * math.cos(sine / 28))*angles(math.rad(0 - 3 * math.cos(sine / 34)),math.rad(0),math.rad(-20 + 3 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),math.rad(0 + 4 * math.cos(sine / 63)),math.rad(20 - 3 * math.cos(sine / 56))),.1)
RW.C0 = clerp(RW.C0, cf(0.85, 0.5 + 0.1 * math.cos(sine / 28), -0.65) * angles(math.rad(90 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(-100 - 2.5 * math.cos(sine / 28))), 0.1)
LW.C0=clerp(LW.C0,cf(-1.5 - 0.01 * math.cos(sine / 32),0.5,0 - 0.01 * math.cos(sine / 8))*angles(math.rad(69 + 1 * math.cos(sine / 8)),math.rad(0 - 0.01 * math.cos(sine / 32)),math.rad(-0 + 1 * math.cos(sine / 4))),.1)
end
CamShakeAll(100,100,Character)
CFuncs["Sound"].Create("rbxassetid://147722227", root, 2.5,1)
wait(1)
CFuncs["Sound"].Create("rbxassetid://147722227", root, 5,1)
wait(1)
CFuncs["Sound"].Create("rbxassetid://147722227", root, 7,1)
ModeOfGlitch = 688
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false

RecolorTextAndRename("Waved~",Color3.new(255,255,255),Color3.new(255,255,255),"Fantasy")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,true)
attack = false
kan.TimePosition = 70
end
	function RiddleMeThisRiddleMeThat()-- Who's afraid of the big black IUSFGEYUI8TY8RUFETUYERFYAERFE7RFWAE9RASEVR7YTRWW65ERAY
    attack = true
    hum.WalkSpeed = 0
    storehumanoidWS = 75
    hum.JumpPower = 0
local bgui = Instance.new("BillboardGui",root)
bgui.Size = UDim2.new(25, 0, 25, 0)
local imgc = Instance.new("ImageLabel",bgui)
imgc.BackgroundTransparency = 1
imgc.ImageTransparency = 1
imgc.Size = UDim2.new(1,0,1,0)
imgc.Image = "rbxassetid://866991660"
imgc.ImageColor3 = Color3.new(99/255,95/255,98/255)
local imgc2 = imgc:Clone()
imgc2.Parent = bgui
imgc2.Position = UDim2.new(-0.5,0,-0.5,0)
imgc2.Size = UDim2.new(2,0,2,0)
imgc2.ImageColor3 = Color3.new(180/255,210/255,228/255)
	newThemeCust("rbxassetid://15356710761",0,1.35,1)
    kan.TimePosition = 0
    ModeOfGlitch = 8376532578634534
    --repeat task.wait() until kan.IsLoaded
	Chat('Riddle me this..')
    for i = 0, 14, .1 do
        task.wait()
        RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
        LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
        RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)  
        Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(0,math.rad(-25),0),.1)
		LW.C0 = aclerp(LW.C0,CFrame.new(-1.15619826, 0.410764694, 0.308931053, 0.862226903, -0.506325424, 0.0141164251, 0.451236814, 0.780479908, 0.432708263, -0.230108798, -0.366722882, 0.901423633),Alpha)
		RW.C0 = aclerp(RW.C0,CFrame.new(1.48984146, 0.433965802, -0.137121022, 0.754978359, -0.655723989, -0.00581999123, -0.244246826, -0.272958666, -0.930503726, 0.608564973, 0.703931689, -0.366236359),Alpha)
    end
coroutine.resume(coroutine.create(function()
for i = 0, 14, 0.1 do
		task.wait()
imgc.ImageTransparency = imgc.ImageTransparency + 0.01
imgc.Rotation = imgc.Rotation + 1
imgc2.ImageTransparency = imgc2.ImageTransparency + 0.01
imgc2.Rotation = imgc2.Rotation - 1
bgui.Size = bgui.Size - UDim2.new(0.25, 0, 0.25, 0)
end
bgui:Destroy()
end))
	Chat('Riddle me that..')
    for i = 0, 12, .1 do
        task.wait()
        RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
        LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
        RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)  
        Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(0,math.rad(25),0),.1)
		LW.C0 = aclerp(LW.C0,CFrame.new(-1.25402236, 0.431008309, 0.117451549, 0.884577334, 0.388638854, 0.257842481, 0.312682211, -0.0839776248, -0.946138322, -0.346053123, 0.917555273, -0.195805177),Alpha)
		RW.C0 = aclerp(RW.C0,CFrame.new(1.22954941, 0.384757012, 0.168471783, 0.915931404, 0.401068091, 0.0146304797, -0.379809946, 0.85445267, 0.354478538, 0.129668966, -0.330234885, 0.934949815),Alpha)
    end
	Chat("Who's afraid of the big black..")
   for i = 0, 16, .1 do
        task.wait()
        RH.C0=clerp(RH.C0,cf(1,-1-.2*math.cos(sine/16),0)*angles(0,math.rad(90),0),.1)
        LH.C0=clerp(LH.C0,cf(-1,-1-.2*math.cos(sine/16),.05)*angles(0,math.rad(15),0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.1)
        RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0+.2*math.cos(sine/16)),.1)  
        Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(25),0,0),.1)
		LW.C0 = aclerp(LW.C0,CFrame.new(-1.32246351, 0.253595859, 0.199904889, 0.862232804, -0.506315708, 0.0141151678, 0.451225579, 0.780480325, 0.432719588, -0.230109304, -0.366735876, 0.90141809),Alpha)
		RW.C0 = aclerp(RW.C0,CFrame.new(1.33073413, 0.290129036, 0.183640629, 0.915928423, 0.401075214, 0.0146333817, -0.379820168, 0.854456067, 0.354459614, 0.129661351, -0.330217659, 0.934956849),Alpha)
    end
    CFuncs["Sound"].Create("rbxassetid://206082327", root, 2.5,1)
    CFuncs["Sound"].Create("rbxassetid://847061203", root, 5,1)
    CFuncs["Sound"].Create("rbxassetid://239000203", root, 2.5,1)
    CFuncs["Sound"].Create("rbxassetid://579687077", root, 2.5,0.75)
	
    RecolorTextAndRename("The Big Black",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
    MAINRUINCOLOR = BrickColor.new("Really black")
    sphere(2.5,"Add",root.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
    sphere(10,"Add",root.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
    for i = 0, 49 do
    PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
    end
    for i = 0,3,0.1 do
    sphereMK(2.5,-1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,MAINRUINCOLOR,0)
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(m:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(m2:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Granite"
    end
    end
    for i, v in pairs(m3:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(extrawingmod1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(extrawingmod2:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Glass"
    end
    end
    for i = 0,2,0.1 do
    task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.2)
    LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.2)
    RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0 + 0.05 * math.cos(sine / 28))*angles(math.rad(-30),math.rad(0),math.rad(0)),.2)
    Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.2)
    RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(0 - 2 * math.cos(sine / 0.2)),math.rad(80 + 2 * math.cos(sine / 0.2))),.2)
    LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(0 + 2 * math.cos(sine / 0.2)),math.rad(-80 - 2 * math.cos(sine / 0.2))),.2)
    end
    hum.JumpPower = 50
    hum.WalkSpeed = storehumanoidWS
    attack = false
	end
	
	

function GreedStorm()
attack = true
hum.WalkSpeed = 0 
local keptcolor = MAINRUINCOLOR
	for i = 0,2,0.1 do
		task.wait()
sphere2(8,"Add",LeftArm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Dark green"),BrickColor.new("Deep orange").Color)
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 47),0 + 0.25 * math.cos(sine / 35),7 + 1 * math.cos(sine / 32))* angles(math.rad(0),math.rad(0),math.rad(40)),0.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(5),math.rad(0),math.rad(-40)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(6), math.rad(-20), math.rad(12)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(50), math.rad(40), math.rad(-40)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 9 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 7 * math.cos(sine / 44))),.1)
	end
local RCARD = {2601039380,133919289,115896863,2601039380,133919289,2601039380,115896863}
CFuncs["TimeSound"].Create("rbxassetid://635905061", root, 10, 1,1)
bosschatfunc("My money..",MAINRUINCOLOR.Color,3)
local orb = Instance.new("Part", char)
        orb.BrickColor = keptcolor
        orb.CanCollide = false
        orb.FormFactor = 3
        orb.Name = "Ring"
        orb.Material = "Neon"
        orb.Size = Vector3.new(1, 0.75, 1.25)
        orb.Transparency = 0
        orb.TopSurface = 0
        orb.BottomSurface = 0
        local orbm = Instance.new("SpecialMesh", orb)
        orbm.MeshType = "Brick"
orbm.Name = "SizeMesh"
orbm.Scale = vt(4,4,4)
orb.CFrame = root.CFrame*CFrame.new(0,8,-3) + root.CFrame.lookVector*3
local eff = Instance.new("ParticleEmitter",orb)
coroutine.resume(coroutine.create(function()
	while true do
	task.wait()
	eff.Texture = "rbxassetid://"..RCARD[math.random(1,7)]
	end
end))
eff.LightEmission = 0.95
eff.Color = ColorSequence.new(Color3.new(1,1,1))
eff.Rate = 10000
eff.Lifetime = NumberRange.new(1.5)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.75,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,85)
eff.Drag = 5
eff.Rotation = NumberRange.new(-250,250)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
	local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    orb.CFrame.p,                           -- origin
	    (mouse.Hit.p - orb.CFrame.p).unit * 500 -- direction
	) 
	local ignore = orb
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (orb.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, 0)
orb.CFrame = a.CFrame
a:Destroy()
CFuncs["Sound"].Create("rbxassetid://304448425", orb, 1.5, 0.9)
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = orb.CFrame.lookVector*300
bv.Parent = orb
game:GetService("Debris"):AddItem(orb, 10)
local hitted = false
coroutine.resume(coroutine.create(function()
while true do
task.wait()
if orb.Parent ~= nil and hitted == false then
sphere2(4,"Add",orb.CFrame*CFrame.new(math.random(-1,1),math.random(-1,1),0) - orb.CFrame.lookVector*1.5,vt(3,3,3),-0.03,-0.03,-0.03,MAINRUINCOLOR)
elseif orb.Parent == nil and hitted == true then
break
end
end
end))
local hit =orb.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
	eff.Enabled = false
CamShakeAll(30,50,Character)
CFuncs["Sound"].Create("rbxassetid://232223678", orb, 4.5, 1)
CFuncs["Sound"].Create("rbxassetid://232223678", orb, 2.5, 1)
	MagniDamage(orb, 25*2, 20,30, 0, "Normal")
sphere2(4,"Add",orb.CFrame,vt(4*2,4*2,4*2),0.5*2,0.5*2,0.5*2,MAINRUINCOLOR)
sphere2(3,"Add",orb.CFrame,vt(4*2,4*2,4*2),0.5*2,0.5*2,0.5*2,MAINRUINCOLOR)
sphere2(2,"Add",orb.CFrame,vt(4*2,4*2,4*2),0.5*2,0.5*2,0.5*2,MAINRUINCOLOR)
for i = 0, 9 do
sphere2(4,"Add",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1.5,1,1.5),-0.005,4,-0.005,MAINRUINCOLOR)
end
for i = 0, 49 do
local rsiz = math.random(10,30)
sphereMK(math.random(1,3),1,"Add",orb.CFrame*CFrame.new(math.random(-20,20)/50,math.random(-20,20)/50,math.random(-20,20)/50)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,MAINRUINCOLOR,0)
end
local eff = Instance.new("ParticleEmitter",orb)
coroutine.resume(coroutine.create(function()
	while true do
	task.wait()
	eff.Texture = "rbxassetid://"..RCARD[math.random(1,7)]
	end
end))
eff.LightEmission = 0.95
eff.Color = ColorSequence.new(Color3.new(1,1,1))
eff.Rate = 10000
eff.Lifetime = NumberRange.new(1.5)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.1,15,0),NumberSequenceKeypoint.new(0.8,25,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.8,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(150,350)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-500,500)
coroutine.resume(coroutine.create(function()
	wait(0.25)
	eff.Enabled = false
end))
local hfr,pfr=rayCast(orb.Position,(CFrame.new(orb.Position,orb.Position - Vector3.new(0,1,0))).lookVector,4,char)
orb.Anchored = true
orb.Transparency = 1
coroutine.resume(coroutine.create(function()
if hfr ~= nil then
orb.Size = vt(50,1,50)
orb.Orientation = vt(0,0,0)
orb.CFrame = orb.CFrame*CFrame.new(0,-5,0)
orbm:Destroy()
local firef = eff:Clone()
coroutine.resume(coroutine.create(function()
	while true do
	task.wait()
	firef.Texture = "rbxassetid://"..RCARD[math.random(1,7)]
	end
end))
firef.Parent = orb
firef.VelocitySpread = 50
firef.Rate = 500
firef.Drag = 3
firef.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.2,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
firef.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,1.5,0),NumberSequenceKeypoint.new(0.05,2.5,0),NumberSequenceKeypoint.new(0.4,1,0),NumberSequenceKeypoint.new(1,0,0)})
firef.Speed = NumberRange.new(10,30)
for i = 0, 24 do
wait(0.25)
MagniDamage(orb, 25, 3,6, 0, "Normal")
end
firef.Enabled = false
end
end))
wait(10)
orb:Destroy()
end
end)
	for i = 0,1,0.1 do
		task.wait()
sphere2(8,"Add",LeftArm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("White"),BrickColor.new("Deep orange").Color)
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 47),0 + 0.25 * math.cos(sine / 35),7 + 1 * math.cos(sine / 32))* angles(math.rad(-15),math.rad(0),math.rad(-50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(5),math.rad(0),math.rad(50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(6), math.rad(-20), math.rad(12)), 0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(-20)), 0.5)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 9 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 7 * math.cos(sine / 44))),.1)
	end
hum.WalkSpeed = storehumanoidWS
attack = false
end


	
function TheoriesTran()
	attack = true
	hum.WalkSpeed = 0
newThemeCust("rbxassetid://1485663990",0,1.01,1.25)
MAINRUINCOLOR = BrickColor.new("New Yeller")
local vel = Instance.new("BodyPosition", root)
vel.P = 10000
vel.D = 1000
vel.maxForce = Vector3.new(50000000000, 10e10, 50000000000)
vel.position = root.CFrame.p + vt(0,150,0)
wait(1)
sphere(1,"Divide",root.CFrame,vt(0,0,0),10,MAINRUINCOLOR)
for i = 0, 80, 0.1 do
		task.wait()
PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
sphereMKCharge(1,-1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,BrickColor.new("Black"),0)
hum.CameraOffset = vt(math.random(-10,10)/50,math.random(-10,10)/50,math.random(-10,10)/50)
RH.C0=clerp(RH.C0,cf(1,-0.4 - 0.05 * math.cos(sine / 32),-0.4)*angles(math.rad(5),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.4 - 0.05 * math.cos(sine / 32),-0.4)*angles(math.rad(5),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.02 + 0.02 * math.cos(sine / 32),1 + 0.05 * math.cos(sine / 32))*angles(math.rad(15 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 44))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(22 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),-0.1)*angles(math.rad(160 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(-33 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),-0.1)*angles(math.rad(160 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(33 - 3 * math.cos(sine / 45))),.1)
end
bosschatfunc("THEORETICAL",MAINRUINCOLOR,1)
ModeOfGlitch = 102341
storehumanoidWS = 125
hum.WalkSpeed = 125
rainbowmode = false
chaosmode = false

RecolorTextAndRename("THEORETICAL",BrickColor.new("New Yeller").Color,BrickColor.new("Cyan").Color,"Code")
MAINRUINCOLOR = BrickColor.new("New Yeller")
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Cyan"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,0,BrickColor.new("Cyan"),0,MAINRUINCOLOR,true)
sphere(2.5,"Add",root.CFrame,vt(1,1,1),1,MAINRUINCOLOR)
for i = 0, 49 do
PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
end
vel:Destroy()
local vel2 = Instance.new("BodyPosition", root)
vel2.P = 20000
vel2.D = 1000
vel2.maxForce = Vector3.new(50000000000, 10e10, 50000000000)
vel2.position = root.CFrame.p - vt(0,148,0)
wait(0.5)
sphere(2.5,"Add",root.CFrame,vt(1,1,1),3,MAINRUINCOLOR)
for i = 0, 49 do
PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
end
CFuncs["Sound"].Create("rbxassetid://239000203", root, 4, 1)
CFuncs["Sound"].Create("rbxassetid://1042716828", root, 2, 1)
CFuncs["Sound"].Create("rbxassetid://847061203", root, 3, 1)
coroutine.resume(coroutine.create(function()
wait(0.2)
vel2:Destroy()
end))
hum.WalkSpeed = storehumanoidWS
attack = false
end
function STRIKE()
attack = true
hum.WalkSpeed = 0
bosschatfunc("STRIKE!",MAINRUINCOLOR.Color,1)
for i = 0, 4, 0.1 do
task.wait()
local snap = math.random(1,10)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(-50 + math.random(-10,10))),1)
end
PixelBlockX(5,0.5,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.01,MAINRUINCOLOR,0)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 9 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 7 * math.cos(sine / 44))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1 + 0.1 * math.cos(sine / 28))* angles(math.rad(0),math.rad(0),math.rad(-60)),0.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-50)),.6)
RW.C0=clerp(RW.C0,cf(1.25,0.5,0)*angles(math.rad(0),math.rad(140),math.rad(90)),.4)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(0),math.rad(-30 + 5 * math.cos(sine / 30)),math.rad(-20)),.6)
end
sphere(1,"Add",mouse.Hit*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(1,100000,1),0.6,BrickColor.new("Really red"))
sphere(1,"Add",mouse.Hit,vt(1,1,1),0.8,BrickColor.new("Really red"))
for i = 0, 49 do
PixelBlockX(1,math.random(1,20),"Add",mouse.Hit*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),8,8,8,0.16,BrickColor.new("Really red"),0)
sphereMK(2.5,-1,"Add",mouse.Hit*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,BrickColor.new("Really red"),0)
slash(math.random(10,20)/10,5,true,"Round","Add","Out",mouse.Hit*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-30, 30)), math.rad(math.random(-30, 30)), math.rad(math.random(-40, 40))),vt(0.05,0.01,0.05),math.random(50,60)/250,BrickColor.new("Really red"))
end
for i, v in pairs(FindNearestHead(mouse.Hit.p, 10)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
for i = 0, 2, 0.1 do
task.wait()
local snap = math.random(1,10)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(-50 + math.random(-10,10))),1)
end
PixelBlockX(5,0.5,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.01,MAINRUINCOLOR,0)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 9 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 7 * math.cos(sine / 44))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1 + 0.1 * math.cos(sine / 28))* angles(math.rad(0),math.rad(0),math.rad(-60)),0.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(0),math.rad(0),math.rad(-90)),.6)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(0),math.rad(0),math.rad(89)),.4)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(0),math.rad(-30 + 5 * math.cos(sine / 30)),math.rad(-20)),.6)
end
attack = false
hum.WalkSpeed = storehumanoidWS
end


function SCREEE()
CFuncs["Sound"].Create("rbxassetid://1177999394", root, 10, 1.5)
CamShakeAll(333,999,Character)
end

function Taunt()
	attack = true
	hum.WalkSpeed = 0
	CreateSound("290084602", tors, 10, 1)
	for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cF.N(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.15)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(-30), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, cF.N(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, cF.N(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, cF.N(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-0), Rad(0), Rad(145)), 0.1)
		LW.C0 = clerp(LW.C0, cF.N(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-0), Rad(0), Rad(-145)), 0.1)
	end
	for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cF.N(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(20), Rad(0), Rad(0)), 0.15)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, cF.N(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(20)), 0.15)
		LH.C0 = clerp(LH.C0, cF.N(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-20)), 0.15)
		RW.C0 = clerp(RW.C0, cF.N(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-30), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, cF.N(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-30), Rad(0), Rad(-15)), 0.1)
	end
	attack = false
	hum.WalkSpeed = 16
end

function Taunt2()
	attack = true
	hum.WalkSpeed = 0
	CreateSound("239443642", tors, 10, 1)
fire = Instance.new("Fire",plr.Character.Torso)
flame = Instance.new("Fire",plr.Character["Right Arm"])
dank = Instance.new("Fire",plr.Character["Left Arm"])
sat = Instance.new("Fire",plr.Character.Head)
wait(8)
fire:Destroy()
flame:Destroy()
dank:Destroy()
sat:Destroy()
ModeOfGlitch = 998877
	hum.WalkSpeed = 16
	insanitymode = false
	chaosmode = false
	rainbowmode = false
	glitching = true
	newTheme("rbxassetid://919231299", 20.25, 1, 5.5)
    RecolorTextAndRename("D",Color3.new(1,1,1),Color3.new(0,0,0),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Di",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Dis",Color3.new(1,1,1),Color3.new(0,0,0),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Dist",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Disto",Color3.new(1,1,1),Color3.new(0,0,0),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Distor",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Distort",Color3.new(1,1,1),Color3.new(0,0,0),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Distorte",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Distorted",Color3.new(1,1,1),Color3.new(0,0,0),"Fantasy")
wait(0.02)
    RecolorTextAndRename("Distorted",Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
    MAINRUINCOLOR = BrickColor.new("White")
    sphere(2.5,"Add",root.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
    sphere(10,"Add",root.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
    for i = 0, 49 do
    PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
    end
    for i = 0, 49 do
    PixelBlock(2,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
    end
    for i = 0, 49 do
    PixelBlock(3,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
    end
    for i = 0,3,0.1 do
    sphereMK(2.5,-1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,MAINRUINCOLOR,0)
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(m:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(m2:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Granite"
    end
    end
    for i, v in pairs(m3:GetChildren()) do
    if v:IsA("Part") then
    v.BrickColor = BrickColor.new("Really black")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(extrawingmod1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Glass"
    end
    end
    for i, v in pairs(extrawingmod2:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.BrickColor = BrickColor.new("Dark stone grey")
    v.Material = "Glass"
    end
    end
    for i = 0,2,0.1 do
    task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.2)
    LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.2)
    RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0 + 0.05 * math.cos(sine / 28))*angles(math.rad(-30),math.rad(0),math.rad(0)),.2)
    Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.2)
    RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(0 - 2 * math.cos(sine / 0.2)),math.rad(80 + 2 * math.cos(sine / 0.2))),.2)
    LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(0 + 2 * math.cos(sine / 0.2)),math.rad(-80 - 2 * math.cos(sine / 0.2))),.2)
    end
    hum.JumpPower = 50
    hum.WalkSpeed = storehumanoidWS
	attack = false
	hum.WalkSpeed = 16
end

function ByeBye()
	local target = nil
	local targettorso = nil
	if mouse.Target.Parent ~= char and mouse.Target.Parent.Parent ~= char and mouse.Target.Parent:FindFirstChild("Humanoid") ~= nil then
		if mouse.Target.Parent.Humanoid.PlatformStand == false then
			target = mouse.Target.Parent.Humanoid
			targettorso = mouse.Target.Parent:FindFirstChild("Torso") or mouse.Target.Parent:FindFirstChild("UpperTorso")
			targethead = mouse.Target.Parent:FindFirstChild("Head")
		end
	end
	if target ~= nil then
		targettorso.Anchored = true
		attack = true
		hum.WalkSpeed = 0
		root.CFrame = targettorso.CFrame * CF(0,0,2)
		for i = 0,4.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.15)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.1, 0.7 + 0.05 * Sin(sine / 30), -.6 + 0.025 * Cos(sine / 20)) * angles(Rad(115), Rad(0), Rad(-15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(20), Rad(0), Rad(-25)), 0.1)
		end
		local bloody = Instance.new("ParticleEmitter",targettorso)
		bloody.Color = ColorSequence.new(Color3.new(1, 0, 0), Color3.new(.5, 0, 0))
		bloody.LightEmission = .1
		bloody.Size = NumberSequence.new(0.5, 0)
		bloody.Texture = "http://www.roblox.com/asset/?ID=0"
		aaa = NumberSequence.new({NumberSequenceKeypoint.new(0, 0.2),NumberSequenceKeypoint.new(1, 5)})
		bbb = NumberSequence.new({NumberSequenceKeypoint.new(0, 1),NumberSequenceKeypoint.new(0.0636, 0), NumberSequenceKeypoint.new(1, 1)})
		bloody.Transparency = bbb
		bloody.Size = aaa
		bloody.ZOffset = -.9
		bloody.Acceleration = Vector3.new(0, -5, 0)
		bloody.LockedToPart = false
		bloody.Lifetime = NumberRange.new(0.8)
		bloody.Rate = 255
		bloody.Rotation = NumberRange.new(-100, 100)
		bloody.RotSpeed = NumberRange.new(-100, 100)
		bloody.Speed = NumberRange.new(6)
		bloody.VelocitySpread = 0
		bloody.Enabled=true
		targethead:Remove()
		CreateSound("429400881", targettorso, 5, .8)
		CreateSound("1093102664", targettorso, 10, 1)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(110)), 0.15)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(-110)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.3, 0.7 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(100), Rad(0), Rad(-15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(-5)), 0.1)
		end
		targettorso.Anchored = false
		attack = false
		hum.WalkSpeed = 16
		root.CFrame = targettorso.CFrame * CF(0,0,3)
	end
end


function Dirtface()
	local TARGET = Mouse.Target
	if TARGET ~= nil then
		if TARGET.Parent:FindFirstChildOfClass("Humanoid") then
			local HUM = TARGET.Parent:FindFirstChildOfClass("Humanoid")
			local ROOT = TARGET.Parent:FindFirstChild("HumanoidRootPart") or TARGET.Parent:FindFirstChild("Torso") or TARGET.Parent:FindFirstChild("UpperTorso")
			if ROOT and HUM.Health > 0 then
				local FOE = Mouse.Target.Parent
				local HEAD = FOE:FindFirstChild("Head")
				local HITFLOOR = Raycast(ROOT.Position, (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 4*ROOT.Size.Z, FOE)
				if HEAD and HITFLOOR then
					attack = true
					RootPart.CFrame = ROOT.CFrame*CF(0,0,2)
					CreateSound(235097614, Torso, 2, 3, false)
					Chat('Struggled..')
					CreateSound(160212585, Torso, 10, 1, false)
					for i=0, 0.4, 0.1 do
						task.wait()
						RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 0 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(0), RAD(0), RAD(-25)),0.1)
						Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-10 - 2.5 * COS(SINE / 12)), RAD(0), RAD(25)),0.1)
						RW.C0 = clerp(RW.C0, CF(1.5, 0.5, 0) * ANGLES(RAD(140 - 27 * math.random(0,2)), RAD(0 - 20 * math.random(0,2)), RAD(0 - 7 * math.random(0,2))),0.1)
						LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(0), RAD(0), RAD(0)),0.1)
						RH.C0 = clerp(RH.C0, CF(1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
						LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(-65), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					for i=0, 0.1, 0.1 do
						task.wait()
						RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 0 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(0), RAD(0), RAD(25)),0.1)
						Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-10 - 2.5 * COS(SINE / 12)), RAD(0), RAD(-25)),0.1)
						RW.C0 = clerp(RW.C0, CF(1.5, 0.5, 0) * ANGLES(RAD(140 - 27 * math.random(0,2)), RAD(0 - 20 * math.random(0,2)), RAD(25 - 7 * math.random(0,2))),0.1)
						LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(0), RAD(0), RAD(0)),0.1)
						RH.C0 = clerp(RH.C0, CF(1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(65), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
						LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					local DEAD = false
					local CFRAME = RootPart.CFrame
					CreateSound(260411131, Torso, 2, 3, false)
					coroutine.resume(coroutine.create(function()
						repeat
							task.wait()
							RootPart.CFrame = CFRAME
							HEAD.CFrame = RightArm.CFrame*CF(0,-(1+HEAD.Size.Z/2),0) * ANGLES(RAD(-90), RAD(0), RAD(0))
							HEAD.Velocity = vt(0,0,0)
							HUM.PlatformStand = true
						until DEAD == true
					end))
					for i=0, 0.2, 0.1 do
						task.wait()
						RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 0 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(0), RAD(0), RAD(25)),0.1)
						Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-10 - 2.5 * COS(SINE / 12)), RAD(0), RAD(-25)),0.1)
						RW.C0 = clerp(RW.C0, CF(1.45, 0.5, -0.3) * ANGLES(RAD(140), RAD(0), RAD(-15)), 0.3)
						LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(0), RAD(0), RAD(0)),0.1)
						RH.C0 = clerp(RH.C0, CF(1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(65), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
						LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					for i=0, 1, 0.1 do
						task.wait()
						RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 0 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(0), RAD(0), RAD(-15)),0.1)
						Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 - 2.5 * COS(SINE / 12)), RAD(0), RAD(15)),0.1)
						RW.C0 = clerp(RW.C0, CF(1.45, 0.5, 0) * ANGLES(RAD(60), RAD(0), RAD(0)),0.1)
						LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(0), RAD(0), RAD(0)),0.1)
						RH.C0 = clerp(RH.C0, CF(1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
						LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.01) * ANGLES(RAD(0), RAD(-70), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					local ERUPT = function()
						local HITFLOOR,HITPOS = Raycast(HEAD.CFrame*CF(0,0.2,0).p+VT(0,0.2,0), (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 4*ROOT.Size.X, FOE)
						if HITFLOOR then
							for i = 1, 5 do
								CreateFlyingDebree(HITFLOOR,CF(HITPOS),MRANDOM(1,2),VT(MRANDOM(10,60)/20,MRANDOM(10,60)/20,MRANDOM(10,60)/20),5,MRANDOM(45,85))
							end
							Chunks(HEAD)
						end
					end
					for i=0, 1, 0.1 do
						task.wait()
							RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, -0.75 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(45), RAD(0), RAD(15)),0.1)
							Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 2.5 * COS(SINE / 12)), RAD(MRANDOM(-5,5)), RAD(10)),0.1)
							RW.C0 = clerp(RW.C0, CF(1.45, 0.5, 1) * ANGLES(RAD(60 + MRANDOM(-5,5)), RAD(0), RAD(25 + MRANDOM(-5,5))) * ANGLES(RAD(0), RAD(80), RAD(0)),0.1)
							LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(5), RAD(0), RAD(5)),0.1)
							RH.C0 = clerp(RH.C0, CF(1, -0.25 - 0.05 * COS(SINE / 12), -0.5) * ANGLES(RAD(40), RAD(70), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(0)),0.1)
							LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.3) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					local ATE = false
					local DEPTH = 1
					coroutine.resume(coroutine.create(function()
						repeat
							task.wait()
							RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, -0.75 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(45), RAD(0), RAD(15)),0.1)
							Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 2.5 * COS(SINE / 12)), RAD(MRANDOM(-5,5)), RAD(10)),0.1)
							RW.C0 = clerp(RW.C0, CF(1.45, 1-DEPTH/4, -DEPTH/4) * ANGLES(RAD(60 + MRANDOM(-5,5)), RAD(0), RAD(25 + MRANDOM(-5,5))) * ANGLES(RAD(0), RAD(80), RAD(0)),0.1)
							LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(5), RAD(0), RAD(5)),0.1)
							RH.C0 = clerp(RH.C0, CF(1, -0.25 - 0.05 * COS(SINE / 12), -0.5) * ANGLES(RAD(40), RAD(70), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(0)),0.1)
							LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.3) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
						until ATE == true
					end))
                    coroutine.resume(coroutine.create(function()
					wait(1)
					for i=0, 2, 0.1 do
						task.wait()
							RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, -0.75 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(45), RAD(0), RAD(15)),0.1)
							Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 2.5 * COS(SINE / 12)), RAD(MRANDOM(-5,5)), RAD(10)),0.1)
							RW.C0 = clerp(RW.C0, CF(1.45, 0.5, 1) * ANGLES(RAD(60 + MRANDOM(-5,5)), RAD(0), RAD(25 + MRANDOM(-5,5))) * ANGLES(RAD(0), RAD(80), RAD(0)),0.1)
							LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(5), RAD(0), RAD(5)),0.1)
							RH.C0 = clerp(RH.C0, CF(1, -0.25 - 0.05 * COS(SINE / 12), -0.5) * ANGLES(RAD(40), RAD(70), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(0)),0.1)
							LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.3) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					wait(1)
					for i=0, 2, 0.1 do
						task.wait()
							RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, -0.75 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(45), RAD(0), RAD(15)),0.1)
							Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 2.5 * COS(SINE / 12)), RAD(MRANDOM(-5,5)), RAD(10)),0.1)
							RW.C0 = clerp(RW.C0, CF(1.45, 0.5, 1) * ANGLES(RAD(60 + MRANDOM(-5,5)), RAD(0), RAD(25 + MRANDOM(-5,5))) * ANGLES(RAD(0), RAD(80), RAD(0)),0.1)
							LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(5), RAD(0), RAD(5)),0.1)
							RH.C0 = clerp(RH.C0, CF(1, -0.25 - 0.05 * COS(SINE / 12), -0.5) * ANGLES(RAD(40), RAD(70), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(0)),0.1)
							LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.3) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
					wait(1.5)
					for i=0, 3, 0.1 do
						task.wait()
							RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, -0.75 + 0.05 * COS(SINE / 12)) * ANGLES(RAD(45), RAD(0), RAD(15)),0.1)
							Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 2.5 * COS(SINE / 12)), RAD(MRANDOM(-5,5)), RAD(10)),0.1)
							RW.C0 = clerp(RW.C0, CF(1.45, 0.5, 2) * ANGLES(RAD(60 + MRANDOM(-5,5)), RAD(0), RAD(25 + MRANDOM(-5,5))) * ANGLES(RAD(0), RAD(80), RAD(-15)), 0.1)
							LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * ANGLES(RAD(5), RAD(0), RAD(5)),0.1)
							RH.C0 = clerp(RH.C0, CF(1, -0.25 - 0.05 * COS(SINE / 12), -0.5) * ANGLES(RAD(40), RAD(70), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(0)),0.1)
							LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.05 * COS(SINE / 12), -0.3) * ANGLES(RAD(0), RAD(-85), RAD(0)) * ANGLES(RAD(-1), RAD(0), RAD(0)),0.1)
					end
                    end))
					wait()
					ERUPT()
					ERUPT()
					DEPTH = 2
					wait(2)
					ERUPT()
					DEPTH = 2.5
					wait(2)
					ERUPT()
					DEPTH = 2.5
					wait(1.75)
					CreateSound(159882598, Torso, 10, 0.9, false)
					wait(0.25)
					Chat('D I E')
					wait(1)
					ERUPT()
					ERUPT()
					HEAD:remove()
					DEAD = true
					ApplyDamage(HUM,0,true)
					wait(0.2)
					ATE = true
					attack = false
				end
			end
		end
	end
end



function Sayonara()
	local target = nil
	local targettorso = nil
	if mouse.Target.Parent ~= char and mouse.Target.Parent.Parent ~= char and mouse.Target.Parent:FindFirstChild("Humanoid") ~= nil then
		if mouse.Target.Parent.Humanoid.PlatformStand == false then
			target = mouse.Target.Parent.Humanoid
			targettorso = mouse.Target.Parent:FindFirstChild("Torso") or mouse.Target.Parent:FindFirstChild("UpperTorso")
			targethead = mouse.Target.Parent:FindFirstChild("Head")
			targetrightarm = mouse.Target.Parent:FindFirstChild("Right Arm")
			targetleftarm = mouse.Target.Parent:FindFirstChild("Left Arm")
		end
	end
	if target ~= nil then
		targettorso.Anchored = true
		attack = true
		hum.WalkSpeed = 0
		root.CFrame = targettorso.CFrame * CF(0,0,2.4)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(10), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20), Rad(10), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(10)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-10)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), -.4 + 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(10)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), -.4 + 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(-10)), 0.1)
		end
		do
		CreateSound("429400881", targettorso, 5, 1)
        local ModelArm02 = New("Model", char, "Arm", {})
		local ModelArm03 = New("Model", char, "Arm", {})
        local Humanoid02 = New("Humanoid", ModelArm02, "Humanoid", {})
		local Humanoid03 = New("Humanoid", ModelArm03, "Humanoid", {})
        local Arm02 = targetleftarm:Clone()
		local Arm03 = targetrightarm:Clone()
        targetleftarm.Transparency = 1
		targetrightarm.Transparency = 1
        Arm02.Parent = ModelArm02
		Arm03.Parent = ModelArm03
        for i, v in pairs(Arm02:GetChildren()) do
          v:Destroy()
        end
		for i, v in pairs(Arm03:GetChildren()) do
          v:Destroy()
        end
        local weldArm02 = Instance.new("Weld")
        weldArm02.Parent = Arm02
        weldArm02.Part0 = targetleftarm
        weldArm02.Part1 = Arm02
        weldArm02.C1 = CFrame.new(0, 0, 0)
		local weldArm03 = Instance.new("Weld")
        weldArm03.Parent = Arm03
        weldArm03.Part0 = targetrightarm
        weldArm03.Part1 = Arm03
        weldArm03.C1 = CFrame.new(0, 0, 0)
        for i, v in pairs(target:GetChildren()) do
          if v:IsA("Shirt") then
            v:clone().Parent = ModelArm02
          end
        end
		for i, v in pairs(target:GetChildren()) do
          if v:IsA("Shirt") then
            v:clone().Parent = ModelArm03
          end
        end
		weldArm02.Part0 = la
        weldArm02.C1 = CFrame.new(0, 0, 1.2) * angles(math.rad(90), math.rad(0), math.rad(0))
		weldArm03.Part0 = ra
        weldArm03.C1 = CFrame.new(0, 0, 1.2) * angles(math.rad(90), math.rad(0), math.rad(0))
       
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(-10), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(-10)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(10)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), .6 + 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), .6 + 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(-15)), 0.1)
		end
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(-20), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(-20)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(20)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(180), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(180), Rad(0), Rad(-15)), 0.1)
		end
		CreateSound("541909763", targettorso, 5, .8)
		weldArm02:Destroy()
        Arm02.CanCollide = true
		weldArm03:Destroy()
        Arm03.CanCollide = true
			local bodyVelocity2 = Instance.new("BodyVelocity")
			bodyVelocity2.Velocity = Vector3.new(0, 10, 0) + root.CFrame.LookVector * 50
			bodyVelocity2.P = 5000
			bodyVelocity2.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity2.Parent = Arm02

			local bodyVelocity3 = Instance.new("BodyVelocity")
			bodyVelocity3.Velocity = Vector3.new(0, 10, 0) + root.CFrame.LookVector * 50
			bodyVelocity3.P = 5000
			bodyVelocity3.MaxForce = Vector3.new(8000, 8000, 8000)
			bodyVelocity3.Parent = Arm03

        game:GetService("Debris"):AddItem(bodyVelocity2, 0.05)
		game:GetService("Debris"):AddItem(bodyVelocity3, 0.05)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(20), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(35)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-20)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(95), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(95), Rad(0), Rad(-15)), 0.1)
		end
		ragdoll(targettorso)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(-20), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.3 - 0.1 * Cos(sine / 20), -.4 + 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(90)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(20)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-30), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-30), Rad(0), Rad(-15)), 0.1)
		end
		targettorso:Remove()
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, -2.5, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(35), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.2 - 0.1 * Cos(sine / 20), -.5 + 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(90)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-35)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-55), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-55), Rad(0), Rad(-15)), 0.1)
		end
		end
		targettorso.Anchored = false
		attack = false
		hum.WalkSpeed = 16
		root.CFrame = targettorso.CFrame * CF(0,0,3.4)
	end
end

function AlohaMyFriend()
	local target = nil
	local targettorso = nil
	if mouse.Target.Parent ~= char and mouse.Target.Parent.Parent ~= char and mouse.Target.Parent:FindFirstChild("Humanoid") ~= nil then
		if mouse.Target.Parent.Humanoid.PlatformStand == false then
			target = mouse.Target.Parent.Humanoid
			targettorso = mouse.Target.Parent:FindFirstChild("Torso") or mouse.Target.Parent:FindFirstChild("UpperTorso")
			targethead = mouse.Target.Parent:FindFirstChild("Head")
		end
	end
	if target ~= nil then
		targettorso.Anchored = true
		attack = true
		hum.WalkSpeed = 0
		root.CFrame = targettorso.CFrame * CF(0,0,2.6)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(20)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(-20)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.1, 0.7 + 0.05 * Sin(sine / 30), -.6 + 0.025 * Cos(sine / 20)) * angles(Rad(115), Rad(0), Rad(-15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(25), Rad(0), Rad(-15)), 0.1)
		end
		local ModelHead01 = New("Model", char, "Dead", {})
        local Humanoid01 = New("Humanoid", ModelHead01, "Humanoid", {})
        local Head01 = targethead:Clone()
        targethead.Transparency = 1
        Head01.Parent = ModelHead01
        local weldHead01 = Instance.new("Weld")
        weldHead01.Parent = Head01
        weldHead01.Part0 = targethead
        weldHead01.Part1 = Head01
        weldHead01.C1 = CFrame.new(0, 0, 0)
		targethead.face:Remove()
		weldHead01.Part0 = ra
      
		targettorso:BreakJoints()
		CreateSound("314390675", targettorso, 5, .7)
		for i = 0,4.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(20)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(-20)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.1, 0.7 + 0.05 * Sin(sine / 30), -.6 + 0.025 * Cos(sine / 20)) * angles(Rad(145), Rad(0), Rad(-15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(25), Rad(0), Rad(-15)), 0.1)
		end
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(-40)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(40)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.4, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(185), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(45), Rad(0), Rad(-15)), 0.1)
		end
		CreateSound("541909763", targettorso, 5, .8)
		weldHead01:Destroy()
        Head01.CanCollide = true
		local bodyVelocity2 = Instance.new("BodyVelocity")
		bodyVelocity2.Velocity = Vector3.new(0, 10, 0) + root.CFrame.LookVector * 50
		bodyVelocity2.P = 5000
		bodyVelocity2.MaxForce = Vector3.new(8000, 8000, 8000)
		bodyVelocity2.Parent = Head01
        game:GetService("Debris"):AddItem(bodyVelocity2, 0.05)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(40)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(-40)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.4, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(65), Rad(0), Rad(-15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(45), Rad(0), Rad(-15)), 0.1)
		end
		targettorso.Anchored = false
		attack = false
		hum.WalkSpeed = 16
		root.CFrame = targettorso.CFrame * CF(0,0,3.4)
	end
end

function Good_Bye()
	local target = nil
	local targettorso = nil
	if mouse.Target.Parent ~= char and mouse.Target.Parent.Parent ~= char and mouse.Target.Parent:FindFirstChild("Humanoid") ~= nil then
		if mouse.Target.Parent.Humanoid.PlatformStand == false then
			target = mouse.Target.Parent.Humanoid
			targettorso = mouse.Target.Parent:FindFirstChild("Torso") or mouse.Target.Parent:FindFirstChild("UpperTorso")
			targethead = mouse.Target.Parent:FindFirstChild("Head")
		end
	end
	if target ~= nil then
		targettorso.Anchored = true
		attack = true
		hum.WalkSpeed = 0
		root.CFrame = targettorso.CFrame * CF(0,0,3)
		for i = 0,6.2,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(-45)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20), Rad(0), Rad(45)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.3, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(25)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(25), Rad(0), Rad(-15)), 0.1)
		end
		CreateSound("429400881", targettorso, 5, 1)
		CreateSound("131038747", targettorso, 7, 1)
		for i = 0,8,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(1.2, -2.5, -0.2) * angles(Rad(0), Rad(0), Rad(40)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20), Rad(10), Rad(-45)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.8, -0.4) * RHCF * angles(Rad(-5), Rad(0), Rad(-20)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.8, -0.2) * LHCF * angles(Rad(-5), Rad(0), Rad(56)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.51 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(40)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(25), Rad(0), Rad(-15)), 0.1)
		end
		targettorso:BreakJoints()
		for i = 0,9,0.1 do
			task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.15)
		tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20), Rad(0), Rad(-20)), 0.3)
		RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-5), Rad(0), Rad(0)), 0.15)
		LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-5), Rad(0), Rad(-0)), 0.15)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(90), Rad(0), Rad(15)), 0.1)
		LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(25), Rad(0), Rad(-15)), 0.1)
		end
		targettorso.Anchored = false
		attack = false
		hum.WalkSpeed = 16
		root.CFrame = targettorso.CFrame * CF(0,0,3.4)
	end
end

function Flame_Burst()
	local target = nil
	local targettorso = nil
	if mouse.Target.Parent ~= char and mouse.Target.Parent.Parent ~= char and mouse.Target.Parent:FindFirstChild("Humanoid") ~= nil then
		if mouse.Target.Parent.Humanoid.PlatformStand == false then
			target = mouse.Target.Parent.Humanoid
			target2 = mouse.Target.Parent
			targettorso = mouse.Target.Parent:FindFirstChild("Torso") or mouse.Target.Parent:FindFirstChild("UpperTorso")
		end
	end
	if target ~= nil then
		attack = true
		hum.WalkSpeed = 0
		for i = 0, 3.4, 0.1 do
			task.wait()
			hum.WalkSpeed = 0
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0 - 0.04 * Sin(sine / 24) * Player_Size, 0 + 0.04 * Sin(sine / 12) * Player_Size, 0 + 0.05 * Player_Size * Cos(sine / 12)) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(0 - 2.5 * Sin(sine / 24)), Rad(45)), 0.1)
			tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15), Rad(0), Rad(-45)), 0.1)
			RH.C0 = clerp(RH.C0, CF(1 * Player_Size, -1 * Player_Size - 0.06  - 0.05 * Player_Size * Cos(sine / 12), -0.01 * Player_Size) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(79), Rad(0)) * angles(Rad(-6 - 2.5 * Sin(sine / 24)), Rad(0), Rad(0)), 0.1)
			LH.C0 = clerp(LH.C0, CF(-1 * Player_Size, -1 * Player_Size - 0.06  - 0.05 * Player_Size * Cos(sine / 12), -0.01 * Player_Size) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(-79), Rad(0)) * angles(Rad(-6 + 2.5 * Sin(sine / 24)), Rad(0), Rad(0)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.02 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(90), Rad(-15), Rad(46 + 4.5 * Sin(sine / 12))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.5 * Player_Size, 0.5 + 0.02 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(25), Rad(-.6), Rad(-46 - 4.5 * Sin(sine / 12))), 0.1)
		end
		--targettorso:BreakJoints()
		for i = 0, 3.4, 0.1 do
			task.wait()
			hum.WalkSpeed = 0
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0 - 0.04 * Sin(sine / 24) * Player_Size, 0 + 0.04 * Sin(sine / 12) * Player_Size, 0 + 0.05 * Player_Size * Cos(sine / 12)) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(0 - 2.5 * Sin(sine / 24)), Rad(45)), 0.1)
			tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15), Rad(0), Rad(-45)), 0.1)
			RH.C0 = clerp(RH.C0, CF(1 * Player_Size, -1 * Player_Size - 0.06  - 0.05 * Player_Size * Cos(sine / 12), -0.01 * Player_Size) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(79), Rad(0)) * angles(Rad(-6 - 2.5 * Sin(sine / 24)), Rad(0), Rad(0)), 0.1)
			LH.C0 = clerp(LH.C0, CF(-1 * Player_Size, -1 * Player_Size - 0.06  - 0.05 * Player_Size * Cos(sine / 12), -0.01 * Player_Size) * angles(Rad(0 - 2.5 * Sin(sine / 12)), Rad(-79), Rad(0)) * angles(Rad(-6 + 2.5 * Sin(sine / 24)), Rad(0), Rad(0)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.5 * Player_Size, 0.5 + 0.02 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(135), Rad(-.6), Rad(46 + 4.5 * Sin(sine / 12))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.5 * Player_Size, 0.5 + 0.02 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(25), Rad(-.6), Rad(-46 - 4.5 * Sin(sine / 12))), 0.1)
		end
		for i, v in pairs(target2:GetChildren()) do
			if(not char:IsAncestorOf(v))then
				local hum = (v and v.Parent and v.Parent:FindFirstChildOfClass'Humanoid')
				local hedder = (v and v.Parent and v.Parent:FindFirstChild'Head')
				if(hum and hedder and hum.Health > 0)then
				Eviscerate(v.Parent)
			end
			end
		end
		attack = false
		hum.WalkSpeed = 16
	end
end

function Taunt10000()
    attack = true
    CreateSound("649634100", hed, 10, 0.5)
    for i = 0, 6, 0.1 do
        task.wait()
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 2 + 0.25* Player_Size * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.05)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-25 - 6.5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.05)
        RH.C0 = clerp(RH.C0, CF(1.1* Player_Size, -0.6 - 0.15 * Cos(sine / 20)* Player_Size, -0.3* Player_Size) * angles(Rad(0), Rad(76), Rad(0)) * angles(Rad(-8.5), Rad(0), Rad(-15)), 0.05)
        LH.C0 = clerp(LH.C0, CF(-1.1* Player_Size, -0.6 - 0.15 * Cos(sine / 20)* Player_Size, -0.3* Player_Size) * angles(Rad(0), Rad(-76), Rad(0)) * angles(Rad(-8.5), Rad(15), Rad(45)), 0.05)
        RW.C0 = clerp(RW.C0, CF(.7* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, -.6* Player_Size) * angles(Rad(0), Rad(-.6), Rad(-135)), 0.2)
        LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.08 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(5), Rad(-.6), Rad(-75)), 0.05)
    end
    attack = false
end

function kickcombo() 
 attack = true
 so("http://www.roblox.com/asset/?id=1452040709", RightLeg, 3, 1)
     WaveEffecte(BrickColor.new("White"), root.CFrame * CFrame.new(0, -1, 0) * euler(0, math.random(-50, 50), 0), 1, 1, 1, 1, 0.5, 1, 0.05)
      for i = 0, 7.14, 0.1 do
        task.wait()
        SphereEffect(BrickColor.new("White"),rl.CFrame*angles(math.random(-50,50),math.random(-50,50),math.random(-50,50)),1,5,1,.05,4,.05,0.03)
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, -0.8) * angles(math.rad(24), math.rad(0), math.rad(0)), 0.2)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(0)), 0.2)
        RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-20), math.rad(0), math.rad(36)), 0.3)
        LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-20), math.rad(0), math.rad(-36)), 0.3)
        RH.C0 = clerp(RH.C0, CFrame.new(1, -0.6, -0.3) * RHCF * angles(math.rad(0), math.rad(0), math.rad(-28)), 0.2)
        LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.2, -0.5) * LHCF * angles(math.rad(0), math.rad(0), math.rad(-34)), 0.2)
      end
local Cracking = Cso("292536356", tors, 10, 1)
 for i = 0, 7.14, 0.1 do
        task.wait()
		hum.CameraOffset = hum.CameraOffset:lerp(Vector3.new(math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8)),0.34)
		Aura(5, 0.15, "Add" , root.CFrame * CF(Mrandom(-12, 12), -6, Mrandom(-12, 12)) * angles(Rad(90 + Mrandom(-12, 12)), 0, 0), 1.5, 1.5, 10, -0.015, BrickC"Lime green", 0, "Sphere")
		WaveEffecte(BrickColor.new("Lime green"), root.CFrame * CFrame.new(0, -6, 0) * euler(0, math.random(-25, 25), 0), 1, 1, 1, 1, 0.2, 1, 0.05)
        SphereEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-50,50),math.random(-50,50),math.random(-50,50)),1,5,1,.05,4,.05,0.03)
		SphereEffect(BrickColor.new("Lime green"),ll.CFrame*angles(math.random(-50,50),math.random(-50,50),math.random(-50,50)),1,5,1,.05,4,.05,0.03)
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, -0.8) * angles(math.rad(24), math.rad(0), math.rad(0)), 0.2)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(math.rad(30), math.rad(0), math.rad(0)), 0.2)
        RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(20), math.rad(0), math.rad(36)), 0.3)
        LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(20), math.rad(0), math.rad(-36)), 0.3)
        RH.C0 = clerp(RH.C0, CFrame.new(1, -0.6, -0.3) * RHCF * angles(math.rad(0), math.rad(0), math.rad(-28)), 0.2)
        LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.2, -0.5) * LHCF * angles(math.rad(0), math.rad(0), math.rad(-34)), 0.2)
      end
      Cracking.Playing = false
      so("http://www.roblox.com/asset/?id=197161452", char, 3, 0.8)
              so("http://www.roblox.com/asset/?id=158475221", RightLeg, 1, 1.3)
              SphereEffect(BrickColor.new("Lime green"),tors.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,38,38,38,0.08)
       local velo=Instance.new("BodyVelocity")
                velo.velocity=vt(0,27,0)
                velo.P=11000
                velo.maxForce=Vector3.new(math.huge, math.huge, math.huge)
                velo.Parent=root
                game:GetService("Debris"):AddItem(velo,1.24)



con5=hum.Touched:connect(function(hit)
if hit.Parent:FindFirstChildOfClass("Humanoid") ~= nil then
if attackdebounce == false then
attackdebounce = true  
coroutine.resume(coroutine.create(function()
    for i = 0,1.5,0.1 do
        task.wait()
 hit.Parent.Head.CFrame = root.CFrame * CFrame.new(0,3.4,-1.8)
end
end))

MagniDamage(rl, 4, 24,30, 0, "Normal",153092213)
 RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
SphereEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,3,3,3,0.06)
coroutine.resume(coroutine.create(function()
for i = 0,1,0.1 do
task.wait()
hum.CameraOffset = hum.CameraOffset:lerp(Vector3.new(math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8)),0.34)
end
end))
 wait(0.09)
attackdebounce = false
end
end
end)
for i = 0, 9.11, 0.2 do
        task.wait()
        BlockEffect(BrickColor.new("Lime green"), rl.CFrame*CF(0,-1,0), 2, 2, 2, 3.5, 3.5, 3.5, 0.05)
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, 0.1+0.12*i) * angles(math.rad(-10-95*i), math.rad(0), math.rad(0)), 0.42)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(math.rad(-43), math.rad(0), math.rad(0)), 0.42)
        RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-8), math.rad(0), math.rad(60)), 0.35)
        LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-8), math.rad(0), math.rad(-60)), 0.35)
        RH.C0 = clerp(RH.C0, CFrame.new(1, -0.5, 0) * RHCF * angles(math.rad(0), math.rad(0), math.rad(20+10*i)), 0.42)
        LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.5, -0.4) * LHCF * angles(math.rad(0), math.rad(0), math.rad(24)), 0.42)
      end
con5:disconnect()
con5=hum.Touched:connect(function(hit)
if hit.Parent:FindFirstChildOfClass("Humanoid") ~= nil then
if attackdebounce == false then
attackdebounce = true  
coroutine.resume(coroutine.create(function()
    for i = 0,1.5,0.1 do
        task.wait()
 hit.Parent.Head.CFrame = root.CFrame * CFrame.new(0,1.1,-1.8)
end
end))
MagniDamage(hit, 4, 24,30, 0, "Normal",153092213)
so("http://roblox.com/asset/?id=636494529",rl,2,1.6)
 RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
SphereEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,3,3,3,0.06)
coroutine.resume(coroutine.create(function()
for i = 0,1,0.1 do
task.wait()
hum.CameraOffset = hum.CameraOffset:lerp(Vector3.new(math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8)),0.34)
end
end))
wait(0.08)
attackdebounce = false
end
end
end)
so("http://www.roblox.com/asset/?id=158475221", RightLeg, 1, 1.3)
          for i = 0, 9.14, 0.3 do
        task.wait()
        root.Velocity = root.CFrame.lookVector * 20
        BlockEffect(BrickColor.new("Lime green"), ll.CFrame*CF(0,-1,0), 2, 2, 2, 3.5, 3.5, 3.5, 0.05)
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, -0.87) * angles(math.rad(53), math.rad(8), math.rad(0-54*i)), 0.35)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(math.rad(12), math.rad(0), math.rad(24)), 0.35)
        RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(12), math.rad(0), math.rad(62)), 0.35)
        LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.3, 0) * angles(math.rad(12), math.rad(0), math.rad(-23)), 0.35)
        RH.C0 = clerp(RH.C0, CFrame.new(1, -0.17, -0.4) * RHCF * angles(math.rad(7), math.rad(0), math.rad(4)), 0.35)
        LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.13, -0.6) * LHCF * angles(math.rad(-64-7*i), math.rad(0), math.rad(0-9*i)), 0.35)
      end
con5:disconnect()
 con5=hum.Touched:connect(function(hit)
if hit.Parent:FindFirstChildOfClass("Humanoid") ~= nil then
if attackdebounce == false then
attackdebounce = true  
coroutine.resume(coroutine.create(function()
for i = 0,1.5,0.1 do
task.wait()
hit.Parent.Head.CFrame = root.CFrame * CFrame.new(0,1.1,-1.8)
end
end))
MagniDamage(hit, 4, 24,30, 0, "Normal",153092213)
so("http://roblox.com/asset/?id=636494529",rl,2,1.6)
RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
RingEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,.2,2,.2,0.06)
SphereEffect(BrickColor.new("Lime green"),rl.CFrame*angles(math.random(-360,360),math.random(-360,360),math.random(-360,360)),1,5,1,3,3,3,0.06)
coroutine.resume(coroutine.create(function()
for i = 0,1,0.1 do
task.wait()
hum.CameraOffset = hum.CameraOffset:lerp(Vector3.new(math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8),math.random(-0.55*1.8,0.55*1.8)),0.34)
end
end))
wait(0.05)
attackdebounce = false
end
end
end)
so("http://www.roblox.com/asset/?id=158475221", RightLeg, 1, 1.3)
for i = 0, 15.14, 0.32 do
task.wait()
root.Velocity = root.CFrame.lookVector * 20
BlockEffect(BrickColor.new("Lime green"), ll.CFrame*CF(0,-1,0), 2, 2, 2, 3.5, 3.5, 3.5, 0.05)
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, -0.87) * angles(math.rad(-21-50*i), math.rad(8+20*i), math.rad(0-90*i)), 0.35)
tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(math.rad(12), math.rad(0), math.rad(24)), 0.35)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(12), math.rad(0), math.rad(62)), 0.35)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.3, 0) * angles(math.rad(12), math.rad(0), math.rad(-23)), 0.35)
RH.C0 = clerp(RH.C0, CFrame.new(1, -0.17, -0.4) * RHCF * angles(math.rad(7), math.rad(0), math.rad(4)), 0.35)
LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.13, -0.6) * LHCF * angles(math.rad(-64-2*i), math.rad(0), math.rad(0-4*i)), 0.35)
end
attack = false
con5:disconnect()
end




function CalMets()
attack = true
hum.WalkSpeed = 0
	local lookavec = 0 
	local mult = 1
	local keptcolor = MAINRUINCOLOR
CFuncs["Sound"].Create("rbxassetid://136007472", root, 7, 1.25)
for i = 0,4,0.1 do
		task.wait()
slash(math.random(25,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,10,1)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.2,0.01,0.2),-0.2,keptcolor)
sphere2(3,"Add",root.CFrame*CFrame.new(0,10,0) + root.CFrame.lookVector*1,vt(3,3,3),0.06,0.06,0.06,MAINRUINCOLOR)
            RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 5 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 44))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),1 + 0.15 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-35),math.rad(0),math.rad(0)),.1)
RW.C0 = clerp(RW.C0, CFrame.new(1.25, 1, -0.5) * angles(math.rad(170), math.rad(0), math.rad(-20)), 0.1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.25, 1, -0.5) * angles(math.rad(170), math.rad(0), math.rad(20)), 0.1)
end
sphere2(2,"Add",root.CFrame*CFrame.new(0,10,0) + root.CFrame.lookVector*1,vt(3,3,3),0.6,0.6,0.6,keptcolor)
sphere2(4,"Add",root.CFrame*CFrame.new(0,10,0) + root.CFrame.lookVector*1,vt(3,3,3),0.6,0.6,0.6,keptcolor)
sphere2(3,"Add",root.CFrame*CFrame.new(0,10,0) + root.CFrame.lookVector*1,vt(1,10000,1),0.06,0.06,0.06,keptcolor)
local elocacenter = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
elocacenter.Anchored = true
elocacenter.CFrame = root.CFrame*CFrame.new(0,150,0)
local eloca1 = CreateParta(elocacenter,1,1,"SmoothPlastic",BrickColor.random())
eloca1.Anchored = true
eloca1.CFrame = elocacenter.CFrame
local at1 = Instance.new("Attachment",eloca1)
at1.Position = vt(0,30,0)
local at2 = Instance.new("Attachment",eloca1)
at2.Position = vt(0,-30,0)
local at1b = Instance.new("Attachment",eloca1)
at1b.Position = vt(0,0,180)
local at2b = Instance.new("Attachment",eloca1)
at2b.Position = vt(0,0,-180)
local trl = Instance.new('Trail',eloca1)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(keptcolor.Color)
trl.Lifetime = 4
local trl2 = trl:Clone()
trl2.Parent = eloca1
trl2.Attachment0 = at1b
trl2.Attachment1 = at2b
trl2.Texture = "rbxassetid://2108945559"
trl2.Lifetime = 2
local eff = Instance.new("ParticleEmitter",eloca1)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,3)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,50,0),NumberSequenceKeypoint.new(0.2,5,0),NumberSequenceKeypoint.new(0.8,5,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
local eloca2 = eloca1:Clone()
eloca2.Parent = elocacenter
local eloca3 = eloca1:Clone()
eloca3.Parent = elocacenter
local eloca4 = eloca1:Clone()
eloca4.Parent = elocacenter
shakes(0.5,0.5)
sphere2(2,"Add",elocacenter.CFrame,vt(1,1,1),2,2,2,keptcolor)
sphere2(3,"Add",elocacenter.CFrame,vt(1,1,1),4,4,4,keptcolor)
sphere2(4,"Add",elocacenter.CFrame,vt(1,1,1),5,5,5,keptcolor)
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),6,6,6,keptcolor)
sphere2(3,"Add",elocacenter.CFrame,vt(1,1,1),25,0.1,25,keptcolor)
sphere2(4,"Add",elocacenter.CFrame,vt(1,1,1),25,0.1,25,keptcolor)
CFuncs["Sound"].Create("rbxassetid://419447292", char, 4, 1)
local effx = Instance.new("ParticleEmitter",elocacenter)
effx.Texture = "rbxassetid://144580273" -- 144580273 74564879
effx.LightEmission = 1
effx.Color = ColorSequence.new(keptcolor.Color)
effx.Rate = 500000
effx.Lifetime = NumberRange.new(0.25,0.75)
effx.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,200,0)})
effx.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.5,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effx.Speed = NumberRange.new(0,10)
effx.Drag = 5
effx.Rotation = NumberRange.new(-500,500)
effx.VelocitySpread = 9000
effx.RotSpeed = NumberRange.new(-50,50)
coroutine.resume(coroutine.create(function()
	wait(0.05)
	effx.Enabled = false
end))
coroutine.resume(coroutine.create(function()
for i = 0, 9, 0.1 do
	task.wait()
	mult = mult + 0.5
lookavec = lookavec + 0.1*mult
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
for i = 0, 19 do
for i = 0, 1, 0.1 do
	task.wait()
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
local lb = Instance.new("Part")
lb.Color = keptcolor.Color
lb.CanCollide = false
lb.Material = "Neon"
lb.Anchored = true
lb.TopSurface = 0
lb.BottomSurface = 0
lb.Transparency = 0
lb.Size = vt(1,1,1)
lb.CFrame = elocacenter.CFrame*CFrame.new(math.random(-150,150),0,math.random(-150,150))*CFrame.Angles(math.rad(-90 + math.random(-15,15)),0,math.rad(math.random(-15,15)))
lb.Anchored = false
 lb.Parent = char
local thingery = Instance.new("SpecialMesh",lb)
     thingery.MeshType = "Sphere"
thingery.Scale = vt(20,20,20)
game:GetService("Debris"):AddItem(lb, 10)
  local bv = Instance.new("BodyVelocity")
  bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
  bv.velocity = lb.CFrame.lookVector*math.random(125,350)
  bv.Parent = lb
sphere(2.5,"Add",lb.CFrame,vt(50,50,0),0.25,keptcolor)
sphere(5,"Add",lb.CFrame,vt(50,50,0),0.5,keptcolor)
CFuncs["Sound"].Create("rbxassetid://633627961",lb, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1002081188", lb, 10, 1)
CFuncs["Sound"].Create("rbxassetid://741272936", lb, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1192402877", lb, 10, 1)
local hitted = false
local tril = Instance.new("ParticleEmitter",lb)
tril.Texture = "rbxassetid://144580273" -- 144580273 74564879
tril.LightEmission = 1
tril.Color = ColorSequence.new(keptcolor.Color)
tril.Rate = 500000
tril.Lifetime = NumberRange.new(0.5,1)
tril.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(1,0,0)})
tril.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.5,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
tril.Speed = NumberRange.new(0,10)
tril.Drag = 5
tril.Rotation = NumberRange.new(-500,500)
tril.VelocitySpread = 9000
tril.RotSpeed = NumberRange.new(-50,50)
game:GetService("Debris"):AddItem(a, 0.1)

coroutine.resume(coroutine.create(function()
lb.Touched:connect(function(hit)
if hitted == false and hit.Parent ~= char then
hitted = true
lb.Transparency = 1
lb.Anchored = true
tril.Enabled = false
CFuncs["EchoSound"].Create("rbxassetid://675172759", lb, 8, 0.8,0,10,0.15,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://782200047", lb, 10, 1.1,0,10,0.15,0.5,1)
MagniDamage(lb, 60, 4500,85000, 0, "Normal")
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestHead(lb.CFrame.p, 50)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
local effx = Instance.new("ParticleEmitter",lb)
effx.Texture = "rbxassetid://144580273" -- 144580273 74564879
effx.LightEmission = 1
effx.Color = ColorSequence.new(keptcolor.Color)
effx.Rate = 500000
effx.Lifetime = NumberRange.new(0.25,0.75)
effx.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,200,0)})
effx.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.5,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effx.Speed = NumberRange.new(0,10)
effx.Drag = 5
effx.Rotation = NumberRange.new(-500,500)
effx.VelocitySpread = 9000
effx.RotSpeed = NumberRange.new(-50,50)
sphere(5,"Add",lb.CFrame,vt(20,20,20),1,keptcolor)
sphere(6,"Add",lb.CFrame,vt(20,20,20),2,keptcolor)
wait(0.05)
effx.Enabled = false
end
end)
end))
end
for i = 0, 9, 0.1 do
	task.wait()
	mult = mult - 0.5
lookavec = lookavec - 0.1*mult
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
for i,v in pairs(elocacenter:GetDescendants()) do
	if v:IsA("ParticleEmitter") then
		v.Enabled = false
	end
end
wait(6)
elocacenter:Destroy()
end))
attack = false
hum.WalkSpeed = storehumanoidWS	
end

function ExtCalbeam()
	local lookavec = 0 
	local mult = 1
	local keptcolor = MAINRUINCOLOR
bosschatfunc("BEGONE!",MAINRUINCOLOR.Color,2)
local dis = CreateParta(char,0,1,"Neon",keptcolor)
for i = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://335657174", dis, 10, 0.5)
end
dis.CFrame = root.CFrame*CFrame.new(0,2,-3)
CreateMesh(dis,"Sphere",4,4,4)
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-2,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(2,0,0)
local trl = Instance.new('Trail',dis)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.FaceCamera = true
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(dis.Color)
trl.Lifetime = 3
local efec = Instance.new("ParticleEmitter",dis)
efec.Texture = "rbxassetid://144580273"
efec.LightEmission = 1
efec.Color = ColorSequence.new(keptcolor.Color)
efec.Rate = 500000
efec.Lifetime = NumberRange.new(1)
efec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,2,0),NumberSequenceKeypoint.new(1,0,0)})
efec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)})
efec.Drag = 5
efec.Rotation = NumberRange.new(-500,500)
efec.VelocitySpread = 9000
efec.RotSpeed = NumberRange.new(-500,500)
local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    dis.CFrame.p,                           -- origin
	    (mouse.Hit.p - dis.CFrame.p).unit * 500 -- direction
	) 
	local ignore = dis
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (dis.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(dis.CFrame.p, position) * CFrame.new(0, 0, 0)
dis.CFrame = a.CFrame
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*250
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 15)
local hitted = false
coroutine.resume(coroutine.create(function()
dis.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
	shakes(1,1)
	efec.Enabled = false
	dis.Anchored = true
	dis.Transparency = 1
	local elocacenter = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
elocacenter.Anchored = true
elocacenter.CFrame = dis.CFrame*CFrame.new(0,1,0)
elocacenter.Orientation = Vector3.new(0,0,0)
local eloca1 = CreateParta(elocacenter,1,1,"SmoothPlastic",BrickColor.random())
eloca1.Anchored = true
eloca1.CFrame = elocacenter.CFrame
local at1 = Instance.new("Attachment",eloca1)
at1.Position = vt(0,20,0)
local at2 = Instance.new("Attachment",eloca1)
at2.Position = vt(0,-20,0)
local at1b = Instance.new("Attachment",eloca1)
at1b.Position = vt(0,0,100)
local at2b = Instance.new("Attachment",eloca1)
at2b.Position = vt(0,0,-100)
local trl = Instance.new('Trail',eloca1)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(keptcolor.Color)
trl.Lifetime = 4
local trl2 = trl:Clone()
trl2.Parent = eloca1
trl2.Attachment0 = at1b
trl2.Attachment1 = at2b
trl2.Texture = "rbxassetid://2108945559"
trl2.Lifetime = 2
local eff = Instance.new("ParticleEmitter",eloca1)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,3)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,50,0),NumberSequenceKeypoint.new(0.2,5,0),NumberSequenceKeypoint.new(0.8,5,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
local eloca2 = eloca1:Clone()
eloca2.Parent = elocacenter
local eloca3 = eloca1:Clone()
eloca3.Parent = elocacenter
local eloca4 = eloca1:Clone()
eloca4.Parent = elocacenter
sphere2(2,"Add",elocacenter.CFrame,vt(1,1,1),2,2,2,keptcolor)
sphere2(3,"Add",elocacenter.CFrame,vt(1,1,1),4,4,4,keptcolor)
sphere2(4,"Add",elocacenter.CFrame,vt(1,1,1),5,5,5,keptcolor)
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),6,6,6,keptcolor)
for i = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://419447292", elocacenter, 8, 1)
CFuncs["Sound"].Create("rbxassetid://1192402877", elocacenter, 10, 0.5)
end
local effx = Instance.new("ParticleEmitter",elocacenter)
effx.Texture = "rbxassetid://144580273" -- 144580273 74564879
effx.LightEmission = 1
effx.Color = ColorSequence.new(keptcolor.Color)
effx.Rate = 500000
effx.Lifetime = NumberRange.new(0.25,0.75)
effx.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,200,0)})
effx.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.5,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effx.Speed = NumberRange.new(0,10)
effx.Drag = 5
effx.Rotation = NumberRange.new(-500,500)
effx.VelocitySpread = 9000
effx.RotSpeed = NumberRange.new(-50,50)
coroutine.resume(coroutine.create(function()
	wait(0.05)
	effx.Enabled = false
end))
coroutine.resume(coroutine.create(function()
for i = 0, 9, 0.1 do
	task.wait()
	mult = mult + 0.5
lookavec = lookavec + 0.06*mult
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
for i = 0, 19, 0.1 do
	task.wait()
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
shakes(1.5,1.5)
MagniDamage(elocacenter, 200, 50,99, 0, "Normal")
coroutine.resume(coroutine.create(function()
for i, v in pairs(FindNearestHead(elocacenter.CFrame.p, 150)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end))
local effe = Instance.new("ParticleEmitter",elocacenter)
effe.Texture = "rbxassetid://2273224484"
effe.LightEmission = 1
effe.Color = ColorSequence.new(keptcolor.Color)
effe.Rate = 500000
effe.Lifetime = NumberRange.new(3,5)
effe.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,150,0),NumberSequenceKeypoint.new(0.2,15,0),NumberSequenceKeypoint.new(0.8,15,0),NumberSequenceKeypoint.new(1,0,0)})
effe.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
effe.Speed = NumberRange.new(250,1200)
effe.Drag = 5
effe.Rotation = NumberRange.new(-500,500)
effe.VelocitySpread = 9000
effe.RotSpeed = NumberRange.new(-50,50)
coroutine.resume(coroutine.create(function()
	effx.Enabled = true
	wait(0.15)
	effx.Enabled = false
	wait(0.25)
	effe.Enabled = false
end))
coroutine.resume(coroutine.create(function()
	local elocor = elocacenter
local lookavec = 0 
	local mult = 1
local elocacenter = CreateParta(elocor,1,1,"SmoothPlastic",BrickColor.random())
elocacenter.Anchored = true
elocacenter.CFrame = elocor.CFrame
local eloca1 = CreateParta(elocacenter,1,1,"SmoothPlastic",BrickColor.random())
eloca1.Anchored = true
eloca1.CFrame = elocacenter.CFrame
local at1 = Instance.new("Attachment",eloca1)
at1.Position = vt(0,10,0)
local at2 = Instance.new("Attachment",eloca1)
at2.Position = vt(0,-10,0)
local trl = Instance.new('Trail',eloca1)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(keptcolor.Color)
trl.Lifetime = 8
local eff = Instance.new("ParticleEmitter",eloca1)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,1)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
local eloca2 = eloca1:Clone()
eloca2.Parent = elocacenter
local eloca3 = eloca1:Clone()
eloca3.Parent = elocacenter
local eloca4 = eloca1:Clone()
eloca4.Parent = elocacenter
coroutine.resume(coroutine.create(function()
for i = 0, 19, 0.1 do
	task.wait()
	mult = mult + 0.25
lookavec = lookavec + 0.05*mult
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/10),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(40+lookavec/5,-15+lookavec*2,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.new(-40-lookavec/5,-15+lookavec*2,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.new(0,-15+lookavec*2,40+lookavec/5)
eloca4.CFrame = elocacenter.CFrame*CFrame.new(0,-15+lookavec*2,-40-lookavec/5)
end
for i,v in pairs(elocacenter:GetDescendants()) do
	if v:IsA("ParticleEmitter") then
		v.Enabled = false
	end
end
wait(6)
elocacenter:Destroy()
end))
end))
CFuncs["Sound"].Create("rbxassetid://763717897", char, 3, 1)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 3, 0.75)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 4, 0.5)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 6,0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 2.5,1)
CFuncs["Sound"].Create("rbxassetid://763718160", char, 3, 0.75)
symbolizeBlink(elocacenter,0,144580273,keptcolor.Color,20,0,0,0,root,true,-5,3)
symbolizeBlink(elocacenter,0,144580273,keptcolor.Color,40,0,0,0,root,true,-5,3)
symbolizeBlink(elocacenter,0,144580273,keptcolor.Color,60,0,0,0,root,true,-5,3)
symbolizeBlink(elocacenter,0,144580273,keptcolor.Color,80,0,0,0,root,true,-5,3)
sphere2(2,"Add",elocacenter.CFrame,vt(10,10000,10),2,2,2,keptcolor)
sphere2(1,"Add",elocacenter.CFrame,vt(10,10000,10),2,2,2,keptcolor)
sphere2(2,"Add",elocacenter.CFrame,vt(10,10,10),5,5,5,keptcolor)
sphere2(2,"Add",elocacenter.CFrame,vt(10,10,10),7.5,7.5,7.5,keptcolor)
sphere2(2,"Add",elocacenter.CFrame,vt(10,10,10),10,10,10,keptcolor)
sphere2(2,"Add",elocacenter.CFrame,vt(10,10,10),2.5,2.5,2.5,keptcolor)
for i = 0, 29 do
		slash(math.random(10,30)/10,5,true,"Round","Add","Out",elocacenter.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,1000)/250,BrickColor.new("White"))
	end
for i = 0, 9, 0.1 do
	task.wait()
	mult = mult - 0.5
lookavec = lookavec - 0.06*mult
sphere2(5,"Add",elocacenter.CFrame,vt(1,1,1),0.05*lookavec/2,0.001,0.05*lookavec/2,keptcolor)
elocacenter.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(5*mult/20),0)
eloca1.CFrame = elocacenter.CFrame*CFrame.new(-lookavec,0,0)
eloca2.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(90),0)*CFrame.new(-lookavec,0,0)
eloca3.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(180),0)*CFrame.new(-lookavec,0,0)
eloca4.CFrame = elocacenter.CFrame*CFrame.Angles(0,math.rad(270),0)*CFrame.new(-lookavec,0,0)
end
for i,v in pairs(elocacenter:GetDescendants()) do
	if v:IsA("ParticleEmitter") then
		v.Enabled = false
	end
end
wait(6)
elocacenter:Destroy()
end))
end
end)
end))	
end


function cutesigh()
attack = true
hum.WalkSpeed = 0
hum.JumpPower = 0
chatfunc("sigh~~",BrickColor.new("Pink").Color)
local blush = Instance.new("Decal",hed)
blush.Texture = "rbxassetid://898404027"
blush.Face = "Front"
CFuncs["Sound"].Create("rbxassetid://294861193", root, 1,1)
for i = 0, 9, 0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(6),math.rad(0),math.rad(25 + 1 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(-35 + 1 * math.cos(sine / 34))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.35,-0.175 + 0.05 * math.cos(sine / 28))*angles(math.rad(35),math.rad(0),math.rad(0)),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-35 - 2.5 * math.cos(sine / 28)),math.rad(10 + 2.5 * math.cos(sine / 75)),math.rad(0)),.2)
RW.C0=clerp(RW.C0,cf(1.35,0.45 + 0.025 * math.cos(sine / 28),-0.2)*angles(math.rad(40),math.rad(0),math.rad(-1)),.2)
LW.C0=clerp(LW.C0,cf(-1.35,0.45 + 0.025 * math.cos(sine / 28),-0.2)*angles(math.rad(40),math.rad(0),math.rad(3)),.2)
end
coroutine.resume(coroutine.create(function()
for i = 0, 49 do
task.wait()
blush.Transparency = blush.Transparency + 0.02
end
blush:Destroy()
end))
hum.WalkSpeed = storehumanoidWS
hum.JumpPower = 50
attack = false
end


function lovesqueal()
attack = true
hum.WalkSpeed = 0
CFuncs["Sound"].Create("rbxassetid://2500548008", root, 1, 1)
local blush = Instance.new("Decal",hed)
blush.Texture = "rbxassetid://898404027"
blush.Face = "Front"
for i = 0, 11, 0.1 do
	task.wait()
	RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(20 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(6),math.rad(0),math.rad(-20 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.2 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(20 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-20 - 5 * math.cos(sine / 37)),math.rad(0 + 14 * math.cos(sine / 58)),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(33 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(3 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(23 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(-3 - 3 * math.cos(sine / 45))),.1)
end
for x = 0, 1 do
for i = 0, 1, 0.2 do
	task.wait()
	RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(-5 - 2 * math.cos(sine / 32))),.3)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(6),math.rad(0),math.rad(5 + 2 * math.cos(sine / 32))),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.05 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(-5 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5 - 5 * math.cos(sine / 37)),math.rad(0 + 14 * math.cos(sine / 58)),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(33 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(3 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.75 + 0.025 * math.cos(sine / 45),-0.6)*angles(math.rad(140 - 3 * math.cos(sine / 73)),math.rad(5 - 1 * math.cos(sine / 55)),math.rad(80 - 3 * math.cos(sine / 45))),.3)
end
for i = 0, 1, 0.2 do
	task.wait()
	RH.C0=clerp(RH.C0,cf(1,-1.025 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(-5 - 2 * math.cos(sine / 32))),.3)
LH.C0=clerp(LH.C0,cf(-1,-1.025 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(6),math.rad(0),math.rad(5 + 2 * math.cos(sine / 32))),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.05 + 0.02 * math.cos(sine / 32),0.025 + 0.05 * math.cos(sine / 32))*angles(math.rad(-5 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5 - 5 * math.cos(sine / 37)),math.rad(0 + 14 * math.cos(sine / 58)),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(33 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(3 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.8 + 0.025 * math.cos(sine / 45),-0.6)*angles(math.rad(140 - 3 * math.cos(sine / 73)),math.rad(5 - 1 * math.cos(sine / 55)),math.rad(80 - 3 * math.cos(sine / 45))),.3)
end
end
coroutine.resume(coroutine.create(function()
for i = 0, 49 do
task.wait()
blush.Transparency = blush.Transparency + 0.02
end
blush:Destroy()
end))
attack = false
hum.WalkSpeed = storehumanoidWS	
end

function WavedOut()
	attack = true
	hum.WalkSpeed = 0
	for i = 0, 6, 0.1 do
		task.wait()				
RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 1.5 - 0.15 * COS(SINE / 24)) * ANGLES(RAD(0), RAD(5 - 25 * SIN(SINE / 15)), RAD(-45)), 0.1)
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15), RAD(0 - 25 * SIN(SINE / 25)), RAD(0 - 25 * SIN(SINE / 25))), .1)
RH.C0 = clerp(RH.C0, CF(1, -1, 0) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
RW.C0 = clerp(RW.C0, cf(1.5* Player_Size, 0.5 + 0.06 * math.sin(sine / 20)* Player_Size, 0* Player_Size) * angles(math.rad(145), math.rad(0), math.rad(15 + 2.5 * math.sin(sine / 20))), 0.12)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
	end
	Magic(5, "Add", mouse.Hit * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 1, maincolor, "Sphere")
	Magic(10, "Add", mouse.Hit * CFrame.new(0, -2.9, 0), Vector3.new(0, 0, 0), 2, maincolor, "Sphere")
	Magic(1, "Add", mouse.Hit, Vector3.new(1, 100000, 1), 0.5, maincolor, "Sphere")
	Magic(1, "Add", mouse.Hit, Vector3.new(1, 1, 1), 0.75, maincolor, "Sphere")
	CamShakeAll(4, 25,Torso)
	for i, v in pairs(FindNearestHead(mouse.Hit.p, 14.5)) do
		if v:FindFirstChild("Head") then
			Eviscerate(v)
		end
	end
	for i = 0, 6, 0.1 do
		task.wait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 1.5 - 0.15 * COS(SINE / 24)) * ANGLES(RAD(0), RAD(5 - 25 * SIN(SINE / 15)), RAD(-45)), 0.1)
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15), RAD(0 - 25 * SIN(SINE / 25)), RAD(0 - 25 * SIN(SINE / 25))), .1)
RH.C0 = clerp(RH.C0, CF(1, -1, 0) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
RW.C0 = clerp(RW.C0, cf(1.5* Player_Size, 0.5 + 0.06 * math.sin(sine / 20)* Player_Size, 0* Player_Size) * angles(math.rad(45), math.rad(0), math.rad(15 + 2.5 * math.sin(sine / 20))), 0.2)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
	end
	attack = false
	hum.WalkSpeed = 10
end

function Waved()
	attack = true
	hum.WalkSpeed = 0
	for i = 0, 9, 0.1 do
		task.wait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 1.5 - 0.15 * COS(SINE / 24)) * ANGLES(RAD(0), RAD(5 - 25 * SIN(SINE / 15)), RAD(-45)), 0.1)
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15), RAD(0 - 25 * SIN(SINE / 25)), RAD(0 - 25 * SIN(SINE / 25))), .1)
RH.C0 = clerp(RH.C0, CF(1, -1, 0) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.06 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(-9), Rad(0), Rad(155 + 25 * Sin(sine / 2.5))), 0.12)
LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
	end
	attack = false
	hum.WalkSpeed = 10
end

function scattercorrupt()
	attack = true
	local rot = 0
	local randomrotations = math.random(1, 2)
	local lookv = 2.5
	local power = 5
	sphere(1, "Add", root.CFrame, vt(1, 100000, 1), 0.5, MAINRUINCOLOR)
	sphere(1, "Add", root.CFrame, vt(1, 1, 1), 0.75, MAINRUINCOLOR)
	for i = 0, 9 do
		sphereMK(1, 1.5, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 10, 10, 45, -0.1,MAINRUINCOLOR,0)
	end
	CFuncs.Sound.Create("rbxassetid://180204650", char, 2.5, 0.6)
	CFuncs.Sound.Create("rbxassetid://233856079", char, 1, 0.5)
	CFuncs.Sound.Create("rbxassetid://1208650519", char, 2.5, 1)
	CFuncs.Sound.Create("rbxassetid://239000203", char, 0.5, 0.75)
	CFuncs.Sound.Create("rbxassetid://579687077", char, 0.5, 0.5)
	local hite = Instance.new("Part", char)
	hite.Anchored = true
	hite.CanCollide = false
	hite.FormFactor = 3
	hite.Name = "Ring"
	hite.Material = "Neon"
	hite.Size = Vector3.new(1, 1, 1)
	hite.Transparency = 1
	hite.TopSurface = 0
	hite.BottomSurface = 0
	hite.CFrame = root.CFrame * CFrame.new(0, -2.5, 0)
	local rem = Instance.new("Part", char)
	rem.Anchored = true
	rem.CanCollide = false
	rem.FormFactor = 3
	rem.Name = "Ring"
	rem.Material = "Neon"
	rem.Size = Vector3.new(1, 1, 1)
	rem.Transparency = 1
	rem.TopSurface = 0
	rem.BottomSurface = 0
	rem.CFrame = hite.CFrame
	local rem2 = rem:Clone()
	rem2.Parent = char
	rem2.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(90), 0)
	local rem3 = rem:Clone()
	rem3.Parent = char
	rem3.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(180), 0)
	local rem4 = rem:Clone()
	rem4.Parent = char
	rem4.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(270), 0)
	hite:Destroy()
	coroutine.resume(coroutine.create(function()
		for i = 0, 24 do
			task.wait(1)
			if randomrotations == 1 then
				rot = rot + 1
			elseif randomrotations == 2 then
				rot = rot - 1
			end
			power = power + 0.5
			lookv = lookv + 7.5
			rem.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(rot), 0)
			rem2.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(90), 0)
			rem3.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(180), 0)
			rem4.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(270), 0)
			orb_spawn_norm(rem.CFrame + rem.CFrame.lookVector * lookv, 3, MAINRUINCOLOR, power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem2.CFrame + rem2.CFrame.lookVector * lookv, 3, MAINRUINCOLOR, power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem3.CFrame + rem3.CFrame.lookVector * lookv, 3, MAINRUINCOLOR, power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem4.CFrame + rem4.CFrame.lookVector * lookv, 3, MAINRUINCOLOR, power, 25, 75, 10, power / 5, 7.5)
		end
	end))
	attack = false
	end
	

function JusticeBeam()
attack = true
bosschatfunc("DEFEND!",MAINRUINCOLOR.Color,1)
CFuncs["EchoSound"].Create("rbxassetid://1436242685", char, 4, 1,0,10,0.15,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://1436242685", root, 7, 1,0,10,0.15,0.5,1)
local rngb = Instance.new("Part", char)
        rngb.Anchored = true
        rngb.BrickColor = origcolor
        rngb.CanCollide = false
        rngb.FormFactor = 3
        rngb.Name = "Ring"
        rngb.Material = "Neon"
        rngb.Size = Vector3.new(1, 0.05, 1)
        rngb.Transparency = 1
        rngb.TopSurface = 0
        rngb.BottomSurface = 0
        local rngmb = Instance.new("SpecialMesh", rngb)
        rngmb.MeshType = "Brick"
rngmb.Name = "SizeMesh"
rngmb.Scale = vt(0,1,0)
 
local orb = rngb:Clone()
orb.Parent = char
orb.Transparency = 0
orb.BrickColor = BrickColor.new("White")
orb.Size = vt(1,1,1)
local orbmish = orb.SizeMesh
orbmish.Scale = vt(0,0,0)
orbmish.MeshType = "Sphere"
 
local orbe = rngb:Clone()
orbe.Parent = char
orbe.Transparency = 0.5
orbe.BrickColor = BrickColor.new("New Yeller")
orbe.Size = vt(1,1,1)
local orbmish2 = orbe.SizeMesh
orbmish2.Scale = vt(0,0,0)
orbmish2.MeshType = "Sphere"
orbe.Color = Color3.new(1,1,1)
 
rngb:Destroy()
--[[CFuncs["Sound"].Create("rbxassetid://136007472", orb, 1.5, 1)
local scaled = 1
for i = 0,5,0.1 do
task.wait()
scaled = scaled - 0.02
if rainbowmode == true then
orbe.Color = Color3.new(r/255,g/255,b/255)
end
orbmish.Scale = orbmish.Scale + vt(scaled/1.5,scaled/1.5,scaled/1.5)
orbmish2.Scale = orbmish2.Scale + vt(scaled*1.1/1.5,scaled*1.1/1.5,scaled*1.1/1.5)
orb.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*11.5
orbe.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*11.5
sphereMKCharge(2.5,-0.5,"Add",orb.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,15,-0.025,MAINRUINCOLOR,25)
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(90)),0.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(-90)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(90)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-20)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-0.5),math.rad(0),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(10),math.rad(0)),.3)
RootPart.CFrame = FaceMouse()[1]
end]]--
for i = 0,5,0.1 do
task.wait()
if rainbowmode == true then
orbe.Color = Color3.new(r/255,g/255,b/255)
end
        if glitching then
            local val = math.random(1,255)
            local color = Color3.fromRGB(val,val,val)
            orbe.Color = color
        end
orb.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*11.5
orbe.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*11.5
RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(-25),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(-25),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1 + 0.2 * math.cos(sine / 28))*angles(math.rad(-25 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.2,0.5,-0.3)*angles(math.rad(90),0,math.rad(-30 + 5.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-1.2,0.5,-0.3)*angles(math.rad(90),0,math.rad(30 - 5.5 * math.cos(sine / 28))),.1)
end
orbe.Transparency = 1
orb.Transparency = 1
orb.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*5
CFuncs["Sound"].Create("rbxassetid://294188875", char, 1, 1)
local a2 = Instance.new("Part",Character)
    a2.Name = "Direction"  
    a2.Anchored = true
    a2.BrickColor = bc("New Yeller")
a2.Color = Color3.new(1,1,1)
a2.Material = "Neon"
a2.Transparency = 0.5
a2.Shape = "Cylinder"
    a2.CanCollide = false
local ba = Instance.new("Part",Character)
    ba.Name = "HitDirect"  
    ba.Anchored = true
    ba.BrickColor = bc("Cool yellow")
ba.Material = "Neon"
ba.Transparency = 1
    ba.CanCollide = false
    local ray = Ray.new(
        orb.CFrame.p,                           -- origin
        root.CFrame.lookVector.unit * 1000 -- direction
    )
    local ignore = Character
    local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
    a2.Transparency = .75
    a2.BottomSurface = 10
    a2.TopSurface = 10
    local distance = (orb.CFrame.p - position).magnitude
    a2.Size = Vector3.new(distance, 1, 1)
    a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
a2.CFrame = a2.CFrame*CFrame.Angles(0,math.rad(90),0)
game:GetService("Debris"):AddItem(a2, 20)
game:GetService("Debris"):AddItem(ba, 20)
local msh2 = Instance.new("SpecialMesh",a2)
msh2.MeshType = "Cylinder"
msh2.Scale = vt(1,6*5,6*5)
 
local snd = CFuncs.Sound.Create("rbxassetid://294188875", Torso, 10, 1)
for i = 1, 80*2 do
RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1 + 0.1 * math.cos(sine / 28))*angles(math.rad(20 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-15),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(110),0,math.rad(20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(110),0,math.rad(-20 - 2.5 * math.cos(sine / 28))),.1)
task.wait()
CameraEnshaking(1,5)
a2.Color = Color3.new(1,1,1)
a2.Transparency = .25
orb.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*4
orbe.CFrame = root.CFrame*CFrame.new(0,0.5,0) + root.CFrame.lookVector*4
    ray = Ray.new(
        orb.CFrame.p,                           -- origin
        root.CFrame.lookVector.unit * 1000 -- direction
    )
hit, position, normal = workspace:FindPartOnRay(ray, ignore)
distance = (orb.CFrame.p - position).magnitude
if typrot == 1 then
rotation = rotation + 2.5
elseif typrot == 2 then
rotation = rotation - 2.5
end
a2.Size = Vector3.new(distance, 1, 1)
a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
a2.CFrame = a2.CFrame*CFrame.Angles(0,math.rad(90),0)
msh2.Scale = msh2.Scale - vt(0,.19,.19)
sphereMK(5,1.5,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),15,15,25,-0.15,MAINRUINCOLOR,0)
sphereMK(5,1.5,"Add",ba.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),15,15,25,-0.15,MAINRUINCOLOR,0)
MagniDamage(ba, 30, 5,25, 0, "Normal")
end
a2:Destroy()
ba:Destroy()
orb:Destroy()
orbe:Destroy()
attack = false
end
	
function BURNINHELL()
    attack = true
    chatfunc("BURN....", BrickColor.random().Color)
    for i = 0,5.2,0.1 do
        task.wait()
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(-20), Rad(0), Rad(0)), 0.15)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(-20 - 2.5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.3)
        RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-4.5), Rad(0), Rad(-20)), 0.15)
        LH.C0 = clerp(LH.C0, CF(-1, -0.3 - 0.1 * Cos(sine / 20), -.4 + 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-6.5), Rad(5 * Cos(sine / 20)), Rad(25)), 0.15)
        RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(135), Rad(0), Rad(-45 - 2.5 * Sin(sine / 20))), 0.1)
        LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(135), Rad(0), Rad(45 + 2.5 * Sin(sine / 20))), 0.1)
    end
    chatfunc("IN....", BrickColor.random().Color)
    wait(2)
    CreateSound("331666100", char, 10, 1)
	sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
	sphere(10, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 2, BrickColor.random())
	sphere(1, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(100, 0.1, 100), 0.01, BrickColor.random())
    chatfunc("HELL!!!!!", BrickColor.random().Color)
    for i, v in pairs(FindNearestHead(tors.CFrame.p, 52.5)) do
        if v:FindFirstChild("Head") then
            Eviscerate(v)
            SoulSteal(v)
        end
    end
    coroutine.resume(coroutine.create(function()
        for i = 0,2.8,0.1 do
            task.wait()
            hum.CameraOffset = Vector3.new(Mrandom(-3,3),Mrandom(-3,3),Mrandom(-3,3))
        end
        for i = 0,1.8,0.1 do
            task.wait()
        hum.CameraOffset = Vector3.new(0,0,0)
        end
    end))
    for i = 0,3.7,0.1 do
        SphereAura(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
        SphereAura(2.5, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
        RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(20), Rad(0), Rad(0)), 0.15)
        tors.Neck.C0 = clerp(tors.Neck.C0, necko * angles(Rad(20 - 2.5 * Sin(sine / 20)), Rad(0), Rad(0)), 0.3)
        RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-4.5), Rad(0), Rad(20)), 0.15)
        LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), -.4 + 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-6.5), Rad(5 * Cos(sine / 20)), Rad(-25)), 0.15)
        RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(-40), Rad(0), Rad(25 - 2.5 * Sin(sine / 20))), 0.1)
        LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(-40), Rad(0), Rad(-25 + 2.5 * Sin(sine / 20))), 0.1)
    end
    wait(.6)
    CreateSound("907332997", hed, 10, 1)
    attack = false
end


function CorruptionEvent()
attack = true
hum.WalkSpeed = 0
CFuncs["Sound"].Create("rbxassetid://838392947", root, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 1)
local keptcolor = MAINRUINCOLOR
for i = 0,4,0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/100,math.random(-10,10)/100,math.random(-10,10)/100)
block(10,"Add",rleg.CFrame*CFrame.new(0,-1,0),vt(1,1,1),0.01,0.01,0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-0.15,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5),math.rad(-20)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(20)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.25,-0.05)*angles(math.rad(-20),math.rad(0),math.rad(10)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-10)),.1)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-5),math.rad(-10),math.rad(20)),.1)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-5),math.rad(10),math.rad(-20)),.1)
end
shakes(0.5,1)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,25,0,0,0,root,false,0,1)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,25,0,0,0,root,false,0,1.5)
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,25,0,0,0,root,false,0,3)
CFuncs["Sound"].Create("rbxassetid://1368637781", root, 3,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 4, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 6, 1)
CFuncs["EchoSound"].Create("rbxassetid://824687369", root, 10, 1.1,0,10,0.25,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://824687369", char, 1.5, 1.1,0,10,0.25,0.5,1)
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",cen)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,120,0),NumberSequenceKeypoint.new(0.1,40,0),NumberSequenceKeypoint.new(0.8,80,0),NumberSequenceKeypoint.new(1,140,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(500)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
wait(5)
eff:Destroy()
	end))
hum.CameraOffset = vt(0,0,0)
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),1,0.01,1,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),2,0.01,2,MAINRUINCOLOR,MAINRUINCOLOR.Color)
for i = 0, 24 do
slash(math.random(15,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(200,500)/250,BrickColor.new("Really black"))
end
local rrot = 0
coroutine.resume(coroutine.create(function()
for i = 0, 4 do
rrot = rrot + 45
local xa = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xa.Anchored = true
local xb = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xb.Anchored = true
local xc = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xc.Anchored = true
local xd = CreateParta(char,1,1,"SmoothPlastic",BrickColor.random())
xd.Anchored = true
CFuncs["Sound"].Create("rbxassetid://824687369", xa, 1,0.75)
CFuncs["Sound"].Create("rbxassetid://822968467", xa, 2,0.95)
CFuncs["Sound"].Create("rbxassetid://822969951", xa, 3,1)
CFuncs["Sound"].Create("rbxassetid://824687369", xb, 1,0.75)
CFuncs["Sound"].Create("rbxassetid://822968467", xb, 2,0.95)
CFuncs["Sound"].Create("rbxassetid://822969951", xb, 3,1)
CFuncs["Sound"].Create("rbxassetid://824687369", xc, 1,0.75)
CFuncs["Sound"].Create("rbxassetid://822968467", xc, 2,0.95)
CFuncs["Sound"].Create("rbxassetid://822969951", xc, 3,1)
CFuncs["Sound"].Create("rbxassetid://824687369", xd, 1,0.75)
CFuncs["Sound"].Create("rbxassetid://822968467", xd, 2,0.95)
CFuncs["Sound"].Create("rbxassetid://822969951", xd, 3,1)
xa.CFrame = root.CFrame*CFrame.Angles(0,math.rad(rrot),0)*CFrame.new(0,-3,-rrot/1.75)
xb.CFrame = root.CFrame*CFrame.Angles(0,math.rad(rrot),0)*CFrame.new(0,-3,rrot/1.75)
xc.CFrame = root.CFrame*CFrame.Angles(0,math.rad(rrot),0)*CFrame.new(-rrot/1.75,-3,0)
xd.CFrame = root.CFrame*CFrame.Angles(0,math.rad(rrot),0)*CFrame.new(rrot/1.75,-3,0)
MagniDamage(xa, 30, 39*rrot/5,65*rrot/2.5, 0, "Normal")
MagniDamage(xb, 30, 39*rrot/5,65*rrot/2.5, 0, "Normal")
MagniDamage(xc, 30, 39*rrot/5,65*rrot/2.5, 0, "Normal")
MagniDamage(xd, 30, 39*rrot/5,65*rrot/2.5, 0, "Normal")
for i = 0, 9 do
slash(math.random(15,50)/10,5,true,"Round","Add","Out",xa.CFrame*CFrame.new(0,-1.5,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(0.01,0.01,0.01),math.random(50,125)/250,BrickColor.new("Really black"))
slash(math.random(15,50)/10,5,true,"Round","Add","Out",xb.CFrame*CFrame.new(0,-1.5,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(0.01,0.01,0.01),math.random(50,125)/250,BrickColor.new("Really black"))
slash(math.random(15,50)/10,5,true,"Round","Add","Out",xc.CFrame*CFrame.new(0,-1.5,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(0.01,0.01,0.01),math.random(50,125)/250,BrickColor.new("Really black"))
slash(math.random(15,50)/10,5,true,"Round","Add","Out",xd.CFrame*CFrame.new(0,-1.5,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(0.01,0.01,0.01),math.random(50,125)/250,BrickColor.new("Really black"))
end
block(1.5,"Add",xa.CFrame*CFrame.new(0,-10,0),vt(30,30,30),0.3,0.3,0.3,keptcolor,keptcolor.Color)
block(1.5,"Add",xb.CFrame*CFrame.new(0,-10,0),vt(30,30,30),0.3,0.3,0.3,keptcolor,keptcolor.Color)
block(1.5,"Add",xc.CFrame*CFrame.new(0,-10,0),vt(30,30,30),0.3,0.3,0.3,keptcolor,keptcolor.Color)
block(1.5,"Add",xd.CFrame*CFrame.new(0,-10,0),vt(30,30,30),0.3,0.3,0.3,keptcolor,keptcolor.Color)
sphere2(2,"Add",xa.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(25,1,25),0.05,1.5,0.05,keptcolor,keptcolor.Color)
sphere2(2,"Add",xb.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(25,1,25),0.05,1.5,0.05,keptcolor,keptcolor.Color)
sphere2(2,"Add",xc.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(25,1,25),0.05,1.5,0.05,keptcolor,keptcolor.Color)
sphere2(2,"Add",xd.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(25,1,25),0.05,1.5,0.05,keptcolor,keptcolor.Color)
sphere2(4,"Add",xa.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(30,1,30),0.05,1.5,0.05,BrickColor.new("Really black"),Color3.new(0,0,0))
sphere2(4,"Add",xb.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(30,1,30),0.05,1.5,0.05,BrickColor.new("Really black"),Color3.new(0,0,0))
sphere2(4,"Add",xc.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(30,1,30),0.05,1.5,0.05,BrickColor.new("Really black"),Color3.new(0,0,0))
sphere2(4,"Add",xd.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(30,1,30),0.05,1.5,0.05,BrickColor.new("Really black"),Color3.new(0,0,0))
game:GetService("Debris"):AddItem(xa, 5)
game:GetService("Debris"):AddItem(xb, 5)
game:GetService("Debris"):AddItem(xc, 5)
game:GetService("Debris"):AddItem(xd, 5)
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/50,math.random(-10,10)/50,math.random(-10,10)/50)
end
hum.CameraOffset = vt(0,0,0)
end))
task.wait(9)
end
end))
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(10)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.25,-0.05)*angles(math.rad(10),math.rad(0),math.rad(0)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(40),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(-35),math.rad(-10),math.rad(60)),.8)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-35),math.rad(10),math.rad(-50)),.8)
end
attack = false
hum.WalkSpeed = storehumanoidWS
end




function leapbreaker()
attack = true
hum.WalkSpeed = 0
for i = 0, 1, 0.1 do
		task.wait()
	RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(20)),.4)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(40)),.4)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.5,-1)*angles(math.rad(20),math.rad(0),math.rad(0)),.4)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(0)),.4)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(40)),.4)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(-40)),.4)
end
CFuncs["Sound"].Create("rbxassetid://477843807", root, 2.5, 1.05)
CFuncs["Sound"].Create("rbxassetid://1295446488", root, 7.5, 1)
local vel = Instance.new("BodyPosition", root)
vel.P = 7500
vel.D = 1000
vel.maxForce = Vector3.new(50000000000, 10e10, 50000000000)
vel.position = root.CFrame.p + vt(0,150,0)
for i = 0, 24 do
slash(math.random(10,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,250)/250,MAINRUINCOLOR)
end
for i = 0, 5, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(-20),math.rad(0),math.rad(0)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-20),math.rad(0),math.rad(0)),.3)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.3)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.3)
end
local landed = false
vel:Destroy()
hum.WalkSpeed = 170
while true do
CFuncs["Sound"].Create("rbxassetid://200633281", rarmor, 2, 1.05)
CFuncs["Sound"].Create("rbxassetid://161006195", rarmor, 2.5, 1.025)
if landed == false then
for i = 0, 1, 0.6 do
		task.wait()
sphere2(5,"Add",rarmor.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
sphere2(5,"Add",rarmor.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(90),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
sphere2(5,"Add",rarmor.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(180),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.6)
end
for i = 0, 1, 0.6 do
		task.wait()
sphere2(5,"Add",rarmor.CFrame*CFrame.new(math.random(-8,-2),0,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.1,0.1),0,0.1,0,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(-20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1),math.rad(0),math.rad(30)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.2,0)*angles(math.rad(270),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,1.25,0)*angles(math.rad(190),math.rad(0),math.rad(30)),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.6)
end
end
hfr,pfr=rayCast(root.Position,(CFrame.new(root.Position,root.Position - vt(0,1,0))).lookVector,4,char)
if hfr~=nil then
hum.WalkSpeed = 0
landed = true
end
if landed == true then
coroutine.resume(coroutine.create(function()
CFuncs["Sound"].Create("rbxassetid://763717897", root, 7.5, 1)
for i = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://824687369", root, 10, 1)
end
coroutine.resume(coroutine.create(function()
for i = 0, 4, 0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/10,math.random(-10,10)/10,math.random(-10,10)/10)
end
hum.CameraOffset = vt(0,0,0)
end))
MagniDamage(root, 50, 99,534576, 0, "Normal",153092213)
sphere2(3,"Add",root.CFrame,vt(45,1,45),0.3,5,0.3,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(3,"Add",root.CFrame,vt(45,1,45),0.2,4,0.2,MAINRUINCOLOR,MAINRUINCOLOR.Color)
for i = 0, 9 do
waveEff(2,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.25,5),math.random(10,200)/100,math.random(10,20)/100,MAINRUINCOLOR)
end
for i = 0, 24 do
slash(math.random(10,20)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(300,400)/250,MAINRUINCOLOR)
end
for i = 0, 3, 0.1 do
		task.wait()
	RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(40)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.5,-1)*angles(math.rad(20),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(0)),.6)
RW.C0=clerp(RW.C0,cf(1.05,0.5,-0.5)*angles(math.rad(30),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,0.5,-0.5)*angles(math.rad(30),math.rad(0),math.rad(30)),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0)),.6)
end
end))
attack = false
hum.WalkSpeed = 16
break
end
end
end





function annihilation()
	attack = true
	hum.WalkSpeed = 0
	CFuncs["Sound"].Create("rbxassetid://247615928", char, 1.5, 1)
	for i = 0, 9, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(20)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(-20)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.2 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(20),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(35),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.05,0.5 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(140 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(-42 + 3 * math.cos(sine / 15))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.5 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(130 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(42 - 3 * math.cos(sine / 15))),.1)
	end
	for i = 0, 3, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(0)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(0)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.05,0.65 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(180 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(-42 + 3 * math.cos(sine / 15))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.65 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(170 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(42 - 3 * math.cos(sine / 15))),.1)
	end
	shakes(1.5,3)
	--[[local e = script.redness:Clone()
	e.Parent = game:GetService("Lighting")]]--
	CFuncs["Sound"].Create("rbxassetid://763717897", char, 3, 0.5)
	CFuncs["Sound"].Create("rbxassetid://239000203", char, 3, 0.9)
	CFuncs["Sound"].Create("rbxassetid://1413550336", char, 3, 1.1)
	CFuncs["Sound"].Create("rbxassetid://1192402877", char, 2,0.75)
    CFuncs["Sound"].Create("rbxassetid://1664711478", char, 2,1)
    CFuncs["Sound"].Create("rbxassetid://763718160", char, 2, 0.75)
	for i = 0, 21, 0.1 do
		task.wait()
coroutine.resume(coroutine.create(function()
if enableddam == true then
for i, v in pairs(FindNearestHead(root.CFrame.p, 1000000000)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end
end))
		slash(math.random(30,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,2500)/250,BrickColor.new("Really red"))
		slash(math.random(30,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,2500)/250,BrickColor.new("Really black"))
		sphere2(8,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),1,250,1,MRCL)
		sphere2(8,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),1,250,1,MRCL2)
		sphere2(6,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(0,0,0),5,5,5,MRCL)
		sphere2(7,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(0,0,0),5.1,5.1,5.1,MRCL2)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(-30)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(30)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(-30),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-32),math.rad(0),math.rad(0 + 35 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.075 * math.cos(sine / 18),0)*angles(math.rad(-40 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(50 + 3 * math.cos(sine / 15))),.5)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.075 * math.cos(sine / 18),0)*angles(math.rad(-40 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(-50 - 3 * math.cos(sine / 15))),.5)
	end
	--e:Destroy()
	attack = false
	hum.WalkSpeed = storehumanoidWS
end


function annihilation2()
	attack = true
	hum.WalkSpeed = 0
	CFuncs["Sound"].Create("rbxassetid://247615928", char, 1.5, 1.3)
	for i = 0, 9, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(20)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(-20)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.2 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(20),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(35),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.05,0.5 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(140 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(-42 + 3 * math.cos(sine / 15))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.5 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(130 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(42 - 3 * math.cos(sine / 15))),.1)
	end
	for i = 0, 3, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(0)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(0)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.05,0.65 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(180 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(-42 + 3 * math.cos(sine / 15))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.65 + 0.075 * math.cos(sine / 18),-0.5)*angles(math.rad(170 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(42 - 3 * math.cos(sine / 15))),.1)
	end
	shakes(1.5,3)
	--[[local e = script.redness:Clone()
	e.Parent = game:GetService("Lighting")]]--
	CFuncs["Sound"].Create("rbxassetid://763717897", char, 3, 0.5)
	CFuncs["Sound"].Create("rbxassetid://239000203", char, 3, 0.9)
	CFuncs["Sound"].Create("rbxassetid://1413550336", char, 3, 1.1)
	CFuncs["Sound"].Create("rbxassetid://1192402877", char, 2,0.75)
    CFuncs["Sound"].Create("rbxassetid://1664711478", char, 2,1)
    CFuncs["Sound"].Create("rbxassetid://763718160", char, 2, 0.75)
	for i = 0, 21, 0.1 do
		task.wait()
coroutine.resume(coroutine.create(function()
if enableddam == true then
for i, v in pairs(FindNearestHead(root.CFrame.p, 1000000000)) do
if v:FindFirstChild('Head') then
dmg(v)
end
end
end
end))
		slash(math.random(30,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,2500)/250,BrickColor.new("Alder"))
		slash(math.random(30,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(500,2500)/250,BrickColor.new("Dark blue"))
		sphere2(8,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),1,250,1,MRCL)
		sphere2(8,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),1,250,1,MRCL2)
		sphere2(6,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(0,0,0),5,5,5,MRCL)
		sphere2(7,"Add",root.CFrame*CFrame.Angles(0,0,0),vt(0,0,0),5.1,5.1,5.1,MRCL2)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5),math.rad(-30)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 20),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(5.5),math.rad(30)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3 + 0.03 * math.cos(sine / 20),0 + 0.1 * math.cos(sine / 20))*angles(math.rad(-30),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-32),math.rad(0),math.rad(0 + 35 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.075 * math.cos(sine / 18),0)*angles(math.rad(-40 - 3 * math.cos(sine / 32)),math.rad(0 + 8 * math.cos(sine / 23)),math.rad(50 + 3 * math.cos(sine / 15))),.5)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.075 * math.cos(sine / 18),0)*angles(math.rad(-40 - 3 * math.cos(sine / 32)),math.rad(0 - 8 * math.cos(sine / 23)),math.rad(-50 - 3 * math.cos(sine / 15))),.5)
	end
	--e:Destroy()
	attack = false
	hum.WalkSpeed = storehumanoidWS
end


function BeamLol()
attack = true
local keptcolor = MAINRUINCOLOR
local radm = math.random(1,3)
if radm == 1 then
bosschatfunc("Chilling Beam!",MAINRUINCOLOR.Color,1)
elseif radm == 2 then
bosschatfunc("Get this.",MAINRUINCOLOR.Color,1)
elseif radm == 3 then
bosschatfunc("Aren't you familiar?",MAINRUINCOLOR.Color,1)
end
coroutine.resume(coroutine.create(function()
for i = 0, 0 do
task.wait(10)
local orb = Instance.new("Part", char)
CFuncs["Sound"].Create("rbxassetid://663361028", orb, 2, 1)
orb.BrickColor = keptcolor
orb.CanCollide = false
orb.FormFactor = 3
orb.Name = "Ring"
orb.Material = "Neon"
orb.Size = Vector3.new(1, 1, 1)
orb.Transparency = 1
orb.TopSurface = 0
orb.BottomSurface = 0
orb.Anchored = true
local orbm = Instance.new("SpecialMesh", orb)
orbm.MeshType = "Sphere"
orbm.Name = "SizeMesh"
orbm.Scale = vt(1.25,1.25,1.25)
orb.CFrame = root.CFrame*CFrame.new(math.random(-25,25),math.random(75,150),math.random(-25,25))
coroutine.resume(coroutine.create(function()
orb.Transparency = 1
local a = Instance.new("Part",char)
a.Name = "Direction" 
a.Anchored = true
a.BrickColor = keptcolor
a.Material = "Neon"
a.Transparency = 1
a.Shape = "Cylinder"
local x = Instance.new("Part",char)
x.Name = "Direction" 
x.Anchored = true
x.BrickColor = keptcolor
x.Material = "Neon"
x.Transparency = 1
x.Shape = "Cylinder"
local ht = Instance.new("Part",char)
ht.Name = "DirectionHit" 
ht.Anchored = true
ht.BrickColor = keptcolor
ht.CanCollide = false
ht.Transparency = 1
ht.Size = vt(0.1,0.1,0.1)
a.CanCollide = false
local ray = Ray.new(
	orb.CFrame.p, -- origin
	(mouse.Hit.p - orb.CFrame.p).unit * 1000 -- direction
	) 
local ignore = char
local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
a.BottomSurface = 10
a.TopSurface = 10
local distance = (orb.CFrame.p - position).magnitude
a.Size = Vector3.new(distance,1,1)
a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance/2)
ht.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
x.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, 0)
local poste = 0
local rotation = 0
CFuncs["Sound"].Create("rbxassetid://153092315", char, 1.5, 1)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,0),vt(5,5,5),2.5,2.5,0,keptcolor)
CameraEnshaking(2,2)
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",orb)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 15000
eff.Lifetime = NumberRange.new(2.5,5)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,60,0),NumberSequenceKeypoint.new(0.2,3,0),NumberSequenceKeypoint.new(0.8,24,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.2,0,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(100,650)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.35)
eff.Enabled = false
end))
for i = 0, 49 do
task.wait()
rotation = rotation + 5
poste = poste + 1
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(-rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
end
shakes(1,1)
local A1 = Instance.new("Attachment",x)
local A2 = Instance.new("Attachment",ht)
local Beem = Instance.new("Beam",ht)
Beem.Attachment0 = A1
Beem.Attachment1 = A2
Beem.LightEmission = 1
Beem.FaceCamera = true
Beem.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 1),NumberSequenceKeypoint.new(0.025, 0),NumberSequenceKeypoint.new(0.975, 0),NumberSequenceKeypoint.new(1, 1)})
Beem.Width0 = 125
Beem.Width1 = 125
Beem.Texture = "rbxassetid://1134824633"
Beem.TextureMode = "Wrap"
Beem.TextureLength = 200
Beem.TextureSpeed = 1.5
Beem.Color = ColorSequence.new(keptcolor.Color)
CameraEnshaking(3,6)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 1.5, 1)
CFuncs["Sound"].Create("rbxassetid://294188875", char, 2, 1.5)
a.Transparency = 0.25
for i = 0, 49 do
local disr = CreateParta(char,1,1,"Neon",keptcolor)
disr.CFrame = ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",disr)
at1.Position = vt(-5,0,0)
local at2 = Instance.new("Attachment",disr)
at2.Position = vt(5,0,0)
local trl = Instance.new('Trail',disr)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://2325530138"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(keptcolor.Color)
trl.Lifetime = 0.5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = disr.CFrame.lookVector*math.random(50,500)
bv.Parent = disr
local val = 0
coroutine.resume(coroutine.create(function()
task.wait(math.random(30,60))
for i = 0, 19 do
task.wait()
val = val + 0.05
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, val),NumberSequenceKeypoint.new(1, 1)})
end
game:GetService("Debris"):AddItem(disr, 3)
end))
end
sphere2(2,"Add",ht.CFrame,vt(1.25,1.25,1.25),0.5,0.5,0.5,keptcolor)
sphere2(4,"Add",ht.CFrame,vt(1.25,1.25,1.25),0.5,0.5,0.5,keptcolor)
sphere2(2,"Add",ht.CFrame,vt(1.25,1.25,1.25),1,1,1,keptcolor)
sphere2(4,"Add",ht.CFrame,vt(1.25,1.25,1.25),1,1,1,keptcolor)
sphere2(2,"Add",ht.CFrame,vt(1.25,1.25,1.25),1.5,1.5,1.5,keptcolor)
sphere2(4,"Add",ht.CFrame,vt(1.25,1.25,1.25),1.5,1.5,1.5,keptcolor)
MagniDamage(ht, 70, 1000,1500, 0, "Normal")
local eff = Instance.new("ParticleEmitter",ht)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 500
eff.Lifetime = NumberRange.new(1,3)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,5,0),NumberSequenceKeypoint.new(0.2,10,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(0.8,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(80,700)
eff.Drag = 3
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-100,100)
for i = 0, 24 do
sphere2(6,"Add",ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(15,1,15),-0.05,math.random(1,5),-0.05,keptcolor)
local rsiz = math.random(10,50)
sphereMK(math.random(3,6),1.25,"Add",ht.CFrame*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,keptcolor,0)
end
a.CFrame = a.CFrame*CFrame.Angles(0,math.rad(90),0)
local msh = Instance.new("SpecialMesh",a)
msh.MeshType = "Cylinder"
msh.Scale = vt(1,15,15)
for i = 0, 49 do
task.wait()
CameraEnshaking(1,4)
MagniDamage(ht, 70, 1000,1500, 0, "Normal")
rotation = rotation + 5
slash(math.random(30,90)/10,5,true,"Round","Add","Out",ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(200,450)/250,BrickColor.new("White"))
sphere2(4,"Add",ht.CFrame,vt(1.25,1.25,1.25),1,1,1,keptcolor)
sphere2(6,"Add",ht.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(15,1,15),-0.05,math.random(1,5),-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,0),vt(25,25,5),1,1,0,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 + rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(-rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 - rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 + rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 - rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 + rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 - rotation))*CFrame.new(0,50,0),vt(5,25,10),-0.05,1.5,-0.1,keptcolor)
for i = 0, 2 do
local rsiz = math.random(50,250)
sphereMK(math.random(3,6),math.random(2,4),"Add",ht.CFrame*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),rsiz/10,rsiz/10,rsiz/10,0,keptcolor,0)
end
msh.Scale = msh.Scale + vt(0,0.25,0.25)
end
eff.Enabled = false
local visibility = 0
for i = 0, 49 do
task.wait()
visibility = visibility + 0.02
Beem.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 1),NumberSequenceKeypoint.new(0.025, visibility),NumberSequenceKeypoint.new(0.975, visibility),NumberSequenceKeypoint.new(1, 1)})
rotation = rotation + 5
poste = poste - 1
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(-rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(180 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(90 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 + rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
sphere2(8,"Add",x.CFrame*CFrame.Angles(0,0,math.rad(270 - rotation))*CFrame.new(0,poste,0),vt(5,5,5),-0.05,-0.05,-0.05,keptcolor)
msh.Scale = msh.Scale + vt(0,-0.5,-0.5)
a.Transparency = a.Transparency + 0.02
end
wait(1)
orb:Destroy()
a:Destroy()
ht:Destroy()
end))
game:GetService("Debris"):AddItem(orb, 10)
end
end))
hum.WalkSpeed = storehumanoidWS
attack = false
end

	
	
function EndGROUND()
	attack = true
hum.WalkSpeed = 0
bosschatfunc("THIS IS IT!",MAINRUINCOLOR.Color,1)
CFuncs["Sound"].Create("rbxassetid://838392947", root, 10, 1)
CFuncs["Sound"].Create("rbxassetid://1368598393", root, 10, 1)
CFuncs["EchoSound"].Create("rbxassetid://1690475123", char, 1.5, 1,0,10,0.15,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://1690475123", root, 10, 1,0,10,0.15,0.5,1)
local keptcolor = MAINRUINCOLOR
for i = 0,4,0.1 do
task.wait()
block(10,"Add",rarm.CFrame*CFrame.new(0,-6,0),vt(4,4,4),0.05,0.05,0.05,MAINRUINCOLOR,MAINRUINCOLOR.Color)
slash(math.random(25,50)/10,5,true,"Round","Add","Out",rarm.CFrame*CFrame.new(0,-6,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.1,0.01,0.1),-0.1,BrickColor.new("Really black"))
RH.C0=clerp(RH.C0,cf(1,-0.15,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-15),math.rad(-20)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(20)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.25,-0.05)*angles(math.rad(-20),math.rad(0),math.rad(30)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.1)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(170),math.rad(-5),math.rad(10)),.1)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-5),math.rad(10),math.rad(-20)),.1)
end
symbolizeBlink(root,0,2109052855,MAINRUINCOLOR.Color,25,0,0,0,root,false,0,1)
CFuncs["Sound"].Create("rbxassetid://1368637781", root, 3,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 4, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 6, 1)
CFuncs["EchoSound"].Create("rbxassetid://824687369", root, 10, 1,0,10,0.25,0.5,1)
CFuncs["EchoSound"].Create("rbxassetid://824687369", char, 2, 1,0,10,0.25,0.5,1)
coroutine.resume(coroutine.create(function()
CamShakeAll(40,100,Character)
local eff = Instance.new("ParticleEmitter",cen)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,120,0),NumberSequenceKeypoint.new(0.1,40,0),NumberSequenceKeypoint.new(0.8,80,0),NumberSequenceKeypoint.new(1,140,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(500)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
wait(5)
eff:Destroy()
end))
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),1,0.01,1,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(10,1,10),2,0.01,2,MAINRUINCOLOR,MAINRUINCOLOR.Color)
for i = 0, 24 do
slash(math.random(15,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(200,500)/250,BrickColor.new("Really black"))
end
local rrot = 0
local xam = 1
coroutine.resume(coroutine.create(function()
for i = 0, 14 do
task.wait()
rrot = rrot + 40*xam
xam = xam + 0.25
local bonus = xam
local xa = CreateParta(char,0.5,1,"Neon",BrickColor.random())
xa.Anchored = true
xa.Color = Color3.new(0,0,0)
xa.CFrame = root.CFrame*CFrame.new(0,-3,-rrot/1.75)
CreateMesh(xa,"Sphere",30*bonus,1,30*bonus)
local xc = 0
coroutine.resume(coroutine.create(function()
for i = 0, 99 do
	task.wait()
	xc = xc + 0.01
	xa.Color = Color3.new(xc,0,0)
end
xa.Transparency = 1
CFuncs["Sound"].Create("rbxassetid://331666100", xa, 5,0.75)
MagniDamage(xa, 30*bonus, 78*bonus,99*bonus, 0, "Normal")
for i = 0, 9 do
slash(math.random(15,50)/10,5,true,"Round","Add","Out",xa.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(0.01*bonus,0.01,0.01*bonus),math.random(50,125)/250*bonus,BrickColor.new("Really black"))
end
CamShakeAll(20,100,xa)
block(1.5,"Add",xa.CFrame*CFrame.new(0,-10,0),vt(30*bonus,30*bonus,30*bonus),0.3,0.3,0.3,keptcolor,keptcolor.Color)
sphere2(2,"Add",xa.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(25*bonus,1,25*bonus),0.05*bonus,1.5*bonus,0.05*bonus,keptcolor,keptcolor.Color)
sphere2(4,"Add",xa.CFrame*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),vt(30*bonus,1,30*bonus),0.05*bonus,1.5*bonus,0.05*bonus,BrickColor.new("Really black"),Color3.new(0,0,0))
game:GetService("Debris"):AddItem(xa, 5)
end))
end
end))
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-25),math.rad(30)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(20)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.25,-0.5)*angles(math.rad(30),math.rad(0),math.rad(50)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-50)),.8)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(35),math.rad(-10),math.rad(30)),.8)
LW.C0=clerp(LW.C0,cf(-1.4,0.5,0.1)*angles(math.rad(-35),math.rad(10),math.rad(-50)),.8)
end
attack = false
hum.WalkSpeed = storehumanoidWS
end

	

	
	
	function ScatterChaos()
	attack = true
	local rot = 0
	local randomrotations = math.random(1, 2)
	local lookv = 2.5
	local power = 5
	sphere(1, "Add", root.CFrame, vt(1, 100000, 1), 0.5, BrickColor.random())
	sphere(1, "Add", root.CFrame, vt(1, 1, 1), 0.75, BrickColor.random())
	for i = 0, 9 do
		sphereMK(1, 1.5, "Add", root.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 10, 10, 45, -0.1, BrickColor.random(), 0)
	end
	CFuncs.Sound.Create("rbxassetid://180204650", char, 2.5, 0.6)
	CFuncs.Sound.Create("rbxassetid://233856079", char, 1, 0.5)
	CFuncs.Sound.Create("rbxassetid://1208650519", char, 2.5, 1)
	CFuncs.Sound.Create("rbxassetid://239000203", char, 0.5, 0.75)
	CFuncs.Sound.Create("rbxassetid://579687077", char, 0.5, 0.5)
	local hite = Instance.new("Part", char)
	hite.Anchored = true
	hite.CanCollide = false
	hite.FormFactor = 3
	hite.Name = "Ring"
	hite.Material = "Neon"
	hite.Size = Vector3.new(1, 1, 1)
	hite.Transparency = 1
	hite.TopSurface = 0
	hite.BottomSurface = 0
	hite.CFrame = root.CFrame * CFrame.new(0, -2.5, 0)
	local rem = Instance.new("Part", char)
	rem.Anchored = true
	rem.CanCollide = false
	rem.FormFactor = 3
	rem.Name = "Ring"
	rem.Material = "Neon"
	rem.Size = Vector3.new(1, 1, 1)
	rem.Transparency = 1
	rem.TopSurface = 0
	rem.BottomSurface = 0
	rem.CFrame = hite.CFrame
	local rem2 = rem:Clone()
	rem2.Parent = char
	rem2.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(90), 0)
	local rem3 = rem:Clone()
	rem3.Parent = char
	rem3.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(180), 0)
	local rem4 = rem:Clone()
	rem4.Parent = char
	rem4.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(270), 0)
	hite:Destroy()
	coroutine.resume(coroutine.create(function()
		for i = 0, 24 do
			task.wait(1)
			if randomrotations == 1 then
				rot = rot + 1
			elseif randomrotations == 2 then
				rot = rot - 1
			end
			power = power + 0.5
			lookv = lookv + 7.5
			rem.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(rot), 0)
			rem2.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(90), 0)
			rem3.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(180), 0)
			rem4.CFrame = rem.CFrame * CFrame.Angles(0, math.rad(270), 0)
			orb_spawn_norm(rem.CFrame + rem.CFrame.lookVector * lookv, 3, BrickColor.random(), power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem2.CFrame + rem2.CFrame.lookVector * lookv, 3, BrickColor.random(), power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem3.CFrame + rem3.CFrame.lookVector * lookv, 3, BrickColor.random(), power, 25, 75, 10, power / 5, 7.5)
			orb_spawn_norm(rem4.CFrame + rem4.CFrame.lookVector * lookv, 3, BrickColor.random(), power, 25, 75, 10, power / 5, 7.5)
		end
	end))
	attack = false
end
function yinyangi()
	attack = true
	for i = 0, 2, 0.1 do
		task.wait()
		RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-20)), 0.2)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(20)), 0.2)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, -0.5, 0.5 + 0.1 * math.cos(sine / 28)) * angles(math.rad(75), math.rad(0), math.rad(0)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.2)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.2)
	end
	local bv = Instance.new("BodyVelocity")
	bv.maxForce = Vector3.new(1000000000, 1000000000, 1000000000)
	bv.velocity = root.CFrame.lookVector * 175
	bv.Parent = root
	for Rotations = 0, 9 do
		for i = 0, 1, 0.5 do
			task.wait()
			bv.velocity = root.CFrame.lookVector * 175
			RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-20)), 0.5)
			LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(20)), 0.5)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, -0.5, 0.5 + 0.1 * math.cos(sine / 28)) * angles(math.rad(90), math.rad(0), math.rad(90)), 0.5)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.5)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.5)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.5)
		end
		orb_spawn(rarm.CFrame * CFrame.new(0, -1, 0), 2.5)
		for i = 0, 1, 0.5 do
			task.wait()
			bv.velocity = root.CFrame.lookVector * 175
			RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-20)), 0.5)
			LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(20)), 0.5)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, -0.5, 0.5 + 0.1 * math.cos(sine / 28)) * angles(math.rad(90), math.rad(0), math.rad(180)), 0.5)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.5)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.5)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.5)
		end
		orb_spawn(rarm.CFrame * CFrame.new(0, -1, 0), 2.5)
		for i = 0, 1, 0.5 do
			task.wait()
			bv.velocity = root.CFrame.lookVector * 175
			RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-20)), 0.5)
			LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(20)), 0.5)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, -0.5, 0.5 + 0.1 * math.cos(sine / 28)) * angles(math.rad(90), math.rad(0), math.rad(270)), 0.5)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.5)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.5)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.5)
		end
		orb_spawn(rarm.CFrame * CFrame.new(0, -1, 0), 2.5)
		for i = 0, 1, 0.5 do
			task.wait()
			bv.velocity = root.CFrame.lookVector * 175
			RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-20)), 0.5)
			LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(20)), 0.5)
			RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, -0.5, 0.5 + 0.1 * math.cos(sine / 28)) * angles(math.rad(90), math.rad(0), math.rad(360)), 0.5)
			Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.5)
			RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.5)
			LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.5)
		end
		orb_spawn(rarm.CFrame * CFrame.new(0, -1, 0), 2.5)
	end
	bv:Destroy()
	attack = false
end
function Wip()
	attack = true
	local rngb = Instance.new("Part", char)
	rngb.Anchored = true
	rngb.BrickColor = origcolor
	rngb.CanCollide = false
	rngb.FormFactor = 3
	rngb.Name = "Ring"
	rngb.Material = "Neon"
	rngb.Size = Vector3.new(1, 0.05, 1)
	rngb.Transparency = 1
	rngb.TopSurface = 0
	rngb.BottomSurface = 0
	local rngmb = Instance.new("SpecialMesh", rngb)
	rngmb.MeshType = "Brick"
	rngmb.Name = "SizeMesh"
	rngmb.Scale = vt(0, 1, 0)
	local orb = rngb:Clone()
	orb.Parent = char
	orb.Transparency = 0
	orb.BrickColor = BrickColor.new("White")
	orb.Size = vt(1, 1, 1)
	local orbmish = orb.SizeMesh
	orbmish.Scale = vt(0, 0, 0)
	orbmish.MeshType = "Sphere"
	local orbe = rngb:Clone()
	orbe.Parent = char
	orbe.Transparency = 0.5
	orbe.BrickColor = BrickColor.new("New Yeller")
	orbe.Size = vt(1, 1, 1)
	local orbmish2 = orbe.SizeMesh
	orbmish2.Scale = vt(0, 0, 0)
	orbmish2.MeshType = "Sphere"
	orbe.Color = Color3.new(r / 255, g / 255, b / 255)
	rngb:Destroy()
	for i = 0, 5, 0.1 do
		task.wait()
		if rainbowmode == true then
			orbe.Color = Color3.new(r / 255, g / 255, b / 255)
		end
		orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 11.5
		orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 11.5
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.3)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.3)
		RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(90)), 0.3)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-20)), 0.3)
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-0.5), math.rad(0), math.rad(0)), 0.3)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(10), math.rad(0)), 0.3)
		RootPart.CFrame = FaceMouse()[1]
	end
	orbe.Transparency = 1
	orb.Transparency = 1
	orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 5
	CFuncs.Sound.Create("rbxassetid://294188875", char, 1, 1)
	local a = Instance.new("Part", Character)
	a.Name = "Direction"
	a.Anchored = true
	a.BrickColor = bc("White")
	a.Material = "Neon"
	a.Transparency = 0
	a.Shape = "Cylinder"
	a.CanCollide = false
	local a2 = Instance.new("Part", Character)
	a2.Name = "Direction"
	a2.Anchored = true
	a2.BrickColor = bc("New Yeller")
	a2.Color = Color3.new(r / 255, g / 255, b / 255)
	a2.Material = "Neon"
	a2.Transparency = 0.5
	a2.Shape = "Cylinder"
	a2.CanCollide = false
	local ba = Instance.new("Part", Character)
	ba.Name = "HitDirect"
	ba.Anchored = true
	ba.BrickColor = bc("Really black")
	ba.Material = "Neon"
	ba.Transparency = 1
	ba.CanCollide = false
	local ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
	local ignore = Character
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	a2.BottomSurface = 10
	a2.TopSurface = 10
	local distance = (orb.CFrame.p - position).magnitude
	a.Size = Vector3.new(distance, 1, 1)
	a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
	a2.Size = Vector3.new(distance, 1, 1)
	a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
	ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
	a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
	a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
	game:GetService("Debris"):AddItem(a, 20)
	game:GetService("Debris"):AddItem(a2, 20)
	game:GetService("Debris"):AddItem(ba, 20)
	local msh = Instance.new("SpecialMesh", a)
	msh.MeshType = "Cylinder"
	msh.Scale = vt(1, 25, 25)
	local msh2 = Instance.new("SpecialMesh", a2)
	msh2.MeshType = "Cylinder"
	msh2.Scale = vt(1, 30, 30)
	for i = 0, 10, 0.1 do
		task.wait()
		CamShakeAll(42,44,Character)

		a2.Color = Color3.new(r / 255, g / 255, b / 255)
		orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
		hit, position, normal = workspace:FindPartOnRay(ray, ignore)
		distance = (orb.CFrame.p - position).magnitude
		if typrot == 1 then
			rotation = rotation + 2.5
		elseif typrot == 2 then
			rotation = rotation - 2.5
		end
		RootPart.CFrame = FaceMouse()[1]
		a.Size = Vector3.new(distance, 1, 1)
		a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		a2.Size = Vector3.new(distance, 1, 1)
		a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
		a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
		a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
		msh.Scale = msh.Scale - vt(0, 0.25, 0.25)
		msh2.Scale = msh2.Scale - vt(0, 0.3, 0.3)
		sphereMK(5, 1.5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 15, 15, 25, -0.15, MAINRUINCOLOR, 0)
		sphereMK(5, 1.5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 15, 15, 25, -0.15, MAINRUINCOLOR, 0)
		MagniDamage(ba, 30, 500, 60000, 0, "Normal")
	end
	a:Destroy()
	a2:Destroy()
	ba:Destroy()
	orb:Destroy()
	orbe:Destroy()
	attack = false
end
function UniversalSpark()
	attack = true
	local rngb = Instance.new("Part", char)
	rngb.Anchored = true
	rngb.BrickColor = origcolor
	rngb.CanCollide = false
	rngb.FormFactor = 3
	rngb.Name = "Ring"
	rngb.Material = "Neon"
	rngb.Size = Vector3.new(1, 0.05, 1)
	rngb.Transparency = 1
	rngb.TopSurface = 0
	rngb.BottomSurface = 0
	local rngmb = Instance.new("SpecialMesh", rngb)
	rngmb.MeshType = "Brick"
	rngmb.Name = "SizeMesh"
	rngmb.Scale = vt(0, 1, 0)
	local orb = rngb:Clone()
	orb.Parent = char
	orb.Transparency = 0
	orb.BrickColor = BrickColor.new("White")
	orb.Size = vt(1, 1, 1)
	local orbmish = orb.SizeMesh
	orbmish.Scale = vt(0, 0, 0)
	orbmish.MeshType = "Sphere"
	local orbe = rngb:Clone()
	orbe.Parent = char
	orbe.Transparency = 0.5
	orbe.BrickColor = BrickColor.new("New Yeller")
	orbe.Size = vt(1, 1, 1)
	local orbmish2 = orbe.SizeMesh
	orbmish2.Scale = vt(0, 0, 0)
	orbmish2.MeshType = "Sphere"
	orbe.Color = Color3.new(r / 255, g / 255, b / 255)
	rngb:Destroy()
	for i = 0, 5, 0.1 do
		task.wait()
		if rainbowmode == true then
			orbe.Color = Color3.new(r / 255, g / 255, b / 255)
		end
		orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 11.5
		orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 11.5
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.3)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(-90)), 0.3)
		RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(90)), 0.3)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-20)), 0.3)
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-0.5), math.rad(0), math.rad(0)), 0.3)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(10), math.rad(0)), 0.3)
		RootPart.CFrame = FaceMouse()[1]
	end
	orbe.Transparency = 1
	orb.Transparency = 1
	orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 5
	CFuncs.Sound.Create("rbxassetid://294188875", char, 1, 1)
	CFuncs.Sound.Create("rbxassetid://741272936", char, 0.75, 1)
	CFuncs.Sound.Create("rbxassetid://1192402877", char, 1, 1)
	CFuncs.Sound.Create("rbxassetid://1208650519", char, 0.75, 1)
	CFuncs.Sound.Create("rbxassetid://164881112", char, 0.75, 1)
	CFuncs.Sound.Create("rbxassetid://429123896", char, 1, 0.85)
	CFuncs.Sound.Create("rbxassetid://164178927", char, 1, 1)
	local xd = Instance.new("Sound", char)
	xd.SoundId = "rbxassetid://445796828"
	xd.Pitch = 0.75
	xd.Looped = true
	xd.Volume = 1.25
	xd:Play()
	local a = Instance.new("Part", Character)
	a.Name = "Direction"
	a.Anchored = true
	a.BrickColor = bc("Alder")
	a.Color = MAINRUINCOLOR.Color
	a.Material = "Neon"
	a.Transparency = 0.5
	a.Shape = "Cylinder"
	a.CanCollide = false
	local a2 = Instance.new("Part", Character)
	a2.Name = "Direction"
	a2.Anchored = true
	a2.BrickColor = bc("New Yeller")
	a2.Color = MAINRUINCOLOR.Color
	a2.Material = "Neon"
	a2.Transparency = 0.5
	a2.Shape = "Cylinder"
	a2.CanCollide = false
	local ba = Instance.new("Part", Character)
	ba.Name = "HitDirect"
	ba.Anchored = true
	ba.BrickColor = bc("Really black")
	ba.Material = "Neon"
	ba.Transparency = 1
	ba.CanCollide = false
	local ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
	local ignore = Character
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	a2.BottomSurface = 10
	a2.TopSurface = 10
	local distance = (orb.CFrame.p - position).magnitude
	a.Size = Vector3.new(distance, 1, 1)
	a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
	a2.Size = Vector3.new(distance, 1, 1)
	a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
	ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
	a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
	a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
	game:GetService("Debris"):AddItem(a, 60)
	game:GetService("Debris"):AddItem(a2, 60)
	game:GetService("Debris"):AddItem(ba, 60)
	local outerscale = 0
	local msh = Instance.new("SpecialMesh", a)
	msh.MeshType = "Cylinder"
	msh.Scale = vt(1, 0, 0)
	local msh2 = Instance.new("SpecialMesh", a2)
	msh2.MeshType = "Cylinder"
	msh2.Scale = vt(1, 0, 0)
	for i = 0, 2, 0.1 do
		task.wait()
		CamShakeAll(42,44,Character)

		msh2.Scale = msh2.Scale + vt(0, outerscale * 20, outerscale * 20)
		msh.Scale = msh.Scale + vt(0, outerscale * 15, outerscale * 15)
		outerscale = outerscale - 0.015
		orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
		hit, position, normal = workspace:FindPartOnRay(ray, ignore)
		distance = (orb.CFrame.p - position).magnitude
		if typrot == 1 then
			rotation = rotation + 2.5
		elseif typrot == 2 then
			rotation = rotation - 2.5
		end
		RootPart.CFrame = FaceMouse()[1]
		a.Size = Vector3.new(distance, 1, 1)
		a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		a2.Size = Vector3.new(distance, 1, 1)
		a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
		a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
		a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
		sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
		sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
		MagniDamage(ba, 100, 500, 60000, 0, "Normal")
	end
	for z = 0, 2 do
		for i = 0, 4, 0.1 do
			task.wait()
			CamShakeAll(42,44,Character)

			msh2.Scale = msh2.Scale + vt(0, outerscale, outerscale)
			msh.Scale = msh.Scale - vt(0, outerscale, outerscale)
			outerscale = outerscale + 0.015
			orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
			orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
			ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
			hit, position, normal = workspace:FindPartOnRay(ray, ignore)
			distance = (orb.CFrame.p - position).magnitude
			if typrot == 1 then
				rotation = rotation + 2.5
			elseif typrot == 2 then
				rotation = rotation - 2.5
			end
			RootPart.CFrame = FaceMouse()[1]
			a.Size = Vector3.new(distance, 1, 1)
			a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
			a2.Size = Vector3.new(distance, 1, 1)
			a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
			ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
			a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
			a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
			sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
			sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
			MagniDamage(ba, 100, 500, 60000, 0, "Normal")
		end
		for i = 0, 4, 0.1 do
			task.wait()
			CamShakeAll(42,44,Character)

			msh2.Scale = msh2.Scale + vt(0, outerscale, outerscale)
			msh.Scale = msh.Scale - vt(0, outerscale, outerscale)
			outerscale = outerscale - 0.015
			orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
			orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
			ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
			hit, position, normal = workspace:FindPartOnRay(ray, ignore)
			distance = (orb.CFrame.p - position).magnitude
			if typrot == 1 then
				rotation = rotation + 2.5
			elseif typrot == 2 then
				rotation = rotation - 2.5
			end
			RootPart.CFrame = FaceMouse()[1]
			a.Size = Vector3.new(distance, 1, 1)
			a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
			a2.Size = Vector3.new(distance, 1, 1)
			a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
			ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
			a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
			a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
			sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
			sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
			MagniDamage(ba, 100, 500, 60000, 0, "Normal")
		end
	end
	for i = 0, 4, 0.1 do
		task.wait()
		CamShakeAll(42,44,Character)

		msh2.Scale = msh2.Scale + vt(0, outerscale, outerscale)
		msh.Scale = msh.Scale - vt(0, outerscale, outerscale)
		xd.Volume = xd.Volume - 0.025
		a.Transparency = a.Transparency + 0.025
		a2.Transparency = a2.Transparency + 0.025
		outerscale = outerscale - 0.015
		orb.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		orbe.CFrame = root.CFrame * CFrame.new(0, 0.5, 0) + root.CFrame.lookVector * 4
		ray = Ray.new(orb.CFrame.p, (mouse.Hit.p - orb.CFrame.p).unit * 1000)
		hit, position, normal = workspace:FindPartOnRay(ray, ignore)
		distance = (orb.CFrame.p - position).magnitude
		if typrot == 1 then
			rotation = rotation + 2.5
		elseif typrot == 2 then
			rotation = rotation - 2.5
		end
		RootPart.CFrame = FaceMouse()[1]
		a.Size = Vector3.new(distance, 1, 1)
		a.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		a2.Size = Vector3.new(distance, 1, 1)
		a2.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance / 2)
		ba.CFrame = CFrame.new(orb.CFrame.p, position) * CFrame.new(0, 0, -distance)
		a.CFrame = a.CFrame * CFrame.Angles(0, math.rad(90), 0)
		a2.CFrame = a2.CFrame * CFrame.Angles(0, math.rad(90), 0)
		sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
		sphereMK(5, 5, "Add", ba.CFrame * CFrame.Angles(math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360)), math.rad(math.random(-360, 360))), 75, 75, 225, -0.75, MAINRUINCOLOR, 0)
		MagniDamage(ba, 100, 500, 60000, 0, "Normal")
	end
	xd:Destroy()
	a:Destroy()
	a2:Destroy()
	ba:Destroy()
	orb:Destroy()
	orbe:Destroy()
	attack = false
end
function resetmode()
for i, v in pairs(m:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Really red")
		v.Material = "Neon"
	end
end
for i, v in pairs(m2:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Crimson")
		v.Material = "Neon"
	end
end
for i, v in pairs(m3:GetChildren()) do
	if v:IsA("Part") then
		v.BrickColor = BrickColor.new("Really red")
		v.Material = "Neon"
	end
end
attack = true
hum.WalkSpeed = 0
CFuncs["Sound"].Create("rbxassetid://136007472", root, 5, 1.25)
for i = 0,6,0.1 do
task.wait()
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Really red"),Color3.new(1,0,0))
sphereMK(2.5,-1.5,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),3.5,3.5,45,-0.035,MAINRUINCOLOR,100)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.02 + 0.02 * math.cos(sine / 32),1 + 0.05 * math.cos(sine / 32))*angles(math.rad(15 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 44))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30),math.rad(0),math.rad(0 - 5 * math.cos(sine / 0.2))),.2)
RH.C0=clerp(RH.C0,cf(1,-0.4 - 0.05 * math.cos(sine / 32),-0.4)*angles(math.rad(5),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.4 - 0.05 * math.cos(sine / 32),-0.4)*angles(math.rad(5),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RW.C0=clerp(RW.C0,cf(1.05,0.4,-0.5)*angles(math.rad(140),math.rad(0),math.rad(-50)),.2)
LW.C0=clerp(LW.C0,cf(-1.05,0.4,-0.5)*angles(math.rad(140),math.rad(0),math.rad(50)),.2)
end
CFuncs["Sound"].Create("rbxassetid://206082327", root, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://847061203", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://239000203", root, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://579687077", root, 7.5,0.75)
CFuncs["Sound"].Create("rbxassetid://1368637781", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 7.5, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 7.5, 1)
rainbowmode = false
chaosmode = false
glitching = false
insanitymode = false
ModeOfGlitch = 1
storehumanoidWS = 16
newTheme("rbxassetid://12489056016",48.6,1,1.25)
RecolorTextAndRename("MAYHEM",Color3.new(0.25,0,0),Color3.new(1,0,0),"Antique")
CamShakeAll(100,100,Character)
MAINRUINCOLOR = BrickColor.new("Really red")
sphere(2.5,"Add",root.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
for i = 0, 49 do
PixelBlock(1,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
end
for i = 0, 24 do
sphere2(2,"Add",tors.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,7,-0.01,MAINRUINCOLOR)
end
for i = 0,3,0.1 do
sphereMK(2.5,-1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,25,-0.025,MAINRUINCOLOR,0)
end
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3,-0.15)*angles(math.rad(-30),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(0 - 2 * math.cos(sine / 0.2)),math.rad(80 + 2 * math.cos(sine / 0.2))),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(0 + 2 * math.cos(sine / 0.2)),math.rad(-80 - 2 * math.cos(sine / 0.2))),.5)
end
hum.WalkSpeed = storehumanoidWS
attack = false
end
function attackone()
	attack = true
	for i = 0, 1, 0.1 do
		task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(20), math.rad(0), math.rad(-40)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(40)), 0.2)
		RW.C0 = clerp(RW.C0, CFrame.new(1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-40)), 0.2)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-40)), 0.2)
	end
	CFuncs.Sound.Create("rbxassetid://200632136", root, 1, 1.1)
	local hitb = Instance.new("Part", char)
	hitb.Anchored = true
	hitb.CanCollide = false
	hitb.FormFactor = 3
	hitb.Name = "Ring"
	hitb.Material = "Neon"
	hitb.Size = Vector3.new(1, 1, 1)
	hitb.Transparency = 1
	hitb.TopSurface = 0
	hitb.BottomSurface = 0
	hitb.CFrame = root.CFrame + root.CFrame.lookVector * 2
	MagniDamage(hitb, 3, 10, 30, 0, "Normal")
	hitb:Destroy()
	for i = 0, 1, 0.1 do
		task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(-5), math.rad(0), math.rad(70)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(-70)), 0.4)
		RW.C0 = clerp(RW.C0, CFrame.new(1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(70)), 0.4)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(40)), 0.4)
	end
	attack = false
end
function attacktwo()
	attack = true
	for i = 0, 1, 0.1 do
		task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(20), math.rad(0), math.rad(40)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(-40)), 0.2)
		RW.C0 = clerp(RW.C0, CFrame.new(1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(40)), 0.2)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(40)), 0.2)
	end
	CFuncs.Sound.Create("rbxassetid://200632136", root, 1, 1)
	local hitb = Instance.new("Part", char)
	hitb.Anchored = true
	hitb.CanCollide = false
	hitb.FormFactor = 3
	hitb.Name = "Ring"
	hitb.Material = "Neon"
	hitb.Size = Vector3.new(1, 1, 1)
	hitb.Transparency = 1
	hitb.TopSurface = 0
	hitb.BottomSurface = 0
	hitb.CFrame = root.CFrame + root.CFrame.lookVector * 2
	MagniDamage(hitb, 3, 10, 30, 0, "Normal")
	hitb:Destroy()
	for i = 0, 1, 0.1 do
		task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(-5), math.rad(0), math.rad(-70)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(70)), 0.4)
		RW.C0 = clerp(RW.C0, CFrame.new(1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-40)), 0.4)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-70)), 0.4)
		RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(-40)), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(-10)), 0.4)
	end
	attack = false
end
function attackthree()
	attack = true
	for i = 0, 1, 0.1 do
		task.wait()
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(80)), 0.3)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(20), math.rad(0), math.rad(-80)), 0.3)
		RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(80)), 0.3)
		LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-20)), 0.3)
	end
	local distlook = 5
	for i = 0, 4 do
		task.wait()
CamShakeAll(50,50,Character)
		local hite = Instance.new("Part", char)
		hite.Anchored = true
		hite.CanCollide = false
		hite.FormFactor = 3
		hite.Name = "Ring"
		hite.Material = "Neon"
		hite.Size = Vector3.new(1, 1, 1)
		hite.Transparency = 1
		hite.TopSurface = 0
		hite.BottomSurface = 0
		hite.CFrame = root.CFrame + root.CFrame.lookVector * distlook
		sphere(3, "Add", hite.CFrame, vt(0, 0, 0), 0.15, MAINRUINCOLOR)
		sphere(6, "Add", hite.CFrame, vt(0, 0, 0), 0.3, MAINRUINCOLOR)
		MagniDamage(hite, 10, 15, 35, 0, "Normal")
		CFuncs.Sound.Create("rbxassetid://183763506", hite, 2.5, 1)
		CFuncs.Sound.Create("rbxassetid://178452221", hite, 0.25, 0.6)
		game:GetService("Debris"):AddItem(hite, 5)
		distlook = distlook + 10
	end
	attack = false
end
---special attacks---
function attackone1()
attack = true
hum.WalkSpeed = 4
for i = 0, 2, 0.1 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-40),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(1),math.rad(5)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.1,0.1,0)*angles(math.rad(0),math.rad(0),math.rad(40)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(-40)),.3)
RW.C0=clerp(RW.C0,cf(1.25,0.5,-0.65)*angles(math.rad(100),math.rad(0),math.rad(-23)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(110),math.rad(0),math.rad(-85)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
end
local hitb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.Random())
hitb.Anchored = true
hitb.CFrame = root.CFrame + root.CFrame.lookVector*4
MagniDamage(hitb, 4, 24,30, 0, "Normal",153092213)
CFuncs["Sound"].Create("rbxassetid://200633196", rarmor, 1, 1.05)
CFuncs["Sound"].Create("rbxassetid://200633108", rarmor, 1.5, 1.025)
CFuncs["Sound"].Create("rbxassetid://234365549", rarmor, 1, 1)
for i = 0, 1, 0.1 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-20)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(50),math.rad(0)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(-0.1,-0.25,0)*angles(math.rad(10),math.rad(0),math.rad(-50)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(50)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(80),math.rad(0),math.rad(70)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(100),math.rad(0),math.rad(-50)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(0),math.rad(-40)),.3)
end
hitb:Destroy()
attack = false
hum.WalkSpeed = 24
end
function attacktwo1()
attack = true
hum.WalkSpeed = 4
for i = 0, 1, 0.1 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(20),math.rad(5)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(-0.1,0.1,0)*angles(math.rad(0),math.rad(0),math.rad(-40)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(40)),.3)
RW.C0=clerp(RW.C0,cf(1.25,0.5,-0.65)*angles(math.rad(100),math.rad(0),math.rad(-23)),.3)
LW.C0=clerp(LW.C0,cf(-0.5,0.5,-0.25)*angles(math.rad(90),math.rad(0),math.rad(40)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(180),math.rad(0)),.3)
end
local hitb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.Random())
hitb.Anchored = true
hitb.CFrame = root.CFrame + root.CFrame.lookVector*4
MagniDamage(hitb, 4, 24,30, 0, "Normal",153092213)
CFuncs["Sound"].Create("rbxassetid://200633281", rarmor, 1, 1.05)
CFuncs["Sound"].Create("rbxassetid://161006195", rarmor, 1.5, 1.025)
for i = 0, 1, 0.1 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-30),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(20)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.2,-0.25,0)*angles(math.rad(10),math.rad(0),math.rad(90)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(-90)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(80),math.rad(0),math.rad(20)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(100),math.rad(0),math.rad(-50)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(180),math.rad(70)),.3)
end
attack = false
hum.WalkSpeed = 24
end
function attackthree1()
attack = true
hum.WalkSpeed = 4
for i = 0, 1, 0.1 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-30),math.rad(0)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(5)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(-0.1,0.1,0)*angles(math.rad(0),math.rad(0),math.rad(-60)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(2),math.rad(0),math.rad(60)),.3)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-30),math.rad(0),math.rad(53)),.3)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(10),math.rad(0),math.rad(-10)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(90),math.rad(-20)),.3)
end
for x = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://200633108", rarmor, 1, 1.05)
CFuncs["Sound"].Create("rbxassetid://234365573", rarmor, 1.5, 1.025)
local hitb = CreateParta(m,1,1,"SmoothPlastic",BrickColor.Random())
hitb.Anchored = true
hitb.CFrame = root.CFrame + root.CFrame.lookVector*4
MagniDamage(hitb, 4, 12,15, 0, "Normal",153092213)
for i = 0, 1, 0.6 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-10)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(40),math.rad(20)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.2,-0.25,0)*angles(math.rad(-2),math.rad(0),math.rad(80)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(-80)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(90),math.rad(0),math.rad(80)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(-20)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,0,0)*angles(math.rad(0),math.rad(30),math.rad(90)),.3)
end
for i = 0, 1, 0.6 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-10)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(40),math.rad(20)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.2,-0.25,0)*angles(math.rad(-2),math.rad(0),math.rad(80)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(-80)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(90),math.rad(0),math.rad(80)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(-20)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(180)),.3)
end
for i = 0, 1, 0.6 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-10)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(40),math.rad(20)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.2,-0.25,0)*angles(math.rad(-2),math.rad(0),math.rad(80)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(-80)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(90),math.rad(0),math.rad(80)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(-20)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,0,0)*angles(math.rad(0),math.rad(-30),math.rad(270)),.3)
end
for i = 0, 1, 0.6 do
        task.wait()
    RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(-10)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(40),math.rad(20)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0.2,-0.25,0)*angles(math.rad(-2),math.rad(0),math.rad(80)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(4),math.rad(0),math.rad(-80)),.3)
RW.C0=clerp(RW.C0,cf(1.45,0.5,0.1)*angles(math.rad(90),math.rad(0),math.rad(80)),.3)
LW.C0=clerp(LW.C0,cf(-1.45,0.5,0.1)*angles(math.rad(10),math.rad(0),math.rad(-20)),.3)
weaponweld.C1=clerp(weaponweld.C1,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
end
end
attack = false
hum.WalkSpeed = storehumanoidWS
end
--more special attacks lol
function attackone2()
	attack = true
	CFuncs["Sound"].Create("rbxassetid://136007472", root, 5, 1.5)
for i = 0,2,0.1 do
task.wait()
sphereMK(2.5,-1.5,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),3.5,3.5,45,-0.035,MAINRUINCOLOR,100)
slash(math.random(30,60)/10,5,true,"Round","Add","In",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.01,0.5),-0.5,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.3,-0.15)*angles(math.rad(30),math.rad(0),math.rad(0)),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30),math.rad(0),math.rad(0 - 5 * math.cos(sine / 0.2))),.2)
RW.C0=clerp(RW.C0,cf(1.05,0.4,-0.5)*angles(math.rad(140),math.rad(0),math.rad(-50)),.2)
LW.C0=clerp(LW.C0,cf(-1.05,0.4,-0.5)*angles(math.rad(140),math.rad(0),math.rad(50)),.2)
end
for i = 0, 24 do
sphere2(2,"Add",tors.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,7,-0.01,MAINRUINCOLOR)
slash(math.random(10,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(150,350)/250,BrickColor.new("White"))
end
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 52.5)) do
if v:FindFirstChild('Torso') then
dmg(v)
end
end
for i = 0, 24 do
sphere2(2,"Add",tors.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,7,-0.01,MAINRUINCOLOR)
slash(math.random(10,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(150,350)/250,BrickColor.new("White"))
end
CFuncs["Sound"].Create("rbxassetid://206082327", root, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://847061203", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://239000203", root, 7.5,1)
CFuncs["Sound"].Create("rbxassetid://579687077", root, 7.5,0.75)
CFuncs["Sound"].Create("rbxassetid://1368637781", root, 10,1)
CFuncs["Sound"].Create("rbxassetid://763718160", root, 7.5, 1.1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 7.5, 1)
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3,-0.15)*angles(math.rad(-30),math.rad(0),math.rad(0)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(0 - 2 * math.cos(sine / 0.2)),math.rad(80 + 2 * math.cos(sine / 0.2))),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(0 + 2 * math.cos(sine / 0.2)),math.rad(-80 - 2 * math.cos(sine / 0.2))),.5)
end
	attack = false
end

function attacktwo2()
	attack = true
hum.WalkSpeed = 2
local keptcolor = MAINRUINCOLOR
CFuncs["Sound"].Create("rbxassetid://847061203", root, 2, 1)
sphere2(5,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(1,1,1),0.1,0.1,0.1,keptcolor,keptcolor.Color)
sphere2(5,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(1,1,1),0.2,0.2,0.2,keptcolor,keptcolor.Color)
for i = 0, 14 do
PixelBlock(1,math.random(1,3),"Add",rarm.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),1,1,1,0.02,keptcolor,0)
end
for i = 0,1,0.1 do
task.wait()
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(60)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.3)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-60)),.3)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.3)
end
for i = 0, 1 do
CFuncs["Sound"].Create("rbxassetid://763755889", root, 3,1.1)
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.6)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-60)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-90)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.6)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-60)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-180)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.6)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-60)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.6)
end
for i = 0,1,0.6 do
task.wait()
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-2,0)*CFrame.Angles(math.rad(90),0,0),vt(2.25,0.1,2.25),0.01,0.01,0.01,keptcolor,keptcolor.Color)
slash(math.random(15,30)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.05,0.01,0.05),math.random(25,75)/250,BrickColor.new("White"))
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-5)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(30),math.rad(0)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-270)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(20),math.rad(0),math.rad(-30)),.6)
RW.C0=clerp(RW.C0,cf(1.15,0.5,-0.5)*angles(math.rad(90),math.rad(0),math.rad(-60)),.6)
LW.C0=clerp(LW.C0,cf(-1.15,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.6)
end
local rot = 0
local dis = CreateParta(char,0.5,1,"Neon",keptcolor)
CFuncs["EchoSound"].Create("rbxassetid://763718160", dis, 3, 1.1,0,10,0.15,0.5,1)
dis.CFrame = root.CFrame*CFrame.new(0,2,-3)
CreateMesh(dis,"Sphere",10,1,10)
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-5,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(5,0,0)
local trl = Instance.new('Trail',wed)
trl.Attachment0 = at1
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(dis.Color)
trl.Lifetime = 0.6
local a = Instance.new("Part",workspace)
	a.Name = "Direction"	
	a.Anchored = true
	a.BrickColor = bc("Bright red")
a.Material = "Neon"
a.Transparency = 1
	a.CanCollide = false
	local ray = Ray.new(
	    dis.CFrame.p,                           -- origin
	    (mouse.Hit.p - dis.CFrame.p).unit * 500 -- direction
	) 
	local ignore = dis
	local hit, position, normal = workspace:FindPartOnRay(ray, ignore)
	a.BottomSurface = 10
	a.TopSurface = 10
	local distance = (dis.CFrame.p - position).magnitude
	a.Size = Vector3.new(0.1, 0.1, 0.1)
	a.CFrame = CFrame.new(dis.CFrame.p, position) * CFrame.new(0, 0, 0)
dis.CFrame = a.CFrame
dis.CFrame = dis.CFrame*CFrame.Angles(0,math.rad(rot),0)
a:Destroy()
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*250
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 5)
local hitted = false
coroutine.resume(coroutine.create(function()
dis.Touched:connect(function(hit) 
	if hitted == false and hit.Parent ~= char then
	hitted = true
	CFuncs["EchoSound"].Create("rbxassetid://782200047", dis, 7, 1.1,0,10,0.15,0.5,1)
	MagniDamage(dis, 30, 33,56, 0, "Normal")
	sphere2(8,"Add",dis.CFrame,vt(10,1,10),1,0.1,1,keptcolor,keptcolor.Color)
	sphere2(4,"Add",dis.CFrame,vt(1,1,1),0.5,0.5,0.5,keptcolor,keptcolor.Color)
	sphere2(3,"Add",dis.CFrame,vt(1,1,1),0.5,0.5,0.5,keptcolor,keptcolor.Color)
	coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2344870656"
eff.LightEmission = 1
eff.Color = ColorSequence.new(dis.Color)
eff.Rate = 10000000
eff.Enabled = true
eff.EmissionDirection = "Front"
eff.Lifetime = NumberRange.new(1)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.1,20,0),NumberSequenceKeypoint.new(0.8,40,0),NumberSequenceKeypoint.new(1,60,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0.8,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(150)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.SpreadAngle = Vector2.new(0,900)
eff.RotSpeed = NumberRange.new(-500,500)
wait(0.2)
eff.Enabled = false
	end))
	coroutine.resume(coroutine.create(function()
		for i = 0, 9 do
local disr = CreateParta(char,1,1,"Neon",keptcolor)
disr.CFrame = dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",disr)
at1.Position = vt(-5,0,0)
local at2 = Instance.new("Attachment",disr)
at2.Position = vt(5,0,0)
local trl = Instance.new('Trail',disr)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://2342682798"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(keptcolor.Color)
trl.Lifetime = 0.5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = disr.CFrame.lookVector*math.random(50,200)
bv.Parent = disr
local val = 0
coroutine.resume(coroutine.create(function()
	task.wait(30)
	for i = 0, 9 do
		task.wait()
		val = val + 0.1
		trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, val),NumberSequenceKeypoint.new(1, 1)})
	end
game:GetService("Debris"):AddItem(disr, 3)
end))
end
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(keptcolor.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(20,250)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.25)
eff.Enabled = false
end))
	for i = 0, 9 do
		slash(math.random(10,20)/10,5,true,"Round","Add","Out",dis.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(100,200)/250,BrickColor.new("White"))
	end
for i = 0, 19 do
PixelBlock(1,math.random(5,20),"Add",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),4,4,4,0.08,keptcolor,0)
end
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/70,math.random(-10,10)/70,math.random(-10,10)/70)
end
hum.CameraOffset = vt(0,0,0)
end))
dis.Anchored = true
dis.Transparency = 1
wait(8)
dis:Destroy()
end
end)
end))
rot = rot - 15
end
for i = 0,2,0.1 do
task.wait()
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(-30),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(5)),.3)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-60)),.3)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10),math.rad(0),math.rad(50)),.3)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(90),math.rad(0),math.rad(60)),.3)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(-20),math.rad(0),math.rad(-10)),.3)
end
attack = false
hum.WalkSpeed = storehumanoidWS
end

function attackthree2()
attack = true
local keptcolor = MAINRUINCOLOR
CFuncs["Sound"].Create("rbxassetid://136007472", root, 2, 1.5)
	for i = 0,2,0.1 do
		task.wait()
		sphere2(5,"Add",larm.CFrame*CFrame.new(0,-1.5,0),vt(1,1,1),0.025,0.025,0.025,MAINRUINCOLOR,MAINRUINCOLOR.Color)
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(10),math.rad(0),math.rad(50)),0.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(5),math.rad(0),math.rad(-50)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(80), math.rad(10), math.rad(60)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(-70)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(-50),math.rad(-10)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(40)),.3)
	end
CFuncs["Sound"].Create("rbxassetid://763716870", root, 3,1)
CFuncs["Sound"].Create("rbxassetid://782353443", root, 5,0.9)
CFuncs["Sound"].Create("rbxassetid://782225570", root, 4,0.5)
CFuncs["Sound"].Create("rbxassetid://763717569", root, 3,1)
sphere2(5,"Add",root.CFrame,vt(1,1,1),1,1,1,MAINRUINCOLOR)
sphere2(5,"Add",root.CFrame,vt(1,1,1),0.5,0.5,0.5,MAINRUINCOLOR)
for i = 0, 24 do
		slash(math.random(10,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(90),math.rad(math.random(-360,360)),math.rad(0)),vt(0.01,0.01,0.01),math.random(50,200)/250,BrickColor.new("White"))
end
for i = 0,4,0.1 do
		task.wait()
		root.CFrame = root.CFrame + root.CFrame.lookVector*5
		local dis = CreateParta(char,0.25,1,"Neon",MAINRUINCOLOR)
CreateMesh(dis,"Sphere",1,1,1)
dis.Anchored = true
dis.CFrame = larm.CFrame*CFrame.new(0,-3,0)
sphere2(5,"Add",dis.CFrame,vt(1,1,1),0.1,0.1,0.1,dis.BrickColor,dis.Color)
coroutine.resume(coroutine.create(function()
	task.wait(30)
	dis.Transparency = 1
coroutine.resume(coroutine.create(function()
for i = 0, 19 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/40,math.random(-10,10)/40,math.random(-10,10)/40)
end
hum.CameraOffset = vt(0,0,0)
end))
coroutine.resume(coroutine.create(function()
local eff = Instance.new("ParticleEmitter",dis)
eff.Texture = "rbxassetid://2273224484"
eff.LightEmission = 1
eff.Color = ColorSequence.new(dis.Color)
eff.Rate = 500000
eff.Lifetime = NumberRange.new(0.5,2)
eff.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,20,0),NumberSequenceKeypoint.new(0.2,2,0),NumberSequenceKeypoint.new(0.8,2,0),NumberSequenceKeypoint.new(1,0,0)})
eff.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0,0),NumberSequenceKeypoint.new(0.8,0,0),NumberSequenceKeypoint.new(1,1,0)})
eff.Speed = NumberRange.new(50,450)
eff.Drag = 5
eff.Rotation = NumberRange.new(-500,500)
eff.VelocitySpread = 9000
eff.RotSpeed = NumberRange.new(-50,50)
wait(0.125)
eff.Enabled = false
end))
MagniDamage(dis, 30, 45,50, 0, "Normal")
    for i = 0, 2 do
		slash(math.random(10,80)/10,5,true,"Round","Add","Out",dis.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.01,0.01,0.01),math.random(50,150)/250,dis.BrickColor)
	end
	CFuncs["Sound"].Create("rbxassetid://782353117", dis, 1,1)
	CFuncs["Sound"].Create("rbxassetid://1666361078", dis, 1,1.5)
	CFuncs["Sound"].Create("rbxassetid://782353443", dis, 2,1.65)
	sphere2(3,"Add",dis.CFrame,vt(1,1,1),0.4,0.4,0.4,dis.BrickColor,dis.Color)
end))
game:GetService("Debris"):AddItem(dis, 5)
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(89),math.rad(-8),math.rad(-5)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-30),math.rad(0),math.rad(8)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-14), math.rad(1), math.rad(17)), 0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.85, 0) * angles(math.rad(180), math.rad(0), math.rad(-8)), 0.5)
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-8),math.rad(0),math.rad(-20)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(9),math.rad(0),math.rad(20)),.5)
	end
attack = false
end
--EVEN MORE ATTACKS LOL--
function attackone3()
        attack=true
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 7.5)) do
if v:FindFirstChild('Torso') then
dmg(v)
end
end        for i=0,1,0.1 do
                task.wait()
                RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(0),math.rad(-90),math.rad(-90))*angles(math.rad(90),0,math.rad(0)),.4)
                LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-25)), 0.3)
        end
	CFuncs.Sound.Create("rbxassetid://199150686", char, 1, 1)
        for i=0,1,0.1 do
                task.wait()
                Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(0),math.rad(0),math.rad(-20)),.4)
                RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-.5)*angles(math.rad(0),math.rad(0),math.rad(25)),.4)
                RW.C0=clerp(RW.C0,cf(1,0.5,-.5)*angles(math.rad(0),math.rad(-90),math.rad(-100))*angles(math.rad(-75),0,math.rad(0)),.4)
                LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-25)), 0.3)
        end
        attack=false
end	

function attacktwo3()
        attack=true
for i, v in pairs(FindNearestHead(Torso.CFrame.p, 7.5)) do
if v:FindFirstChild('Torso') then
dmg(v)
end
end        for i=0,1,0.1 do
                task.wait()
                RW.C0=clerp(RW.C0,cf(1,0.5,-.5)*angles(math.rad(0),math.rad(-90),math.rad(-90))*angles(math.rad(-75),0,math.rad(0)),.4)
                LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-25)), 0.3)
        end
	CFuncs.Sound.Create("rbxassetid://199146359", char, 1, 1)
        for i=0,1,0.1 do
                task.wait()
                Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(0),math.rad(0),math.rad(40)),.4)
                RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-.5)*angles(math.rad(0),math.rad(0),math.rad(-45)),.4)
                RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(0),math.rad(-90),math.rad(-90))*angles(math.rad(90),0,math.rad(0)),.4)
                LW.C0 = clerp(LW.C0, CFrame.new(-1.45, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-25)), 0.3)
        end
        attack=false
end     

function attackthree3()
	attack = true
	for i = 0, 2, 0.1 do
		task.wait()
		RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(20)), 0.2)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20), math.rad(0), math.rad(0)), 0.2)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(-20)), 0.2)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(140), math.rad(0), math.rad(20)), 0.2)
	end
	CFuncs.Sound.Create("rbxassetid://438666141", root, 7.5, 1)
	CFuncs.Sound.Create("rbxassetid://1208650519", root, 7.5, 1)
CamShakeAll(31,32,Character)
	for i, v in pairs(FindNearestHead(Torso.CFrame.p, 25)) do
		if v:FindFirstChild("Head") then
			dmg(v)
		end
	end
	sphere(5, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 1, BrickColor.random())
	sphere(10, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(0, 0, 0), 2, BrickColor.random())
	sphere(1, "Add", root.CFrame * CFrame.new(0, -2.9, 0), vt(25, 0.01, 25), 0.01, BrickColor.random())
	for i = 0, 2, 0.1 do
		task.wait()
		sphereMK(10, 0.75, "Add", root.CFrame * CFrame.new(math.random(-52.5, 52.5), -5, math.random(-52.5, 52.5)) * CFrame.Angles(math.rad(90 + math.rad(math.random(-45, 45))), math.rad(math.random(-45, 45)), math.rad(math.random(-45, 45))), 2.5, 2.5, 25, -0.025, BrickColor.random(), 0)
		RH.C0 = clerp(RH.C0, cf(1, -1, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0), math.rad(10)), 0.4)
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0) * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(10), math.rad(0), math.rad(0)), 0.4)
		RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(30)), 0.4)
		LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(-50), math.rad(0), math.rad(-30)), 0.4)
	end
	attack = false
end


--GIANT PERSON--
local ActiveGia = false
function THEHELLITSTHATBIG()
ActiveGia = true
attack = true
hum.WalkSpeed = 0
	for i = 0,2,0.1 do
		task.wait()
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(-20),math.rad(0),math.rad(0)),0.2)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-15),math.rad(0),math.rad(0)),.2)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(100)), 0.2)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-100)), 0.2)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-0.5),math.rad(0),math.rad(-20)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(10),math.rad(20)),.2)
	end
for i = 0,1,0.1 do
torsweld.C1=clerp(torsweld.C1,cf(0,5*4,-8)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(0),math.rad(0),math.rad(20)),1)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(0),math.rad(0),math.rad(-20)),1)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,0)*angles(math.rad(-10),math.rad(0),math.rad(0)),1)
end
CFuncs["Sound"].Create("rbxassetid://528589382", sectors, 5, 1)
secrleg.Transparency = 0.5
seclleg.Transparency = 0.5
secrarm.Transparency = 0.5
seclarm.Transparency = 0.5
seched.Transparency = 0.5
sectors.Transparency = 0.5
for i = 0,25,0.1 do
task.wait()
PixelBlockNeg(1,math.random(1,5),"Add",sectors.CFrame*CFrame.new(math.random(-25,25),0,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),5,5,5,0.1,MAINRUINCOLOR,-10)
torsweld.C1=clerp(torsweld.C1,cf(0,-2 + 0.25 * math.cos(sine / 32) ,-8)*angles(math.rad(0),math.rad(0),math.rad(0)),.025)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(0),math.rad(0),math.rad(20)),0.025)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(0),math.rad(0),math.rad(-20)),0.025)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,0.2)*angles(math.rad(-10),math.rad(0),math.rad(0)),0.025)
end
--[[secrleg.Transparency = 1
seclleg.Transparency = 1
secrarm.Transparency = 1
seclarm.Transparency = 1
seched.Transparency = 1
sectors.Transparency = 1]]--
torsweld.Part0 = root
hum.WalkSpeed = storehumanoidWS
attack = false
end

function removelol()
ActiveGia = false
attack = true
hum.WalkSpeed = 0
	for i = 0,2,0.1 do
		task.wait()
            RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(-20),math.rad(0),math.rad(0)),0.2)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-15),math.rad(0),math.rad(0)),.2)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(100)), 0.2)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(90), math.rad(0), math.rad(-100)), 0.2)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-0.5),math.rad(0),math.rad(-20)),.2)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 25),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(10),math.rad(20)),.2)
	end
CFuncs["Sound"].Create("rbxassetid://528589274", sectors, 5, 1)
for i = 0,25,0.1 do
task.wait()
secrleg.Transparency = secrleg.Transparency + 0.00225
seclleg.Transparency = secrleg.Transparency
secrarm.Transparency = secrleg.Transparency
seclarm.Transparency = secrleg.Transparency
seched.Transparency = secrleg.Transparency
sectors.Transparency = secrleg.Transparency
PixelBlockNeg(1,math.random(1,5),"Add",sectors.CFrame*CFrame.new(math.random(-25,25),0,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),5,5,5,0.1,MAINRUINCOLOR,-10)
torsweld.C1=clerp(torsweld.C1,cf(0,-2 + 0.25 * math.cos(sine / 32) ,-8)*angles(math.rad(0),math.rad(0),math.rad(0)),.025)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(20),math.rad(0),math.rad(20)),0.025)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(20),math.rad(0),math.rad(-20)),0.025)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,0.2)*angles(math.rad(-10),math.rad(0),math.rad(0)),0.025)
end
CFuncs["Sound"].Create("rbxassetid://468991944", sectors, 10, 1)
sphere(1,"Add",sectors.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
sphere(2,"Add",sectors.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
sphere(3,"Add",sectors.CFrame,vt(0,0,0),1,MAINRUINCOLOR)
secrleg.Transparency = 1
seclleg.Transparency = 1
secrarm.Transparency = 1
seclarm.Transparency = 1
seched.Transparency = 1
sectors.Transparency = 1
torsweld.Part0 = root
hum.WalkSpeed = storehumanoidWS
attack = false
end


local attacktype = 1
mouse.Button1Down:connect(function()
  if attack == false and attacktype == 1 and equipped == false and advanced == false then
    attacktype = 2
    attackone()
  elseif attack == false and attacktype == 2 and equipped == false and advanced == false then
    attacktype = 3
    attacktwo()
  elseif attack == false and attacktype == 3 and equipped == false and advanced == false then
    attacktype = 1
    attackthree()

  elseif attack == false and attacktype == 1 and equipped == true and advanced == false then
    attacktype = 2
    attackone1()
  elseif attack == false and attacktype == 2 and equipped == true and advanced == false then
    attacktype = 3
    attacktwo1()
  elseif attack == false and attacktype == 3 and equipped == true and advanced == false then
    attacktype = 1
    attackthree1()

  elseif attack == false and attacktype == 1 and advanced == true and equipped == false then
    attacktype = 2
    attackone2()
  elseif attack == false and attacktype == 2 and advanced == true and equipped == false then
    attacktype = 3
    attacktwo2()
  elseif attack == false and attacktype == 3 and advanced == true and equipped == false then
    attacktype = 1
    attackthree2()

  elseif attack == false and attacktype == 1 and advanced == true and equipped == true then
    attacktype = 2
    attackone3()
  elseif attack == false and attacktype == 2 and advanced == true and equipped == true then
    attacktype = 3
    attacktwo3()
  elseif attack == false and attacktype == 3 and advanced == true and equipped == true then
    attacktype = 1
    attackthree3()
  end
end)
mouse.KeyDown:connect(function(k)
	if Diversial == false then
	if k == "q" and attack == false and ModeOfGlitch ~= 2 then
		ModeOfGlitch = 2
		storehumanoidWS = 16
		hum.WalkSpeed = 16
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Purity", Color3.new(0,1,1),Color3.new(1,1,1),"Code")
		newTheme("rbxassetid://12578898194", 20.25, 1, 1)
		MAINRUINCOLOR = BrickColor.new("Toothpaste")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("White")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Pastel light blue")
				v.Material = "Glass"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Toothpaste")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "q" and attack == false and ModeOfGlitch == 2 then
		resetmode()
	end
	if k == "one" and attack == false and ModeOfGlitch ~= 70077 then
		ModeOfGlitch = 70077
		storehumanoidWS = 50
		hum.WalkSpeed = 50
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		ModeFrame.Text = RandomCaps"guESt GLiTcHEr v999"
		RecolorTextAndRename("guESt GLiTcHEr v999", Color3.new(0,1,1),Color3.new(1,1,1),"Code")
		newTheme("rbxassetid://1010460329", 20.25, 1, 1)
		kan.TimePosition = 0
		MAINRUINCOLOR = BrickColor.new("Toothpaste")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 01
				v.BrickColor = BrickColor.new("White")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Pastel light blue")
				v.Material = "Glass"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Toothpaste")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "one" and attack == false and ModeOfGlitch == 70077 then
		resetmode()
	end
	if k == "e" and attack == false and ModeOfGlitch ~= 3 then
		ModeOfGlitch = 3
		storehumanoidWS = 16
		hum.WalkSpeed = 16
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Corruption", Color3.new(0,0,0),Color3.new(0.35,0,1),"Antique")
		newTheme("rbxassetid://1837008684", 58.15, 1,2)
		MAINRUINCOLOR = BrickColor.new("Royal purple")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Dark indigo")
				v.Material = "Glass"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Royal purple")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "e" and attack == false and ModeOfGlitch == 3 then
		resetmode()
	end
	if k == "m" and attack == false and ModeOfGlitch == 3 then
attack = true
ModeOfGlitch = 3
hum.WalkSpeed = 0
newThemeCust("rbxassetid://2368327428",9,1,2)
wait(2)
for i = 0, 15, 0.1 do
		task.wait()
RH.C0=clerp(RH.C0,cf(1, -1 - 0.025 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
LH.C0=clerp(LH.C0,cf(-1, -1 - 0.05 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(-83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0, 0, 0 + 0.05 * math.cos(sine / 12))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*cf(0, 0, 0 + ((1) - 1))*angles(math.rad(15 - 2.5 * math.sin(sine / 12)),math.rad(0),math.rad(0)),0.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.125 * math.cos(sine / 12),-0.45)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.125 * math.cos(sine / 12),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(67 - 4 * math.cos(sine / 45))),.1)
end
sphere(2,"Add",root.CFrame,vt(0,0,0),12.5,MAINRUINCOLOR)
sphere(3,"Add",root.CFrame,vt(0,0,0),10,MAINRUINCOLOR)
sphere(1,"Add",root.CFrame,vt(0,0,0),7.5,MAINRUINCOLOR)
sphere(2,"Add",root.CFrame,vt(0,0,0),5,MAINRUINCOLOR)
sphere(3,"Add",root.CFrame,vt(0,0,0),2.5,MAINRUINCOLOR)
CFuncs["Sound"].Create("rbxassetid://847061203", char, 2,1)
               ModeOfGlitch = 146536
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("MATTER-V",Color3.new(255, 176, 0),Color3.new(213, 115, 61),"Antique")
MAINRUINCOLOR = BrickColor.new("Deep orange")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Neon orange"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
attack = false
	elseif k == "m" and attack == false and ModeOfGlitch == 146536 then
		resetmode()
	end
	if k == "n" and attack == false and ModeOfGlitch == 146536 then
		Krabbo()
	end
if k == "m" and attack == false and ModeOfGlitch == 6127843 and ModeOfGlitch ~= 778899 then
               ModeOfGlitch = 778899
storehumanoidWS = 50
hum.WalkSpeed = 50
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("Relaxation",Color3.new(34,34,34),BrickColor.new("Ghost grey").Color,"Fantasy")
newTheme("rbxassetid://860594509",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Dark stone grey")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Cloudy grey"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
elseif k == "m" and attack == false and ModeOfGlitch == 778899 then
		resetmode()
end
if k == "n" and attack == false and ModeOfGlitch == 778899 and ModeOfGlitch ~= 353567 then
               ModeOfGlitch = 353567
storehumanoidWS = 12
hum.WalkSpeed = 12
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("Silence..",Color3.new(0,0,0),BrickColor.new("Really black").Color,"Antique")
newTheme("rbxassetid://187918023",0,0.5,0.5)
MAINRUINCOLOR = BrickColor.new("Really black")
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Really black"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
elseif k == "m" and attack == false and ModeOfGlitch == 353567 then
		resetmode()
end
if k == "j" and attack == false and ModeOfGlitch ~= 67966 then
               ModeOfGlitch = 67966
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("LOVE",Color3.new(1,0,1),Color3.new(1,0.5,1),"Highway")
newTheme("rbxassetid://13506226037",0,1,1.75)
MAINRUINCOLOR = BrickColor.new("Hot pink")
		disably = false
		warnedpeople("Love <3","Antique",BrickColor.new("White").Color,BrickColor.new("Pink").Color)
		disably = true
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Pink"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "m" and attack == false and ModeOfGlitch == 2 and ModeOfGlitch ~= 2332 then
               ModeOfGlitch = 2332
storehumanoidWS = 12
hum.WalkSpeed = 12
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("CLARITY",Color3.new(1,1,1),BrickColor.new("Pastel Blue").Color,"Fantasy")
newTheme("rbxassetid://2482117221",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Pastel Blue")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Pastel Blue"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
	elseif k == "m" and attack == false and ModeOfGlitch == 2332 then
		resetmode()
	end
if k == "three" and attack == false and ModeOfGlitch ~= 9123851 then
                 ModeOfGlitch = 9123851
storehumanoidWS = 135
hum.WalkSpeed = 135
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Visualiser",BrickColor.new("Medium stone grey").Color,BrickColor.new("Black").Color,"Arcade")
print("Default: 147372923")
newTheme("rbxassetid://"..OVMID,0,OVMPIT,OVMVOL)
MAINRUINCOLOR = BrickColor.new("Medium stone grey")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "four" and attack == false and ModeOfGlitch ~= 912 then
                 ModeOfGlitch = 912
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Cored",BrickColor.new("Really red").Color,BrickColor.new("Crimson").Color,"Arcade")
newTheme("rbxassetid://153166656",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Really red")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "five" and attack == false and ModeOfGlitch ~= 9123 then
                 ModeOfGlitch = 9123
storehumanoidWS = 135
hum.WalkSpeed = 135
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Greed",BrickColor.new("New Yeller").Color,BrickColor.new("Brick yellow").Color,"Antique")
newTheme("rbxassetid://341281110",0,0.7,1.5)
MAINRUINCOLOR = BrickColor.new("New Yeller")
		disably = false
		warnedpeople("Greedy","Antique",BrickColor.new("New Yeller").Color,BrickColor.new("Bright yellow").Color)
		disably = true
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "six" and attack == false and ModeOfGlitch ~= 91234 then
                 ModeOfGlitch = 91234
storehumanoidWS = 19
hum.WalkSpeed = 19
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Cyber",BrickColor.new("Light blue").Color,BrickColor.new("Cyan").Color,"Arcade")
newTheme("rbxassetid://170282324",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Deep blue")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "seven" and attack == false and ModeOfGlitch ~= 912345 then
                 ModeOfGlitch = 912345
storehumanoidWS = 19
hum.WalkSpeed = 19
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Synthezizer",BrickColor.new("Alder").Color,BrickColor.new("Pastel light blue").Color,"SciFi")
newTheme("rbxassetid://923445685",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Alder")
RecolorThing(MAINRUINCOLOR,1,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
end
if k == "eight" and attack == false and ModeOfGlitch ~= 9123456 then
                 ModeOfGlitch = 9123456
storehumanoidWS = 19
hum.WalkSpeed = 19
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Warrior",BrickColor.new("Ghost grey").Color,BrickColor.new("Medium stone grey").Color,"Bodoni")
newTheme("rbxassetid://164084138",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Fossil")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
end
if k == "nine" and attack == false and ModeOfGlitch ~= 91234567 then
                 ModeOfGlitch = 91234567
storehumanoidWS = 50
hum.WalkSpeed = 50
rainbowmode = false
chaosmode = false
RecolorTextAndRename("The Monarch",Color3.new(0,0,0),Color3.new(255,0,0),"Antique")
newTheme("rbxassetid://1255569288",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Really red")
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new("Medium stone grey")
v.Material = "Granite"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new("Medium stone grey")
v.Material = "Granite"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = BrickColor.new("Really red")
v.Material = "Granite"
end
end
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Dark stone grey")
v.Material = "Granite"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Really red")
v.Material = "Granite"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Dark stone grey")
v.Material = "Granite"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Really red")
v.Material = "Granite"
end
end
end
if k == "zero" and attack == false and ModeOfGlitch ~= 912345678 then
                 ModeOfGlitch = 912345678
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Retribution",BrickColor.new("Crimson").Color,BrickColor.new("Lime green").Color,"Legacy")
newTheme("rbxassetid://164084138",0,1,1.5)
MAINRUINCOLOR = BrickColor.new("Forest green")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
end
if k == "k" and attack == false and ModeOfGlitch ~= 2334 then
               ModeOfGlitch = 2334
storehumanoidWS = 12
hum.WalkSpeed = 12
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("super thinking :thinking:...",BrickColor.new'Toothpaste'.Color,BrickColor.new'Dark blue'.Color,"Fantasy")
newTheme("rbxassetid://346324685",0,1,0.3)
MAINRUINCOLOR = BrickColor.new("Dark blue")
RecolorThing2(MAINRUINCOLOR,1,BrickColor.new("Pastel Blue"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
	elseif k == "k" and attack == false and ModeOfGlitch == 2334 then
		resetmode()
	end
if k == "x" and attack == false and ModeOfGlitch == 2334 then
               ModeOfGlitch = 2339
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("T-POSE",BrickColor.new'Crimson'.Color,BrickColor.new'Bright red'.Color,"Fantasy")
newTheme("rbxassetid://2410799757",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Bright red")
RecolorThing2(MAINRUINCOLOR,1,BrickColor.new("Crimson"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
	elseif k == "x" and attack == false and ModeOfGlitch == 2339 then
		resetmode()
	end
	if k == "r" and attack == false and ModeOfGlitch ~= 4 then
		ModeOfGlitch = 4
		storehumanoidWS = 16
		hum.WalkSpeed = 16
		rainbowmode = false
		chaosmode = true
        insanitymode = false
		glitching = false
		RecolorTextAndRename("CHAOS", Color3.new(0, 0, 0), BrickColor.random().Color,"Fantasy")
		newTheme("rbxassetid://12578906659", 0, 1, 3)
		MAINRUINCOLOR = BrickColor.new("Black")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Black")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Black")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "r" and attack == false and ModeOfGlitch == 4 then
		resetmode()
	end
	if k == "n" and attack == false and ModeOfGlitch == 4 and ModeOfGlitch ~= 8787 then
		ModeOfGlitch = 8787
		storehumanoidWS = 100
		hum.WalkSpeed = 100
		rainbowmode = false
		chaosmode = false
        insanitymode = true
		glitching = false
		
		RecolorTextAndRename("INSANITY", Color3.new(0, 0, 0), BrickColor.random().Color,"Antique")
			newTheme("rbxassetid://122590523821798", 2, 1, 10)
		MAINRUINCOLOR = BrickColor.new("Lime green")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
	elseif k == "n" and attack == false and ModeOfGlitch == 8787 then
		resetmode()
	end
if k == "m" and attack == false and ModeOfGlitch == 4 then
               ModeOfGlitch = 151353
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("Fighter",Color3.new(255,255,255),BrickColor.new("Crimson").Color,"Fantasy")
newTheme("rbxassetid://900817147",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Really red")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Really black"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
end
	if k == "t" and attack == false and ModeOfGlitch ~= 5 then
		ModeOfGlitch = 5
		storehumanoidWS = 16
		hum.WalkSpeed = 16
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Solitude", Color3.new(0, 0, 0), Color3.new(255, 255, 255),"Bodoni")
		newTheme("rbxassetid://12578927972", 10, 1, 3)		
		MAINRUINCOLOR = BrickColor.new("Really black")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "t" and attack == false and ModeOfGlitch == 5 then
		resetmode()
	end
if k == "m" and attack == false and ModeOfGlitch == 8376532578634534 and ModeOfGlitch ~= 47 then
               ModeOfGlitch = 47
storehumanoidWS = 90
hum.WalkSpeed = 90
rainbowmode = false
chaosmode = false
RecolorTextAndRename("L O S T  S O U L",Color3.new(0.5,0,0),Color3.new(0.1,0,0),"Arcade")
newTheme("rbxassetid://353645187",0,1,0.85)
MAINRUINCOLOR = BrickColor.new("Crimson")
RecolorThing2(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Material = "SmoothPlastic"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Material = "SmoothPlastic"
end
end
end
	if k == "b" and attack == false and ModeOfGlitch == 5 then
		ModeOfGlitch = 111111112
		storehumanoidWS = 16
		hum.WalkSpeed = 16
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Darkness", Color3.new(1, 1, 1), Color3.new(0, 0, 0),"Antique")
		newTheme("rbxassetid://601069330", 10, 1, 3)		
		MAINRUINCOLOR = BrickColor.new("Really black")
		disably = false
		warnedpeople("Darkness rises..","Antique",BrickColor.new("White").Color,BrickColor.new("Really black").Color)
		disably = true
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Really black"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,0.5,MAINRUINCOLOR,0.5,MAINRUINCOLOR,true,false)
	elseif k == "b" and attack == false and ModeOfGlitch == 111111112 then
		resetmode()
	end
	if k == "m" and attack == false and ModeOfGlitch == 5 then
		ModeOfGlitch = 109124
		MAINRUINCOLOR = BrickColor.new("Really black")
		storehumanoidWS = 10
		hum.WalkSpeed = 10
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
			newTheme("rbxassetid://108258362263996", 10, 1, 0.7)	--rainbow 12578935192 
		chatfunc("Bye bye.. Baby blue..", MAINRUINCOLOR.Color)
		kan.TimePosition = 9
		RecolorTextAndRename("Bye bye..", Color3.new(0, 0, 0), Color3.new(0, 0, 0),"Antique")	
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0				
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0				
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "m" and attack == false and ModeOfGlitch == 109124 then
		resetmode()
	end
	if k == "y" and attack == false and ModeOfGlitch ~= 6 then
		ModeOfGlitch = 6
		storehumanoidWS = 75
		hum.WalkSpeed = 75
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Glitched", Color3.new(0,0,0),Color3.new(1,1,1),"Fantasy")
		newTheme("rbxassetid://128506208052160", 0, 0.32, 4) --pitche change herer
		MAINRUINCOLOR = BrickColor.new("Really black")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("White")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("Really black")
				v.Material = "Ice"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		
		
	elseif k == "y" and attack == false and ModeOfGlitch == 6 then
		resetmode()
	end
if k == "n" and attack == false and ModeOfGlitch == 6 then
               ModeOfGlitch = 1055
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
RecolorTextAndRename("Pandora",BrickColor.new("White").Color,BrickColor.new("Lavender").Color,"Code")
newTheme("rbxassetid://12489148247",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Lavender")
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Lavender"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
	elseif k == "n" and attack == false and ModeOfGlitch == 1055 then
		resetmode()
	end
if k == "m" and attack == false and ModeOfGlitch == 6 then
attack = true
hum.WalkSpeed = 0
MAINRUINCOLOR = BrickColor.new("Really black")
newTheme("rbxassetid://899090278",0,1.005,1.75)
CamShakeAll(750,150,Character)
local vel = Instance.new("BodyPosition", root)
vel.P = 10000
vel.D = 1000
vel.maxForce = Vector3.new(50000000000, 10e10, 50000000000)
vel.position = root.CFrame.p + vt(0,250,0)
CFuncs["Sound"].Create("rbxassetid://1295446488", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1368598393", char, 7.5, 0.5)
for i = 0, 49 do
slash(math.random(10,100)/10,3,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-10,10)),math.rad(math.random(-360,360)),math.rad(math.random(-10,10))),vt(0.05,0.01,0.05),math.random(25,500)/250,BrickColor.new("White"))
end
local efec = Instance.new("ParticleEmitter",root)
efec.Texture = "rbxassetid://2109052855"
efec.LightEmission = 1
efec.Color = ColorSequence.new(Color3.new(1,0.45,0))
efec.Rate = 5
efec.Lifetime = NumberRange.new(3)
efec.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,75,0),NumberSequenceKeypoint.new(0.2,60,0),NumberSequenceKeypoint.new(0.6,400,0),NumberSequenceKeypoint.new(0.8,300,0),NumberSequenceKeypoint.new(1,200,0)})
efec.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.1,0.25,0),NumberSequenceKeypoint.new(0.6,0.25,0),NumberSequenceKeypoint.new(1,1,0)})
efec.Drag = 5
efec.LockedToPart = true
efec.Rotation = NumberRange.new(-500,500)
efec.VelocitySpread = 9000
efec.RotSpeed = NumberRange.new(-500,500)
local efec2 = efec:Clone()
efec2.LightEmission = 1
efec2.Texture = "rbxassetid://2092248396"
efec2.Parent = root
efec2.Rate = 10
efec2.Lifetime = NumberRange.new(2)
efec2.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,175,0),NumberSequenceKeypoint.new(0.5,150,0),NumberSequenceKeypoint.new(0.8,500,0),NumberSequenceKeypoint.new(1,1000,0)})
efec2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0.5,0),NumberSequenceKeypoint.new(1,1,0)})
efec2.Speed = NumberRange.new(0)
efec2.RotSpeed = NumberRange.new(-100,100)
local efec3 = efec:Clone()
efec3.LightEmission = 1
efec3.Color = ColorSequence.new(Color3.new(1,0.85,0.5))
efec3.Texture = "rbxassetid://2273224484"
efec3.Parent = root
efec3.Rate = 10000
efec3.Drag = 5
efec3.LockedToPart = false
efec3.Lifetime = NumberRange.new(2)
efec3.Size = NumberSequence.new({NumberSequenceKeypoint.new(0,5,0),NumberSequenceKeypoint.new(0.5,10,0),NumberSequenceKeypoint.new(0.8,15,0),NumberSequenceKeypoint.new(1,0,0)})
efec3.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,1,0),NumberSequenceKeypoint.new(0.5,0,0),NumberSequenceKeypoint.new(1,1,0)})
efec3.Speed = NumberRange.new(50,1550)
efec3.RotSpeed = NumberRange.new(-100,100)
for x = 0, 10 do
for i = 0, 1, 0.6 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/30,math.random(-10,10)/30,math.random(-10,10)/30)
sphere2(4,"Add",sorb.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
sphere2(4,"Add",sorb2.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1.05,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(7),math.rad(0),math.rad(-16)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1.05,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-25),math.rad(0),math.rad(97)),.8)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(-27),math.rad(0),math.rad(-98)),.8)
end
for i = 0, 1, 0.6 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/30,math.random(-10,10)/30,math.random(-10,10)/30)
sphere2(4,"Add",sorb.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
sphere2(4,"Add",sorb2.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1.05,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(7),math.rad(0),math.rad(-16)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1.05,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(90)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-25),math.rad(0),math.rad(97)),.8)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(-27),math.rad(0),math.rad(-98)),.8)
end
for i = 0, 1, 0.6 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/30,math.random(-10,10)/30,math.random(-10,10)/30)
sphere2(4,"Add",sorb.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
sphere2(4,"Add",sorb2.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1.05,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(7),math.rad(0),math.rad(-16)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1.05,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(180)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-25),math.rad(0),math.rad(97)),.8)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(-27),math.rad(0),math.rad(-98)),.8)
end
for i = 0, 1, 0.6 do
task.wait()
hum.CameraOffset = vt(math.random(-10,10)/30,math.random(-10,10)/30,math.random(-10,10)/30)
sphere2(4,"Add",sorb.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
sphere2(4,"Add",sorb2.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),0.1,0.1,0.1,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-1.05,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(7),math.rad(0),math.rad(-16)),.8)
LH.C0=clerp(LH.C0,cf(-1,-1.05,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(10)),.8)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(270)),.8)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-5),math.rad(0),math.rad(0)),.8)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(-25),math.rad(0),math.rad(97)),.8)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(-27),math.rad(0),math.rad(-98)),.8)
end
end
local absval = 0
CFuncs["Sound"].Create("rbxassetid://1368583274", char, 7.5, 0.25)
CFuncs["LongSound"].Create("rbxassetid://1368583274", char, 7.5, 0.5)
for i = 0, 40, 0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-20,20)/10*absval/2,math.random(-20,20)/10*absval/2,math.random(-20,20)/10*absval/2)
absval = absval + 0.01
slash(math.random(50,100)/10,2,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(absval*2,0.01,absval*2),math.random(10,100)/1000,BrickColor.new("Really red"))
slash(math.random(10,100)/10,2,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(absval/3,0.01,absval/3),math.random(50,100)/100,BrickColor.new("Really red"))
for i = 0, 1 do
sphere2(4,"Add",root.CFrame*CFrame.new(math.random(-absval*200,absval*200),math.random(-25,25),math.random(-absval*200,absval*200)),vt(1,1,1),0.35,0.35,0.35,MAINRUINCOLOR)
end
sphere2(4,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),absval,absval,absval,MAINRUINCOLOR)
sphere2(4,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(15,5,15),-0.15,absval*5,-0.15,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-0.05,-0.75)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.5,-0.25)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(20 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(55),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
end
for i = 0, 25, 0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-20,20)/10*absval/2,math.random(-20,20)/10*absval/2,math.random(-20,20)/10*absval/2)
slash(math.random(50,100)/10,2,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(absval*2,0.01,absval*2),math.random(10,100)/1000,BrickColor.new("Really red"))
slash(math.random(10,100)/10,2,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(absval/3,0.01,absval/3),math.random(50,100)/100,BrickColor.new("Really red"))
for i = 0, 1 do
sphere2(4,"Add",root.CFrame*CFrame.new(math.random(-absval*200,absval*200),math.random(-25,25),math.random(-absval*200,absval*200)),vt(1,1,1),0.35,0.35,0.35,MAINRUINCOLOR)
end
sphere2(4,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),absval,absval,absval,MAINRUINCOLOR)
sphere2(4,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(15,5,15),-0.15,absval*5,-0.15,MAINRUINCOLOR)
RH.C0=clerp(RH.C0,cf(1,-0.05,-0.75)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.5,-0.25)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(20 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(55),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
end
efec.Enabled = false
efec2.Enabled = false
efec3.Enabled = false
CFuncs["Sound"].Create("rbxassetid://1368637781", char, 5, 0.25)
CFuncs["Sound"].Create("rbxassetid://1368637781", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1368637781", char, 5, 0.75)
CFuncs["Sound"].Create("rbxassetid://1368637781", char, 7.5, 1)
CFuncs["Sound"].Create("rbxassetid://1368605755", char, 7.5, 1)
CFuncs["Sound"].Create("rbxassetid://763718160", char, 10, 0.5)
CFuncs["Sound"].Create("rbxassetid://763718160", char, 10, 0.25)
CFuncs["Sound"].Create("rbxassetid://782353443", char, 10, 1)
CFuncs["Sound"].Create("rbxassetid://782353443", char, 10, 0.75)
CFuncs["LongSound"].Create("rbxassetid://782353443", char, 10, 0.5)
CFuncs["LongSound"].Create("rbxassetid://782353443", char, 10, 0.25)
for i = 0, 2 do
CFuncs["Sound"].Create("rbxassetid://763717897", char, 10, 0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 10, 1)
end
for i = 0, 99 do
local dis = CreateParta(char,1,1,"Neon",MAINRUINCOLOR)
dis.CFrame = root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),math.random(-5,5))*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360)))
local at1 = Instance.new("Attachment",dis)
at1.Position = vt(-25000,0,0)
local at2 = Instance.new("Attachment",dis)
at2.Position = vt(25000,0,0)
local trl = Instance.new('Trail',dis)
trl.Attachment0 = at1
trl.FaceCamera = true
trl.Attachment1 = at2
trl.Texture = "rbxassetid://1049219073"
trl.LightEmission = 1
trl.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0, 0),NumberSequenceKeypoint.new(1, 1)})
trl.Color = ColorSequence.new(MAINRUINCOLOR.Color)
trl.Lifetime = 5
local bv = Instance.new("BodyVelocity")
bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
bv.velocity = dis.CFrame.lookVector*math.random(500,2500)
bv.Parent = dis
game:GetService("Debris"):AddItem(dis, 15)
end
for i = 0, 49 do
sphere2(1,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(10,10,10),-0.1,absval*100,-0.1,MAINRUINCOLOR)
end
for i = 0, 9, 0.1 do
task.wait()
hum.CameraOffset = vt(math.random(-20,20)/5*absval,math.random(-20,20)/5*absval,math.random(-20,20)/5*absval)
sphere2(9,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),absval+5,absval+5,absval+5,MAINRUINCOLOR)
for i = 0, 4 do
slash(math.random(10,50)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(absval/2,0.01,absval/2),math.random(50,5000)/100,BrickColor.new("Really red"))
end
RH.C0=clerp(RH.C0,cf(1,-0.05,-0.75)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.5,-0.25)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(20 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(55),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
end
hum.CameraOffset = vt(0,0,0)
vel:Destroy()
efec:Destroy()
efec2:Destroy()
efec3:Destroy()
ModeOfGlitch = 765688533321
storehumanoidWS = 260
hum.WalkSpeed = 260
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false

RecolorTextAndRename("UNSTABLE",Color3.new(1,1,1),Color3.new(1,0,0),"Arcade")
disably = false
warnedpeople("UNSTABLE POWER!!","Arcade",BrickColor.new("Really red").Color,BrickColor.new("White").Color)
disably = true
MAINRUINCOLOR = BrickColor.new("Really black")
RecolorThing(BrickColor.new("Institutional white"),0,BrickColor.new("Really red"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,0,BrickColor.new("Crimson"),0,BrickColor.new("Really black"),true,true)
attack = false
end
if k == "m" and attack == false and ModeOfGlitch == 1 and ModeOfGlitch ~= 99999123778356 then
               ModeOfGlitch = 99999123778356
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("NUCLEAR",BrickColor.new("Lime green").Color,Color3.new(0.1,1,0),"Antique")
newTheme("rbxassetid://12643311678",0,1.01,1.5)
MAINRUINCOLOR = BrickColor.new("Lime green")
RecolorThing(MAINRUINCOLOR,0,BrickColor.new("Bright green"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "n" and attack == false and ModeOfGlitch == 99999123778356 and ModeOfGlitch ~= 01010101000001 then
ModeOfGlitch = 01010101000001
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("NUCLEAR V",Color3.new(0,1,0),Color3.new(0.8,1,0.5),"Bodoni")
newTheme("rbxassetid://798163149",2,2,1.25)
MAINRUINCOLOR = BrickColor.new("Forest green")
RecolorThing(MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true)
coroutine.resume(coroutine.create(function()
repeat
task.wait()
if ModeOfGlitch == 01010101000001 then
for i,v in pairs(mw1:GetChildren())do	
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
end
end
task.wait()
if ModeOfGlitch == 01010101000001 then
for i,v in pairs(mw2:GetChildren())do	
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
end
end
until ModeOfGlitch ~= 01010101000001
end))
end
if k == "two" and attack == false and ModeOfGlitch ~= 0101 then
ModeOfGlitch = 0101
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Infected",Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20)),Color3.new(0,0,0),"Antique")
newTheme("rbxassetid://798163149",3,3,1.25)
MAINRUINCOLOR = BrickColor.new("Really black")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
coroutine.resume(coroutine.create(function()
repeat
task.wait()
if ModeOfGlitch == 0101 then
for i,v in pairs(mw1:GetChildren())do	
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
end
end
task.wait()
if ModeOfGlitch == 0101 then
for i,v in pairs(mw2:GetChildren())do	
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
end
end
until ModeOfGlitch ~= 0101
end))
end
if k == "n" and attack == false and ModeOfGlitch == 1 and ModeOfGlitch ~= 9797 then
		ModeOfGlitch = 9797
		storehumanoidWS = 75
		hum.WalkSpeed = 75
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("Natural",Color3.new(1,1,1),BrickColor.new("Forest green").Color,"Code")
		newTheme("rbxassetid://181761264",0,1,1.4)
		MAINRUINCOLOR = BrickColor.new("Dark green")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Forest green")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Lime green")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Bright green")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.new("Sage green")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		
		
	elseif k == "n" and attack == false and ModeOfGlitch == 9797 then
		resetmode()
	end
if k == "b" and attack == false and ModeOfGlitch == 1 and ModeOfGlitch ~= 666 then
newThemeCust("rbxassetid://383141805",0,0.8,3)
attack = true
hum.WalkSpeed = 0
MAINRUINCOLOR = BrickColor.new("Crimson")
MAINRUINCOLOR2 = BrickColor.new("Really black")
for i = 0, 24, 0.1 do
task.wait()
sphereMK(1,-2,"Add",tors.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2.5,2.5,15,-0.025,MAINRUINCOLOR,100)
RH.C0=clerp(RH.C0,cf(1,-0.05,-0.75)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-30)),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.5,-0.25)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(30)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(20 - 1 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(55),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
end
CamShakeAll(50,50,Character)
sphere(5,"Add",root.CFrame,vt(0,0,0),2.5,MAINRUINCOLOR)
CFuncs["Sound"].Create("rbxassetid://847061203", char, 0.5,1)
wait(0.55)
CamShakeAll(50,50,Character)
sphere(5,"Add",root.CFrame,vt(0,0,0),7.5,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),5,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),2.5,MAINRUINCOLOR)
CFuncs["Sound"].Create("rbxassetid://847061203", char, 1,1)
wait(0.55)
CamShakeAll(50,50,Character)
sphere(5,"Add",root.CFrame,vt(0,0,0),12.5,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),10,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),7.5,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),5,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),2.5,MAINRUINCOLOR)
CFuncs["Sound"].Create("rbxassetid://847061203", char, 2,1)
wait(0.55)
CamShakeAll(50,50,Character)
CFuncs["Sound"].Create("rbxassetid://741272936", char, 1, 1)
CFuncs["Sound"].Create("rbxassetid://164881112", char, 1, 1)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 1, 1)
CFuncs["Sound"].Create("rbxassetid://429123896", char, 1, 0.85)
CFuncs["Sound"].Create("rbxassetid://1208650519", char, 1, 1)
sphere(1,"Add",root.CFrame,vt(0,0,0),2,MAINRUINCOLOR)
sphere(2,"Add",root.CFrame,vt(0,0,0),4,MAINRUINCOLOR)
sphere(3,"Add",root.CFrame,vt(0,0,0),6,MAINRUINCOLOR)
sphere(4,"Add",root.CFrame,vt(0,0,0),8,MAINRUINCOLOR)
sphere(5,"Add",root.CFrame,vt(0,0,0),10,MAINRUINCOLOR)
sphere(6,"Add",root.CFrame,vt(0,0,0),12,MAINRUINCOLOR)
sphere(7,"Add",root.CFrame,vt(0,0,0),14,MAINRUINCOLOR)
sphere(8,"Add",root.CFrame,vt(0,0,0),16,MAINRUINCOLOR)
sphere(9,"Add",root.CFrame,vt(0,0,0),18,MAINRUINCOLOR)
sphere(10,"Add",root.CFrame,vt(0,0,0),20,MAINRUINCOLOR)
for i = 0, 49 do
sphereMK(1,3,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),50,50,200,-1,MAINRUINCOLOR,0)
sphereMK(2,6,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),50,50,150,-0.5,MAINRUINCOLOR,0)
sphereMK(3,9,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),50,50,100,-0.5,MAINRUINCOLOR,0)
sphereMK(4,12,"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),50,50,50,-0.5,MAINRUINCOLOR,0)
end
ModeOfGlitch = 666
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
RecolorTextAndRename("Hero?",Color3.new(1,0,0),Color3.new(0.75,0,0),"Antique")
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = MAINRUINCOLOR
v.Material = "Neon"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = MAINRUINCOLOR
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.Color = Color3.new(1,0,0)
v.Material = "Neon"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.Color = Color3.new(1,0,0)
v.Material = "Neon"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.Color = Color3.new(1,0,0)
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.new(1,0,0)
v.Material = "Neon"
end
end
for i, v in pairs(extrawingmod2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.new(1,0,0)
v.Material = "Neon"
end
attack = false
end
elseif k == "b" and attack == false and ModeOfGlitch == 666 then
resetmode()
end
	if k == "u" and attack == false and ModeOfGlitch ~= 6127843 then
		ModeOfGlitch = 6127843
		storehumanoidWS = 50
		hum.WalkSpeed = 50
		rainbowmode = true
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("RAINBOW", Color3.new(1, 1, 1), Color3.new(1, 1, 1),"Fantasy")
		newTheme("rbxassetid://12578935192", 0, 1, 1)
		MAINRUINCOLOR = BrickColor.new("White")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.BrickColor = BrickColor.new("White")
				v.Material = "Neon"
			end
		end
	elseif k == "u" and attack == false and ModeOfGlitch == 6127843 then
		resetmode()
	end
	if k == "p" and attack == false and ModeOfGlitch ~= 1000000 then
		ModeOfGlitch = 1000000
		storehumanoidWS = 100
		hum.WalkSpeed = 100
		rainbowmode = false
		chaosmode = false
        insanitymode = false
		glitching = false
		RecolorTextAndRename("True Starlight", Color3.new(0.25, 0, 1), Color3.new(0.5, 0, 1),"Antique")
		newTheme("rbxassetid://363284685", 0, 1, 1)
		MAINRUINCOLOR = BrickColor.new("Bright violet")
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(0.5, 0, 1)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(0.25, 0, 1)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(0.45, 0, 1)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.Color = Color3.new(0.25, 0, 1)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.Color = Color3.new(0.5, 0, 1)
				v.Material = "Neon"
			end
		end
	elseif k == "p" and attack == false and ModeOfGlitch == 1000000 then
		resetmode()
	end
if k == "m" and attack == false and ModeOfGlitch == 1000000 and ModeOfGlitch ~= 808080 then
               ModeOfGlitch = 808080
storehumanoidWS = 250
hum.WalkSpeed = 250
rainbowmode = false
chaosmode = false
insanitymode = false
glitching = false
CFuncs["Sound"].Create("rbxassetid://763717897", char, 4, 0.75)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 8, 0.5)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 10, 0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 6, 0.5)

RecolorTextAndRename("Celestial Eye",BrickColor.new("Alder").Color,BrickColor.new("Really blue").Color,"Bodoni")
newThemeCust("rbxassetid://398455752",0,1.01,2)
MAINRUINCOLOR = BrickColor.new("Really blue")
chatfunc("Celestial eye wing weld by wwwargos", MAINRUINCOLOR.Color)
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Dark indigo"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,0,BrickColor.new("Alder"),0,BrickColor.new("Pastel light blue"),true,true)
end
	elseif Diversial == true then --< from spectrum to put in UG modes
-- Universal Glitcher Started-----------------
if k == "q" and attack == false and ModeOfGlitch ~= 90909 then
MRCL = BrickColor.new"Toothpaste"
MRCL2 = BrickColor.new"White"
               ModeOfGlitch = 90909
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("EXQUISITE",BrickColor.new("Toothpaste").Color,BrickColor.new("Mint").Color,"Antique")
newTheme("rbxassetid://2128137966",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Toothpaste")
RecolorThing(BrickColor.new("Toothpaste"),0,BrickColor.new("Mint"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,BrickColor.new("Deep orange"),true,false)
end
if k == "e" and attack == false and ModeOfGlitch ~= 2002 then
               ModeOfGlitch = 2002
MRCL = BrickColor.new"Alder"
MRCL2 = BrickColor.new"White"
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("ABERIATION",BrickColor.new("Alder").Color,BrickColor.new("White").Color,"Bodoni")
newTheme("rbxassetid://1002071384",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Alder")
RecolorThing(BrickColor.new("Alder"),0,BrickColor.new("White"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,BrickColor.new("Deep orange"),true,false)
end
if k == "r" and attack == false and ModeOfGlitch ~= 3003 then
MRCL = BrickColor.new"Baby blue"
MRCL2 = BrickColor.new"White"
               ModeOfGlitch = 3003
storehumanoidWS = 70
hum.WalkSpeed = 70
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("SCINTILLANT",BrickColor.new("White").Color,BrickColor.new("Baby blue").Color,"SciFi")
newTheme("rbxassetid://1861780345",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Baby blue")
RecolorThing(BrickColor.new("Baby blue"),0,BrickColor.new("White"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,BrickColor.new("Deep orange"),true,false)
end
if k == "one" and attack == false and ModeOfGlitch ~= 7788 then
MRCL = BrickColor.new"Ghost grey"
MRCL2 = BrickColor.new"Dark stone grey"
               ModeOfGlitch = 7788
storehumanoidWS = 0
hum.WalkSpeed = 0
rainbowmode = false
chaosmode = false
insanitymode = false
universalchaos = false
RecolorTextAndRename("Chill",Color3.new(34,34,34),BrickColor.new("Ghost grey").Color,"Fantasy")
newTheme("rbxassetid://452385370",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Dark stone grey")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Cloudy grey"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "two" and attack == false and ModeOfGlitch ~= 7788 then
MRCL = BrickColor.new"Alder"
MRCL2 = BrickColor.new"Dark blue"
               ModeOfGlitch = 929292
storehumanoidWS = 32
hum.WalkSpeed = 32
rainbowmode = false
chaosmode = false
insanitymode = false
universalchaos = false
RecolorTextAndRename("Dream",Color3.new(0,0,255),BrickColor.new("Navy blue").Color,"Fantasy")
newTheme("rbxassetid://1341134893",0,1,2)
MAINRUINCOLOR = BrickColor.new("Dark blue")
RecolorThing2(MAINRUINCOLOR,0,BrickColor.new("Alder"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "three" and attack == false and ModeOfGlitch ~= 40044 then
MRCL = BrickColor.new"Black"
MRCL2 = BrickColor.new"Black"
               ModeOfGlitch = 40044
storehumanoidWS = 50
hum.WalkSpeed = 50
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("HATRED",BrickColor.new("Black").Color,BrickColor.new("Black").Color,"SciFi")
newTheme("rbxassetid://2098624159",0,1.02,1.25)
MAINRUINCOLOR = BrickColor.new("Black")
RecolorThing(BrickColor.new("Black"),0,BrickColor.new("Black"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Black"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "t" and attack == false and ModeOfGlitch ~= 5005 then
MRCL = BrickColor.new"Dark blue"
MRCL2 = BrickColor.new"Really red"
               ModeOfGlitch = 5005
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("DYSMORPHIC",BrickColor.new("Really red").Color,BrickColor.new("Dark indigo").Color,"Arcade")
newTheme("rbxassetid://1751171913",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Really red")
RecolorThing(BrickColor.new("Really red"),0,BrickColor.new("Dark indigo"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,BrickColor.new("Deep orange"),true,false)
end
if k == "y" and attack == false and ModeOfGlitch ~= 6006 then
MRCL = BrickColor.new"Really black"
MRCL2 = BrickColor.new"Maroon"
               ModeOfGlitch = 6006
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("RECALCITRANT",BrickColor.new("Really black").Color,BrickColor.new("Maroon").Color,"Antique")
newTheme("rbxassetid://1119709168",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Maroon")
RecolorThing(BrickColor.new("Maroon"),0,BrickColor.new("Really black"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Maroon"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "u" and attack == false and ModeOfGlitch ~= 7007 then
MRCL = BrickColor.new"White"
MRCL2 = BrickColor.new"Cool yellow"
               ModeOfGlitch = 7007
storehumanoidWS = 70
hum.WalkSpeed = 70
rainbowmode = false
chaosmode = false
universalchaos = false
RecolorTextAndRename("SERAPHIC",BrickColor.new("Brick yellow").Color,BrickColor.new("Cool yellow").Color,"SciFi")
newTheme("rbxassetid://2127419486",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Cool yellow")
RecolorThing(BrickColor.new("Cool yellow"),0,BrickColor.new("Brick yellow"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Cool yellow"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "h" and attack == false and ModeOfGlitch ~= 4004 then
MRCL = BrickColor.new"Black"
MRCL2 = BrickColor.new"Black"
               ModeOfGlitch = 4004
storehumanoidWS = 16
hum.WalkSpeed = 16
rainbowmode = false
chaosmode = false
universalchaos = true
RecolorTextAndRename("CALATUSTIC",BrickColor.new("Black").Color,BrickColor.new("Black").Color,"SciFi")
newTheme("rbxassetid://1276814239",0,1,1.3)
MAINRUINCOLOR = BrickColor.new("Black")
RecolorThing(BrickColor.new("Black"),0,BrickColor.new("Black"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Black"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "j" and attack == false and ModeOfGlitch ~= 10 then
MRCL = BrickColor.new"Lilac"
MRCL2 = BrickColor.new"Royal purple"
               ModeOfGlitch = 10
storehumanoidWS = 100
hum.WalkSpeed = 100
rainbowmode = false
chaosmode = false
universalchaos = false
tbeam(BrickColor.new("Lilac"),BrickColor.new("Royal purple"))
CFuncs["Sound"].Create("rbxassetid://763717897", char, 4, 0.75)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 1.2, 0.5)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 3, 0.5)
RecolorTextAndRename("SERVANTISTUALITY",BrickColor.new("Lilac").Color,BrickColor.new("Royal purple").Color,"SciFi")
newTheme("rbxassetid://1301290348",0,1,1.3)
MAINRUINCOLOR = BrickColor.new("Lilac")
RecolorThing(BrickColor.new("Lilac"),0,BrickColor.new("Royal purple"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Royal purple"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "f" and attack == false and ModeOfGlitch ~= 9 then
               ModeOfGlitch = 9
storehumanoidWS = 16
hum.WalkSpeed = 16
MRCL = BrickColor.new"New Yeller"
MRCL2 = BrickColor.new"Lime green"
rainbowmode = false
chaosmode = false
universalchaos = false
tbeam(BrickColor.new("Lime green"),BrickColor.new("New Yeller"))
CFuncs["Sound"].Create("rbxassetid://763717897", char, 4, 0.75)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 1.2, 0.5)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 3, 0.5)
RecolorTextAndRename("ALACRITY",BrickColor.new("Lime green").Color,BrickColor.new("New Yeller").Color,"Bodoni")
newTheme("rbxassetid://2127505351",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Lime green")
RecolorThing(BrickColor.new("Lime green"),0,BrickColor.new("New Yeller"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("New Yeller"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
if k == "g" and attack == false and ModeOfGlitch ~= 8 then
               ModeOfGlitch = 8
storehumanoidWS = 100
hum.WalkSpeed = 100
MRCL = BrickColor.new("Really black")
MRCL2 = BrickColor.new"Royal purple"
rainbowmode = false
chaosmode = false
universalchaos = false
tbeam(BrickColor.new("Really black"),BrickColor.new("Royal purple"))
CFuncs["Sound"].Create("rbxassetid://763717897", char, 4, 0.75)
CFuncs["Sound"].Create("rbxassetid://763717897", char, 1.2, 0.5)
CFuncs["Sound"].Create("rbxassetid://1192402877", char, 5, 0.5)
CFuncs["Sound"].Create("rbxassetid://1664711478", char, 3, 0.5)
RecolorTextAndRename("DIMENTIA",BrickColor.new("Really black").Color,BrickColor.new("Royal purple").Color,"Antique")
newTheme("rbxassetid://2482043741",0,1,1.25)
MAINRUINCOLOR = BrickColor.new("Royal purple")
RecolorThing(BrickColor.new("Royal purple"),0,BrickColor.new("Really black"),MAINRUINCOLOR,MAINRUINCOLOR,BrickColor.new("Royal purple"),1,MAINRUINCOLOR,1,MAINRUINCOLOR,true,false)
end
end
	if k == "l" and toggleTag == false then
		toggleTag = true
		text.TextTransparency = 0
		text.TextStrokeTransparency = 0
	elseif k == "l" and toggleTag == true then
		toggleTag = false
		text.TextTransparency = 1
		text.TextStrokeTransparency = 1
	end
if k == "semicolon" and mutedtog == false then
mutedtog = true
kan.Volume = 0
elseif k == "semicolon" and mutedtog == true then
mutedtog = false
kan.Volume = currentVol
end
if k == "v" and Diversial == false and attack == false and ModeOfGlitch == 1 then
Diversial = true
ModeOfGlitch = 676767
storehumanoidWS = 250
hum.WalkSpeed = 250
ModeFrame.Text = "Universal Glitcher"
rainbowmode = false
chaosmode = false
insanitymode = false

RecolorTextAndRename("Universal Glitcher",Color3.new(1,1,1),BrickColor.new("Royal purple").Color,"SciFi")
newTheme("rbxassetid://603567552",0,1.02,1.25)
MAINRUINCOLOR = BrickColor.new("Royal purple")
RecolorThing2(BrickColor.new("Royal purple"),0,BrickColor.new("Royal purple"),MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,0,MAINRUINCOLOR,0,BrickColor.new("Royal purple"),true,true)
elseif k == "v" and Diversial == true and attack == false then
insanitymode = false
Diversial = false
resetmode()
ModeOfGlitch = 1
storehumanoidWS = 16
hum.WalkSpeed = 16
ModeFrame.Text = "Star Glitcher"
rainbowmode = false
chaosmode = false
insanitymode = false
universalchaos = false
newTheme("rbxassetid://12489056016",48.6,1,1.25)

RecolorTextAndRename("MAYHEM",Color3.new(0.25,0,0),Color3.new(1,0,0),"Antique")
MAINRUINCOLOR = BrickColor.new("Really red")
RecolorThing(MAINRUINCOLOR,0,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,MAINRUINCOLOR,1,MAINRUINCOLOR,1,MAINRUINCOLOR,false,false)
end
	if k == "z" and attack == false and ModeOfGlitch == 1 then
		ExtinctiveHeartbreak()
	elseif k == "z" and attack == false and ModeOfGlitch == 5 then
		ExtinctiveHeartbreak()
	elseif k == "period" and attack == false and equipped == true then		
		leapbreaker()
	elseif k == "z" and attack == false and ModeOfGlitch == 109124 then		
		ByeBye()
	elseif k == "x" and attack == false and ModeOfGlitch == 109124 then		
		Sayonara()
	elseif k == "c" and attack == false and ModeOfGlitch == 109124 then		
		Good_Bye()
	elseif k == "v" and attack == false and ModeOfGlitch == 109124 then	
		AlohaMyFriend()
	elseif k == "b" and attack == false and ModeOfGlitch == 109124 then		
		Taunt()
	elseif k == "z" and attack == false and ModeOfGlitch == 7788 then		
		BeamLol()
	elseif k == "n" and attack == false and ModeOfGlitch == 109124 then		
		Taunt2()
	elseif k == "z" and attack == false and ModeOfGlitch == 688 then		
		WavedOut()
	elseif k == "x" and attack == false and ModeOfGlitch == 929292 then		
		WavedOut()
elseif k == "x" and attack == false and ModeOfGlitch == 1 then
		EndGROUND()
	elseif k == "z" and attack == false and ModeOfGlitch == 6006 then
		annihilation()
	elseif k == "c" and attack == false and ModeOfGlitch == 929292 then
		annihilation2()
	elseif k == "x" and attack == false and ModeOfGlitch == 5005 then
		annihilation3()
elseif k == "z" and attack == false and ModeOfGlitch == 40044 then
ChaosGroundStrikeop()
elseif k == "x" and attack == false and ModeOfGlitch == 40044 then
ChaosBegoneOP() 
elseif k == "z" and attack == false and ModeOfGlitch == 2002 then
shdnontwist()
	elseif k == "z" and attack == false and ModeOfGlitch == 9 then
		BigBoy()
	elseif k == "z" and attack == false and ModeOfGlitch == 8 then
		CorruptionEvent()
	elseif k == "z" and attack == false and ModeOfGlitch == 4004 then
		EternalChaosOrb()
	elseif k == "z" and attack == false and ModeOfGlitch == 90909 then
		ExquisiteDisk()
	elseif k == "z" and attack == false and ModeOfGlitch == 99999123778356 then
		NuclearJump()
	elseif k == "b" and attack == false and ModeOfGlitch == 6 then
		balancedmode()
	elseif k == "z" and attack == false and ModeOfGlitch == 5005 then
		BURNINHELL()	
	elseif k == "z" and attack == false and ModeOfGlitch == 3003 then
		JusticeBeam()
	elseif k == "x" and attack == false and ModeOfGlitch == 688 then		
		Waved()
	elseif k == "z" and attack == false and ModeOfGlitch == 912 then		
		CoredOmega()
	elseif k == "z" and attack == false and ModeOfGlitch == 91234 then		
		Cybersplosion()
	elseif k == "x" and attack == false and ModeOfGlitch == 91234 then		
		cyberstomp()
	elseif k == "c" and attack == false and ModeOfGlitch == 91234 then		
		blink()
	elseif k == "z" and attack == false and ModeOfGlitch == 912345 then		
		uselessnuke()
	elseif k == "x" and attack == false and ModeOfGlitch == 912345 then		
		Laserbeamy()
	elseif k == "z" and attack == false and ModeOfGlitch == 929292 then		
		Laserbeamy()
	elseif k == "z" and attack == false and ModeOfGlitch == 912345678 then		
		Dirtface()
	elseif k == "z" and attack == false and ModeOfGlitch == 9123 then		
		GreedStorm()
elseif k == "h" and attack == false and advanced == false and Diversial == false then
	equip1()
elseif k == "h" and attack == false and advanced == true and Diversial == false then
   unequip1()
	elseif k == "n" and attack == false and ModeOfGlitch == 5 then
		RiddleMeThisRiddleMeThat()
	elseif k == "z" and attack == false and ModeOfGlitch == 666 then
		CalMets()
	elseif k == "x" and attack == false and ModeOfGlitch == 666 then
		ExtCalbeam()
	elseif k == "z" and attack == false and ModeOfGlitch == 10 then
		CalMets()
	elseif k == "x" and attack == false and ModeOfGlitch == 10 then
		ExtCalbeam()
	elseif k == "z" and attack == false and ModeOfGlitch == 67966 then
		lovesqueal()
	elseif k == "x" and attack == false and ModeOfGlitch == 67966 then
		cutesigh()
	elseif k == "z" and attack == false and ModeOfGlitch == 2 then
		PureBomb()
	elseif k == "z" and attack == false and ModeOfGlitch == 111111112 then
		Flame_Burst()
	elseif k == "x" and attack == false and ModeOfGlitch == 111111112 then
		Taunt10000()
	elseif k == "z" and attack == false and ModeOfGlitch == 3 then
		scattercorrupt()
	elseif k == "z" and attack == false and ModeOfGlitch == 4 then
		ChaosGroundStrike()
	elseif k == "x" and attack == false and ModeOfGlitch == 998877 then
		ChaosGroundStrike2()
	elseif k == "z" and attack == false and ModeOfGlitch == 8787 then
		ChaosGroundStrike()
	elseif k == "z" and attack == false and ModeOfGlitch == 1000000 then
		UniversalSpark()
	elseif k == "z" and attack == false and ModeOfGlitch == 146536 then
		Fanta()
	elseif k == "z" and attack == false and ModeOfGlitch == 998877 then
		Fanta()
	elseif k == "z" and attack == false and ModeOfGlitch == 2334 then
		TheoriesTran()
	elseif k == "l" and attack == false then		
		SCREEE()
    elseif k == "x" and attack == false and ModeOfGlitch == 1000000 then
        scattercorrupt()
        wait(1)
        yinyangi()
    elseif k == "c" and attack == false and ModeOfGlitch == 1000000 then
		DETERMINED()
    elseif k == "z" and attack == false and ModeOfGlitch == 699 then		
		STRIKE()
    elseif k == "z" and attack == false and ModeOfGlitch == 151353 then		
		kickcombo()
    elseif k == "x" and attack == false and ModeOfGlitch == 5 then
        scattercorrupt()
        scattercorrupt()
	elseif k == "z" and attack == false and ModeOfGlitch == 6 then
		yinyangi()
	elseif k == "x" and attack == false and ModeOfGlitch == 4 then
		ChaosBegone()
	elseif k == "c" and attack == false and ModeOfGlitch == 4 then
		RapidBurst()		
	elseif k == "z" and attack == false and ModeOfGlitch == 6127843 then
		Wip()
	end
	if k == "x" and attack == false and ModeOfGlitch == 8787 then
		ScatterChaos()
		        wait(1)
        ChaosBegone()
	elseif k == "f" and attack == false and ModeOfGlitch == 1 and ActiveGia == false then
	THEHELLITSTHATBIG()
	elseif k == "f" and attack == false and ModeOfGlitch == 1 and ActiveGia == true then
	removelol()
	end
	
--[[if k == "v" and etypemodes == "OP" and ModeOfGlitch == 1 then
etypemodes = "U"
ModeFrame.Text = "UNIVERSAL"
elseif k == "v" and etypemodes == "U" then
etypemodes = "S"
ModeFrame.Text = "STAR"
elseif k == "v" and etypemodes == "S" then
etypemodes = "SM"
ModeFrame.Text = "STAR MAJORS"
elseif k == "v" and etypemodes == "SM" then
etypemodes = "SN"
ModeFrame.Text = "STAR NONCANONS"
elseif k == "v" and etypemodes == "SN" then
etypemodes = "G"
ModeFrame.Text = "GALAXY"
elseif k == "v" and etypemodes == "G" then
etypemodes = "GM"
ModeFrame.Text = "GALAXY MAJORS"
elseif k == "v" and etypemodes == "GM" then
etypemodes = "OP"
ModeFrame.Text = "OP MODES"
end]]--
	end)
	
	plr.Chatted:connect(function(message)
if ModeOfGlitch == 9123851 then
if message:sub(1,5) == "play/" then
OVMID = message:sub(6)
newThemeCust("rbxassetid://"..OVMID,0,OVMPIT,OVMVOL)
elseif message:sub(1,4) == "pit/" then
OVMPIT = message:sub(7)
newTheme("rbxassetid://"..OVMID,0,OVMPIT,OVMVOL)
elseif message:sub(1,4) == "vol/" then
OVMVOL = message:sub(5)
newTheme("rbxassetid://"..OVMID,0,OVMPIT,OVMVOL)
elseif message:sub(1,5) == "skip/" then
chatfunc("Skipped to "..message:sub(8).." out of "..math.floor(kan.TimeLength).." seconds.",MAINRUINCOLOR.Color,"Inverted","Arcade",3)
newThemeCust("rbxassetid://"..OVMID,message:sub(8),OVMPIT,OVMVOL)
elseif message:sub(1,5) == "time/" then
chatfunc("Current time pos: "..math.floor(kan.TimePosition).." out of "..math.floor(kan.TimeLength).." seconds.",MAINRUINCOLOR.Color,"Inverted","Arcade",3)
end
end
end)
coroutine.resume(coroutine.create(function()
	while true do
		task.wait(0.2)
		if rainbowmode == true or ModeOfGlitch == 6 then
			sphereMK(5, 0.15, "Add", root.CFrame * CFrame.new(math.random(-5, 5), -6, math.random(-5, 5)) * CFrame.Angles(math.rad(90), 0, 0), 1.5, 1.5, 10, -0.015, MAINRUINCOLOR, 0)
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch == 1000000 then
			sphereMK(5, 0.5, "Add", root.CFrame * CFrame.new(math.random(-25, 25), -10, math.random(-25, 25)) * CFrame.Angles(math.rad(90 + math.random(-15, 15)), math.rad(math.random(-15, 15)), 0), 1, 1, 15, -0.01, MAINRUINCOLOR, 0)
		elseif ModeOfGlitch == 146536 then
			sphereMK(5,math.random(8,14)/45,"Add",root.CFrame*CFrame.new(math.random(-15,15),-10,math.random(-15,15))*CFrame.Angles(math.rad(90 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),0.75,0.75,20,-0.0075,MAINRUINCOLOR,0)
if ModeOfGlitch == 6 or ModeOfGlitch == 99999123778356 or ModeOfGlitch == 8 or ModeOfGlitch == 9 or ModeOfGlitch == 8889 or ModeOfGlitch == 88893333388 or ModeOfGlitch == 664663666 or ModeOfGlitch == 1264532489 or ModeOfGlitch == 55469696922 or ModeOfGlitch == 4367677813 or ModeOfGlitch == 9999999921111 or ModeOfGlitch == 999999999556 or ModeOfGlitch == 765688533321 or ModeOfGlitch == 808080808080808080808080 then
sphereMK(7.5,math.random(15,50)/45,"Add",root.CFrame*CFrame.new(math.random(-25,25),-10,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),0.75,0.75,10,-0.0075,MAINRUINCOLOR,0)
end
if ModeOfGlitch == 765688533321 then
sphereMK(7.5,math.random(15,50)/45,"Add",root.CFrame*CFrame.new(math.random(-25,25),-10,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),0.75,0.75,10,-0.0075,MAINRUINCOLOR,0)
end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do 
	task.wait()
	if insanitymode == true then
			lolwut = {"DEATH","INSANITY","MISERY","DREAD","CRAZED","CHAOS","VOID","MAYHEM","HeLp ME","LEt Me OuT","SaVe Me!","PLEaSe","KiLl IT!","DIE","hElp!","dEaD","BaNG","OUt!","SAvE","mE","oUt PleAse","savIng!","KiLl aLl","pOp","INSANITY",}
            Sanicz = lolwut[math.random(1,#lolwut)]
           RecolorTextAndRename(Sanicz,BrickColor.Random().Color,BrickColor.Random().Color,"Antique")
            MAINRUINCOLOR = BrickColor.Random()
		end
	end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 688 then
		text.Rotation = -360 * math.cos(sine / 36)
end
end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 109124 then
    local val = math.random(1,26)
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
			Byebye = {"Bye bye..",}
            Cya = Byebye[math.random(1,#Byebye)]
           RecolorTextAndRename(Cya,Color3.new(color),BrickColor.new(color).Color,"Antique")
		local glitch = math.random(1,3)
		if glitch == 1 then
		text.Position = UDim2.new(0,0,0,0)
		text.Rotation = -17 * math.cos(sine / 32)
		elseif glitch == 2 then
		text.Position = UDim2.new(0,0,0,0)
		text.Rotation = -37 * math.cos(sine / 6)
		elseif glitch == 3 then
		text.Position = UDim2.new(0,0,0,0)
		text.Rotation = -5 * math.cos(sine / 17)
		end
    for i, v in pairs(m2:GetChildren()) do
    if v:IsA("Part") then
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m:GetChildren()) do
    if v:IsA("Part") then
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m3:GetChildren()) do
    if v:IsA("Part") then
    v.Color = color
    v.Material = "Neon"
    end
    end
end
end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 666 then
	local val = BrickColor.new("Really red","Really black")
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
RecolorTextAndRename("Hero?", Color3.new(color), BrickColor.new(color).Color,"Fantasy")
    MAINRUINCOLOR = BrickColor.new(color)
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
    v.Color = color
    v.Material = "Neon"
    end
    end
end
end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 6 then
    local val = math.random(1,255)
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
RecolorTextAndRename(RandomCaps"Glitched", Color3.new(color), BrickColor.new(color).Color,"Fantasy")
    MAINRUINCOLOR = BrickColor.new(color)
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
end
end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 998877 then
    local val = math.random(1,34)
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
    MAINRUINCOLOR = BrickColor.new(color)
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
	end
    for i, v in pairs(m3:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
	end
    for i, v in pairs(extrawingmod1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(extrawingmod2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
end
end
end))
coroutine.resume(coroutine.create(function()
		while true do 
	task.wait()
if ModeOfGlitch == 998877 then
    local val = math.random(1,255)
    local color = Color3.fromRGB(val,val,val)
    pcall(function() Character.ReaperShadowHead.Eye1.Color = color end)
    pcall(function() Character.ReaperShadowHead.Eye2.Color = color end)
    MAINRUINCOLOR = BrickColor.new(color)
    for i, v in pairs(mw1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(mw2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(m2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
	end
    for i, v in pairs(m3:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
	end
    for i, v in pairs(extrawingmod1:GetChildren()) do
    if v:IsA("Part") then
    v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
    for i, v in pairs(extrawingmod2:GetChildren()) do
    if v:IsA("Part") then
	v.Transparency = 0
    v.Color = color
    v.Material = "Neon"
    end
    end
end
end
end))

		--
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
	if ModeOfGlitch == 912 then
MAINRUINCOLOR = BrickColor.new("Really red")
refec.Color = ColorSequence.new(BrickColor.new("Really red").Color)
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Really red")
v.Material = "Neon"
end
end
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Really black")
v.Material = "Neon"
end
end
RecolorTextAndRename("Cored",Color3.new(0, 0, 0),Color3.new(151, 0, 0),"Code")
if math.random(1,2) == 1 then
MAINRUINCOLOR = BrickColor.new("Really black")
refec.Color = ColorSequence.new(BrickColor.new("Really black").Color)
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Crimson")
v.Material = "Neon"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.BrickColor = BrickColor.new("Really black")
v.Material = "Neon"
end
end
RecolorTextAndRename("Cored",Color3.new(151, 0, 0),Color3.new(0, 0, 0),"Code")
end
	end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
	if ModeOfGlitch == 912345678 then
MAINRUINCOLOR = BrickColor.new("Crimson")
refec.Color = ColorSequence.new(BrickColor.new("Crimson").Color)
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(196 + math.random(-20,20), 40 + math.random(-20,20), 28 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(196 + math.random(-20,20), 40 + math.random(-20,20), 28 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(196 + math.random(-20,20), 40 + math.random(-20,20), 28 + math.random(-20,20))
v.Material = "Neon"
end
end
RecolorTextAndRename(plr.Name.."'s Retribution",Color3.new(31, 128, 29),Color3.new(151, 0, 0),"Code")
if math.random(1,2) == 1 then
MAINRUINCOLOR = BrickColor.new("Forest green")
refec.Color = ColorSequence.new(BrickColor.new("Forest green").Color)
for i, v in pairs(mw2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(196 + math.random(-20,20), 40 + math.random(-20,20), 28 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(mw1:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m3:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m2:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(196 + math.random(-20,20), 40 + math.random(-20,20), 28 + math.random(-20,20))
v.Material = "Neon"
end
end
for i, v in pairs(m:GetChildren()) do
if v:IsA("Part") then
v.Transparency = 0
v.Color = Color3.fromRGB(31 + math.random(-20,20), 128 + math.random(-20,20), 29 + math.random(-20,20))
v.Material = "Neon"
end
end
RecolorTextAndRename(plr.Name.."'s Retribution",Color3.new(151, 0, 0),Color3.new(0, 255, 0),"Code")
end
	end
	end
end))

coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch ~= 70077 and Diversial == false then
		ModeFrame.Text = "Star Glitcher"
		elseif ModeOfGlitch ~= 70077 and Diversial == true then
		ModeFrame.Text = "Universal Glitcher"
		
		end
		end
		end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch == 70077 then
			RecolorTextAndRename(RandomCaps"guESt GLiTcHEr v999", Color3.new(r / 255, g / 255, b / 255), BrickColor.random().Color,"Fantasy")
			MAINRUINCOLOR = BrickColor.Random()
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if chaosmode == true then
			RecolorTextAndRename("CHAOS", Color3.new(0, 0, 0), BrickColor.random().Color,"Fantasy")
			MAINRUINCOLOR = BrickColor.Random()
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if universalchaos == true then
		RecolorTextAndRename("CALATUSTIC",MRCL.Color,BrickColor.random().Color,"Arcade")
			MAINRUINCOLOR = BrickColor.new("Black")
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch == 40044 then
		RecolorTextAndRename("HATRED",MRCL.Color,BrickColor.random().Color,"Arcade")
			MAINRUINCOLOR = BrickColor.new("Black")
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.75
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0.25
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait(2)
		if rainbowmode == true or ModeOfGlitch == 6 then
			sphereMK(5, 0.15, "Add", root.CFrame * CFrame.new(math.random(-5, 5), -6, math.random(-5, 5)) * CFrame.Angles(math.rad(90), 0, 0), 1.5, 1.5, 10, -0.015, MAINRUINCOLOR, 0)
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch == 1000000 then
			sphereMK(5, 0.5, "Add", root.CFrame * CFrame.new(math.random(-25, 25), -10, math.random(-25, 25)) * CFrame.Angles(math.rad(90 + math.random(-15, 15)), math.rad(math.random(-15, 15)), 0), 1, 1, 15, -0.01, MAINRUINCOLOR, 0)
		slash2(math.random(50,100)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3.05,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(5,50)/250,BrickColor.new("White"))
		elseif ModeOfGlitch == 9797 then
			sphereMK(7.5,math.random(15,50)/45,"Add",root.CFrame*CFrame.new(math.random(-25,25),-10,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),0.75,0.75,10,-0.0075,MAINRUINCOLOR,0)
			slash(math.random(75,150)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(5,150)/250,MAINRUINCOLOR)
		elseif ModeOfGlitch == 8787 then
			slash(math.random(75,150)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(5,150)/250,MAINRUINCOLOR)
			slash(math.random(75,150)/10,5,true,"Round","Add","In",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(5,150)/250,MAINRUINCOLOR)
		elseif ModeOfGlitch == 778899 then
			waveEff(1,"Add","Out",root.CFrame*CFrame.new(0,-3.3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(5,0.001,5),0.01,0.015,MAINRUINCOLOR)
if ModeOfGlitch == 67966 then
sphereMK(10,math.random(10,25)/45,"Add",root.CFrame*CFrame.new(math.random(-20,20),-5,math.random(-20,20))*CFrame.Angles(math.rad(90 + math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(math.random(-5,5))),0.25,0.25,8,0,MAINRUINCOLOR,0)
end

if ModeOfGlitch == 688 then
waveEff(2,"Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0),vt(2,0.001,2),0.01,0.015,MAINRUINCOLOR)
end
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if ModeOfGlitch == 1 or ModeOfGlitch == 2 or ModeOfGlitch == 3 or ModeOfGlitch == 4 or ModeOfGlitch == 5 or ModeOfGlitch == 2334 or ModeOfGlitch == 8787 or ModeOfGlitch == 2 or ModeOfGlitch == 1000000 or ModeOfGlitch == 699 or ModeOfGlitch == 8787 or ModeOfGlitch == 9797 or ModeOfGlitch == 102341 or ModeOfGlitch == 8376532578634534 or ModeOfGlitch == 146536 or ModeOfGlitch == 666 or ModeOfGlitch == 778899 or ModeOfGlitch == 2339 or ModeOfGlitch == 1055 or ModeOfGlitch == 765688533321 or ModeOfGlitch == 912 or ModeOfGlitch == 9123 or ModeOfGlitch == 91234 or ModeOfGlitch == 912345 or ModeOfGlitch == 10101010 then
		end
	end
end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if rainbowmode == false or insanitymode == false or chaosmode == false then
for i, v in pairs(secondchar:GetChildren()) do
if v:IsA("Part") then
v.BrickColor = MAINRUINCOLOR
v.Material = "Neon"
end
end
		end
	end
end))
coroutine.resume(coroutine.create(function()
while true do
if ModeOfGlitch == 1000000 then
task.wait()
end
task.wait()
if ModeOfGlitch == 666 then
sphereMK(5,0.5,"Add",root.CFrame*CFrame.new(math.random(-25,25),-10,math.random(-25,25))*CFrame.Angles(math.rad(90 + math.random(-15,15)),math.rad(math.random(-15,15)),0),1,1,15,-0.01,MAINRUINCOLOR,0)
end
if ModeOfGlitch == 91234 then
task.wait()
blockMK(6,math.random(5,15)/45,"Add",root.CFrame*CFrame.new(math.random(-10,10),-5,math.random(-10,10))*CFrame.Angles(math.rad(90 + math.random(-3,3)),math.rad(math.random(-3,3)),math.rad(math.random(-3,3))),0.2,0.2,3,0,MAINRUINCOLOR,0)
end
if ModeOfGlitch == 666 then
sphereMK(5,math.random(1,2),"Add",root.CFrame*CFrame.new(math.random(-75,75),-25,math.random(-75,75))*CFrame.Angles(math.rad(90 + math.random(-25,25)),math.rad(math.random(-25,25)),0),1,1,50,-0.01,MAINRUINCOLOR,0)
end
end
end))
coroutine.resume(coroutine.create(function()
while true do
	task.wait(0)
	if ModeOfGlitch == 151353 then
		RecolorTextAndRename("Fighter", Color3.new(1,0,0), Color3.new(r / 255, g / 255, b / 255),"Fantasy")
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				end
			end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
while true do
	task.wait()
	if ModeOfGlitch == 2334 then
		RecolorTextAndRename("Thinking...", Color3.new(r / 255, g / 255, b / 255), Color3.new(r / 500, g / 500, b / 500),"Fantasy")
		MAINRUINCOLOR = BrickColor.new(r / 255, g / 255, b / 255)
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 1
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
while true do
	task.wait()
	if ModeOfGlitch == 9123851 then
		RecolorTextAndRename("Visualiser", Color3.new(r / 255, g / 255, b / 255), Color3.new(r / 500, g / 500, b / 500),"Fantasy")
		MAINRUINCOLOR = BrickColor.new(r / 255, g / 255, b / 255)
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
				end
			end
		end
	end
end))
coroutine.resume(coroutine.create(function()
while true do
	task.wait()
if glitching == true then
	RW.C0 = clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
	LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0 + 15 * math.cos(sine / 30)), math.rad(0), math.rad(-1 + 0 * math.cos(sine / 30))), 0.1)
	    Torso.Material = "Neon"
	    Head.Material = "Neon"
	    RightArm.Material = "Neon"
	    LeftArm.Material = "Neon"
	    LeftLeg.Material = "Neon"
	    RightLeg.Material = "Neon"
		elseif glitching == false then
	    Torso.Material = "SmoothPlastic"
	    Head.Material = "SmoothPlastic"
	    RightArm.Material = "SmoothPlastic"
	    LeftArm.Material = "SmoothPlastic"
	    LeftLeg.Material = "SmoothPlastic"
	    RightLeg.Material = "SmoothPlastic"
		end
end
	end))
coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
		if insanitymode == true then
			RecolorTextAndRename("INSANITY", Color3.new(0, 0, 0), BrickColor.random().Color,"Antique")
			MAINRUINCOLOR = BrickColor.random()
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
			end
		end
		for i, v in pairs(extrawingmod2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.BrickColor = BrickColor.random()
				v.Material = "Neon"
				end
			end
		end
	end
end))

coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
refec.Color = ColorSequence.new(MAINRUINCOLOR.Color,MAINRUINCOLOR.Color)
refec2.Color = ColorSequence.new(MAINRUINCOLOR.Color,MAINRUINCOLOR.Color)
refec3.Color = ColorSequence.new(MAINRUINCOLOR.Color,MAINRUINCOLOR.Color)
end
end))

coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
if equipped == false then
for i,v in pairs(Model0:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
elseif equipped == true then
for i,v in pairs(Model0:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
end
end
end))

coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
if ModeOfGlitch ~= 912345 and ModeOfGlitch ~= 929292 then
for i,v in pairs(colorizermod:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
for i,v in pairs(colorizermod2:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
for i,v in pairs(rotzo:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
for i,v in pairs(rotzo2:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
for i,v in pairs(m4:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 1
	end
end
---
elseif ModeOfGlitch == 912345 or ModeOfGlitch == 929292 then
for i,v in pairs(colorizermod:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
for i,v in pairs(colorizermod2:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
for i,v in pairs(rotzo:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
for i,v in pairs(rotzo2:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
for i,v in pairs(m4:GetChildren())do
	if v:IsA("Part")then
		v.Transparency = 0
	end
end
end
end
end))

coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
if ModeOfGlitch == 912345 and ModeOfGlitch ~= 929292 then
for i,v in pairs(colorizermod:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
for i,v in pairs(colorizermod2:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
for i,v in pairs(rotzo:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
for i,v in pairs(rotzo2:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
---
elseif ModeOfGlitch ~= 912345 or ModeOfGlitch == 929292 then
for i,v in pairs(colorizermod:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Dark blue")
	end
end
for i,v in pairs(colorizermod2:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Dark blue")
	end
end
for i,v in pairs(rotzo:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
for i,v in pairs(rotzo2:GetChildren())do
	if v:IsA("Part")then
		v.BrickColor = BrickColor.new("Alder")
	end
end
end
end
end))


coroutine.resume(coroutine.create(function()
	while true do
		task.wait()
	if rainbowmode == true then
		RecolorTextAndRename("RAINBOW", Color3.new(r / 255, g / 255, b / 255), Color3.new(r / 500, g / 500, b / 500),"Fantasy")
		MAINRUINCOLOR = BrickColor.new(r / 255, g / 255, b / 255)
		for i, v in pairs(m:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(m2:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(m3:GetChildren()) do
			if v:IsA("Part") then
				v.Color = Color3.new(r / 255, g / 255, b / 255)
			end
		end
		for i, v in pairs(mw1:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
			end
		end
		for i, v in pairs(secondchar:GetChildren()) do
			if v:IsA("Part") then
				v.BrickColor = MAINRUINCOLOR
				v.Material = "Neon"
			end
		end
		for i, v in pairs(mw2:GetChildren()) do
			if v:IsA("Part") then
				v.Transparency = 0
				v.Color = Color3.new(r / 255, g / 255, b / 255)
				v.Material = "Neon"
				end
			end
		end
	end
end))

Humanoid.Name = "THEGLITCHEREDIT"
Humanoid.MaxHealth = math.huge
Humanoid.Health = math.huge
Instance.new("ForceField", char).Visible = false

Humanoid.Animator.Parent = nil

idleanim=.4
while true do
if mutedtog == false then
kan.Volume = currentVol
elseif mutedtog == true then
kan.Volume = 0
end

	if(God)then
		hum.MaxHealth = 1e100
		hum.Health = 1e100
		if(not Character:FindFirstChildOfClass'ForceField')then IN("ForceField",Character).Visible = false end
		hum.Name = M.RNG()*100
	end

if chaosmode == false and glitching == false and insanitymode == false then
text.Position = UDim2.new(0,0,0,0)
text.Rotation = -5 * math.cos(sine / 32)
wobble.Rotation = 0 - 1 * math.cos(sine / 24)
wobble.BackgroundColor3 = text.TextColor3
wobble.BorderColor3 = text.TextStrokeColor3
wobble.BorderSizePixel = 2
wobble2.Rotation = 0 - 1 * math.cos(sine / 30)
wobble2.BackgroundColor3 = text.TextStrokeColor3
wobble2.BorderColor3 = text.TextColor3
wobble2.BorderSizePixel = 2
TextFrame.TextColor3 = text.TextColor3
TextFrame.TextStrokeColor3 = text.TextStrokeColor3
TextFrame.TextStrokeTransparency = 0
TextFrame.Rotation = 0 - 2 * math.cos(sine / 30)
TextFrame.Position = UDim2.new(0.48,0 - 10 * math.cos(sine / 50),0.867,0 - 10 * math.cos(sine / 50))
ModeFrame.Rotation = 6 - 2 * math.cos(sine / 35)
ModeFrame.TextColor3 = text.TextColor3
ModeFrame.TextStrokeColor3 = text.TextStrokeColor3
ModeFrame.TextStrokeTransparency = 0
ned.Rotation = 0 - 2 * math.cos(sine / 24)
ned.Position = UDim2.new(0.7,0 - 10 * math.cos(sine / 32),0.8,0 - 10 * math.cos(sine / 45))
elseif chaosmode == true then
TextFrame.TextColor3 = text.TextColor3
TextFrame.TextStrokeColor3 = text.TextStrokeColor3
TextFrame.TextStrokeTransparency = 0
TextFrame.Rotation = 0 + math.random(-3,3)
TextFrame.Position = UDim2.new(0.48,0 + math.random(-3,3),0.867,0 + math.random(-3,3)) -- backori
ModeFrame.Rotation = 6 + math.random(-2,2)
ModeFrame.TextColor3 = text.TextColor3
ModeFrame.TextStrokeColor3 = text.TextStrokeColor3
ModeFrame.TextStrokeTransparency = 0
wobble.Rotation = 0 - 2 * math.cos(sine / 24)
wobble2.Rotation = 0 - 2 * math.cos(sine / 30)
wobble2.BackgroundColor3 = text.TextStrokeColor3
wobble2.BorderColor3 = text.TextColor3
wobble2.BorderSizePixel = 2
wobble.BackgroundColor3 = text.TextColor3
wobble.BorderColor3 = text.TextStrokeColor3
wobble.BorderSizePixel = 2
ned.Rotation = 0 -2 * math.cos(sine / 1) + math.random(-3,3)
ned.Position = UDim2.new(0.7,0 + math.random(-3,3),0.8,0 + math.random(-3,3))
text.Position = UDim2.new(0,math.random(-1,1),0,math.random(-1,1))
text.Rotation = -2 * math.cos(sine / 1) + math.random(-3,3)
elseif insanitymode == true then
TextFrame.TextColor3 = text.TextColor3
TextFrame.TextStrokeColor3 = text.TextStrokeColor3
TextFrame.TextStrokeTransparency = 0
TextFrame.Rotation = 0 + math.random(-11,11)
TextFrame.Position = UDim2.new(0.48,0 + math.random(-9,9),0.867,0 + math.random(-9,9)) -- backori
ModeFrame.Rotation = 18 + math.random(-9,9)
ModeFrame.TextColor3 = text.TextColor3
ModeFrame.TextStrokeColor3 = text.TextStrokeColor3
ModeFrame.TextStrokeTransparency = 0
wobble.Rotation = 0 - 7.5 * math.cos(sine / 24)
wobble2.Rotation = 0 - 8 * math.cos(sine / 30)
wobble2.BackgroundColor3 = text.TextStrokeColor3
wobble2.BorderColor3 = text.TextColor3
wobble2.BorderSizePixel = 2
wobble.BackgroundColor3 = text.TextColor3
wobble.BorderColor3 = text.TextStrokeColor3
wobble.BorderSizePixel = 2
ned.Rotation = 0 -6 * math.cos(sine / 1) + math.random(-9,9)
ned.Position = UDim2.new(0.7,0 + math.random(-3,3),0.8,0 + math.random(-9,9))
text.Position = UDim2.new(0,math.random(-1,1),0,math.random(-4,4))
text.Rotation = -6 * math.cos(sine / 1) + math.random(-9,9)
elseif glitching == true then
TextFrame.TextColor3 = text.TextColor3
TextFrame.TextStrokeColor3 = text.TextStrokeColor3
TextFrame.TextStrokeTransparency = 0
TextFrame.Rotation = 0 + math.random(-4,4)
TextFrame.Position = UDim2.new(0.48,0 + math.random(-4,4),0.867,0 + math.random(-4,4)) -- backori
ModeFrame.Rotation = 6 + math.random(-4,4)
ModeFrame.TextColor3 = text.TextColor3
ModeFrame.TextStrokeColor3 = text.TextStrokeColor3
ModeFrame.TextStrokeTransparency = 0
wobble.Rotation = 0 - 4 * math.cos(sine / 24)
wobble2.Rotation = 0 - 4 * math.cos(sine / 30)
wobble2.BackgroundColor3 = text.TextStrokeColor3
wobble2.BorderColor3 = text.TextColor3
wobble2.BorderSizePixel = 2
wobble.BackgroundColor3 = text.TextColor3
wobble.BorderColor3 = text.TextStrokeColor3
wobble.BorderSizePixel = 2
ned.Rotation = 0 -4 * math.cos(sine / 1) + math.random(-4,4)
ned.Position = UDim2.new(0.7,0 + math.random(-3,3),0.8,0 + math.random(-4,4))
text.Position = UDim2.new(0,math.random(-2,2),0,math.random(-2,2))
text.Rotation = -4 * math.cos(sine / 1) + math.random(-4,4)
end
--
if ModeOfGlitch ~= 40044 then
rval = rval + 2
elseif ModeOfGlitch == 40044 then
rval = rval + 10
end
--wing welds
	task.wait()
	if ModeOfGlitch ~= 1 and ModeOfGlitch ~= 2 and ModeOfGlitch ~= 3 and ModeOfGlitch ~= 4 and ModeOfGlitch ~= 5 and ModeOfGlitch ~= 6 and ModeOfGlitch ~= 8787 and ModeOfGlitch ~= 9797 and ModeOfGlitch ~= 2 and ModeOfGlitch ~= 1000000 and ModeOfGlitch ~= 6127843 and ModeOfGlitch ~= 146536 and ModeOfGlitch ~= 102341 and ModeOfGlitch ~= 699 and ModeOfGlitch ~= 109124 and ModeOfGlitch ~= 778899 and ModeOfGlitch ~= 151353 and ModeOfGlitch ~= 353567 and ModeOfGlitch ~= 67966 and ModeOfGlitch ~= 688 and ModeOfGlitch ~= 47 and ModeOfGlitch ~= 808080 and ModeOfGlitch ~= 765688533321 and ModeOfGlitch ~= 676767 and ModeOfGlitch ~= 4004 and ModeOfGlitch ~= 90909 and ModeOfGlitch ~= 5005 and ModeOfGlitch ~= 6006 and ModeOfGlitch ~= 9 and ModeOfGlitch ~= 2002 and ModeOfGlitch ~= 10 and ModeOfGlitch ~= 912 and ModeOfGlitch ~= 91234567 and ModeOfGlitch ~= 929292 and ModeOfGlitch ~= 40044 then
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
	lwing1weld.C1 = clerp(lwing1weld.C1, cf(2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 32)), math.rad(0), math.rad(12.5 + 5 * math.cos(sine / 32))), 0.3)
	lwing2weld.C1 = clerp(lwing2weld.C1, cf(3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 32)), math.rad(0), math.rad(25 + 7.5 * math.cos(sine / 32))), 0.3)
	lwing3weld.C1 = clerp(lwing3weld.C1, cf(3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 32)), math.rad(0), math.rad(37.5 + 10 * math.cos(sine / 32))), 0.3)
	lwing4weld.C1 = clerp(lwing4weld.C1, cf(4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 32)), math.rad(0), math.rad(50 + 12.5 * math.cos(sine / 32))), 0.3)
	lwing5weld.C1 = clerp(lwing5weld.C1, cf(5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 32)), math.rad(0), math.rad(62.5 + 15 * math.cos(sine / 32))), 0.3)
	lwing6weld.C1 = clerp(lwing6weld.C1, cf(6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 32)), math.rad(0), math.rad(75 + 17.5 * math.cos(sine / 32))), 0.3)
	rwing1weld.C1 = clerp(rwing1weld.C1, cf(-2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 32)), math.rad(0), math.rad(-12.5 - 5 * math.cos(sine / 32))), 0.3)
	rwing2weld.C1 = clerp(rwing2weld.C1, cf(-3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 32)), math.rad(0), math.rad(-25 - 7.5 * math.cos(sine / 32))), 0.3)
	rwing3weld.C1 = clerp(rwing3weld.C1, cf(-3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 32)), math.rad(0), math.rad(-37.5 - 10 * math.cos(sine / 32))), 0.3)
	rwing4weld.C1 = clerp(rwing4weld.C1, cf(-4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 32)), math.rad(0), math.rad(-50 - 12.5 * math.cos(sine / 32))), 0.3)
	rwing5weld.C1 = clerp(rwing5weld.C1, cf(-5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 32)), math.rad(0), math.rad(-62.5 - 15 * math.cos(sine / 32))), 0.3)
	rwing6weld.C1 = clerp(rwing6weld.C1, cf(-6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 32)), math.rad(0), math.rad(-75 - 17.5 * math.cos(sine / 32))), 0.3)
elseif ModeOfGlitch == 151353 then
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(-0.5 + -2.5 * math.cos(sine / 25),0.5 + -0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(0 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(-0.5 + -2.5 * math.cos(sine / 25),0.5 + -0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(120 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(-0.5 + -2.5 * math.cos(sine / 25),0.5 + -0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-120 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0.5 + 2.5 * math.cos(sine / 25),-0.5 - 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + -1 * math.cos(sine / 50)),math.rad(0 + 2 * math.cos(sine / 36)),math.rad(0 - 3600 * math.cos(sine / 360))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0.5 + 2.5 * math.cos(sine / 25),-0.5 - 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + -1 * math.cos(sine / 70)),math.rad(0 + 2 * math.cos(sine / 37)),math.rad(120 - 3600 * math.cos(sine / 360))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0.5 + 2.5 * math.cos(sine / 25),-0.5 - 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + -1 * math.cos(sine / 60)),math.rad(0 + 2 * math.cos(sine / 51)),math.rad(-120 - 3600 * math.cos(sine / 360))),.3)
elseif ModeOfGlitch == 808080 then -- Celestial wing weld by wwwargos
handlexweld.C0=clerp(handleweld.C0,cf(0,9,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,9,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 + 4500 * math.cos(sine / 280))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 + 4500 * math.cos(sine / 280))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 + 4500 * math.cos(sine / 280))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 + 4500 * math.cos(sine / 280))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 + 4500 * math.cos(sine / 280))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 + 4500 * math.cos(sine / 280))),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 - 4500 * math.cos(sine / 280))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 - 4500 * math.cos(sine / 280))),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 - 4500 * math.cos(sine / 280))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 - 4500 * math.cos(sine / 280))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 - 4500 * math.cos(sine / 280))),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 0 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 - 4500 * math.cos(sine / 280))),.3)

elseif ModeOfGlitch == 8889 or ModeOfGlitch == 67966 or ModeOfGlitch == 688 or ModeOfGlitch == 664663666 or ModeOfGlitch == 88893333388 or ModeOfGlitch == 929292 then
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),0.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(0 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),0.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(120 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),0.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-120 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 1.5 * math.cos(sine / 360),-0.25 - 0.5 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(0 - 3600 * math.cos(sine / 720))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 1.5 * math.cos(sine / 360),-0.25 - 0.5 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(120 - 3600 * math.cos(sine / 720))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 1.5 * math.cos(sine / 360),-0.25 - 0.5 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-120 - 3600 * math.cos(sine / 720))),.3)
elseif ModeOfGlitch == 808080808080808080808080 or ModeOfGlitch == 765688533321 or ModeOfGlitch == 1264532489 or ModeOfGlitch == 6518594185 or ModeOfGlitch == 676767 then
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 + 3600 * math.cos(sine / 360))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 + 3600 * math.cos(sine / 360))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 + 3600 * math.cos(sine / 360))),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 - 3600 * math.cos(sine / 360))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 - 3600 * math.cos(sine / 360))),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 - 3600 * math.cos(sine / 360))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 - 3600 * math.cos(sine / 360))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 - 3600 * math.cos(sine / 360))),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 - 3600 * math.cos(sine / 360))),.3)

elseif ModeOfGlitch == 912 then
handleweld.C0=clerp(handleweld.C0,cf(0,-1.6,-1.6)*angles(math.rad(90),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 50)),math.rad(0 - 0.05 * math.cos(sine / 36)),math.rad(90 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 70)),math.rad(0 - 0.05 * math.cos(sine / 37)),math.rad(147.5 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 60)),math.rad(0 - 0.05 * math.cos(sine / 51)),math.rad(32.5 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 50)),math.rad(0 - 0.05 * math.cos(sine / 36)),math.rad(-90 + 3600 * math.cos(sine / 360))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 70)),math.rad(0 - 0.05 * math.cos(sine / 37)),math.rad(-147.5 + 3600 * math.cos(sine / 360))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.05 * math.cos(sine / 60)),math.rad(0 - 0.05 * math.cos(sine / 51)),math.rad(-32.5 + 3600 * math.cos(sine / 360))),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 50)),math.rad(0 - 0.05 * math.cos(sine / 36)),math.rad(90 - 3600 * math.cos(sine / 50))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 70)),math.rad(0 - 0.05 * math.cos(sine / 37)),math.rad(147.5 - 3600 * math.cos(sine / 70))),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 60)),math.rad(0 - 0.05 * math.cos(sine / 51)),math.rad(32.5 - 3600 * math.cos(sine / 60))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 50)),math.rad(0 - 0.05 * math.cos(sine / 36)),math.rad(-90 - 3600 * math.cos(sine / 50))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 70)),math.rad(0 - 0.05 * math.cos(sine / 37)),math.rad(-147.5 - 3600 * math.cos(sine / 70))),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.05 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.05 * math.cos(sine / 60)),math.rad(0 - 0.05 * math.cos(sine / 51)),math.rad(-32.5 - 3600 * math.cos(sine / 60))),.3)

elseif ModeOfGlitch == 91234567 then
handleweld.C0=clerp(handleweld.C0,cf(0,-2.5,-1.5)*angles(math.rad(80),math.rad(0),math.rad(0)),.3)
handlexweld.C0=clerp(handleweld.C0,cf(0,-4.5,-1.5)*angles(math.rad(80),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 + 1 * math.cos(sine / 1)),math.rad(0 - 1),1 + 1),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 2),1 + 2),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 3),1 + 3),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 4),1 + 4),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 5),1 + 5),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 6),1 + 6),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 - 3600 * math.cos(sine / 360))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 - 3600 * math.cos(sine / 360))),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 - 3600 * math.cos(sine / 360))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 - 3600 * math.cos(sine / 360))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 - 3600 * math.cos(sine / 360))),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 2 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 - 3600 * math.cos(sine / 360))),.3)

elseif ModeOfGlitch == 778899 then
handleweld.C0=clerp(handleweld.C0,cf(0,-1,-0.4)*angles(math.rad(32),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 50)),math.rad(0 - 0.75 * math.cos(sine / 36)),math.rad(90 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 70)),math.rad(0 - 0.75 * math.cos(sine / 37)),math.rad(147.5 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 60)),math.rad(0 - 0.75 * math.cos(sine / 51)),math.rad(32.5 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 50)),math.rad(0 - 0.75 * math.cos(sine / 36)),math.rad(-90 + 3600 * math.cos(sine / 360))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 70)),math.rad(0 - 0.75 * math.cos(sine / 37)),math.rad(-147.5 + 3600 * math.cos(sine / 360))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 0.75 * math.cos(sine / 60)),math.rad(0 - 0.75 * math.cos(sine / 51)),math.rad(-32.5 + 3600 * math.cos(sine / 360))),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 50)),math.rad(0 - 0.75 * math.cos(sine / 36)),math.rad(90 - 3600 * math.cos(sine / 50))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 70)),math.rad(0 - 0.75 * math.cos(sine / 37)),math.rad(147.5 - 3600 * math.cos(sine / 70))),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 60)),math.rad(0 - 0.75 * math.cos(sine / 51)),math.rad(32.5 - 3600 * math.cos(sine / 60))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 50)),math.rad(0 - 0.75 * math.cos(sine / 36)),math.rad(-90 - 3600 * math.cos(sine / 50))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 70)),math.rad(0 - 0.75 * math.cos(sine / 37)),math.rad(-147.5 - 3600 * math.cos(sine / 70))),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),-1)*angles(math.rad(0 + 0.75 * math.cos(sine / 60)),math.rad(0 - 0.75 * math.cos(sine / 51)),math.rad(-32.5 - 3600 * math.cos(sine / 60))),.3)
elseif ModeOfGlitch == 9797 then
lwing1weld.C1=clerp(lwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(90 + 3600 * math.cos(sine / 360))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(147.5 + 3600 * math.cos(sine / 360))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(32.5 + 3600 * math.cos(sine / 360))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 50)),math.rad(0 - 2 * math.cos(sine / 36)),math.rad(-90 + 3600 * math.cos(sine / 360))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 70)),math.rad(0 - 2 * math.cos(sine / 37)),math.rad(-147.5 + 3600 * math.cos(sine / 360))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0 + 2.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 25),0)*angles(math.rad(0 + 1 * math.cos(sine / 60)),math.rad(0 - 2 * math.cos(sine / 51)),math.rad(-32.5 + 3600 * math.cos(sine / 360))),.3)
elseif ModeOfGlitch == 1 or ModeOfGlitch == 2 or ModeOfGlitch == 3 or ModeOfGlitch == 4 or ModeOfGlitch == 5 or ModeOfGlitch == 6 or ModeOfGlitch == 8787 or ModeOfGlitch == 353567 or ModeOfGlitch == 1000000 or ModeOfGlitch == 6127843 or ModeOfGlitch == 699 then
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
	lwing1weld.C1 = clerp(lwing1weld.C1, cf(2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 32)), math.rad(0), math.rad(12.5 + 5 * math.cos(sine / 32))), 0.3)
	lwing2weld.C1 = clerp(lwing2weld.C1, cf(3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 32)), math.rad(0), math.rad(25 + 7.5 * math.cos(sine / 32))), 0.3)
	lwing3weld.C1 = clerp(lwing3weld.C1, cf(3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 32)), math.rad(0), math.rad(37.5 + 10 * math.cos(sine / 32))), 0.3)
	lwing4weld.C1 = clerp(lwing4weld.C1, cf(4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 32)), math.rad(0), math.rad(50 + 12.5 * math.cos(sine / 32))), 0.3)
	lwing5weld.C1 = clerp(lwing5weld.C1, cf(5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 32)), math.rad(0), math.rad(62.5 + 15 * math.cos(sine / 32))), 0.3)
	lwing6weld.C1 = clerp(lwing6weld.C1, cf(6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 32)), math.rad(0), math.rad(75 + 17.5 * math.cos(sine / 32))), 0.3)
	rwing1weld.C1 = clerp(rwing1weld.C1, cf(-2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 32)), math.rad(0), math.rad(-12.5 - 5 * math.cos(sine / 32))), 0.3)
	rwing2weld.C1 = clerp(rwing2weld.C1, cf(-3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 32)), math.rad(0), math.rad(-25 - 7.5 * math.cos(sine / 32))), 0.3)
	rwing3weld.C1 = clerp(rwing3weld.C1, cf(-3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 32)), math.rad(0), math.rad(-37.5 - 10 * math.cos(sine / 32))), 0.3)
	rwing4weld.C1 = clerp(rwing4weld.C1, cf(-4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 32)), math.rad(0), math.rad(-50 - 12.5 * math.cos(sine / 32))), 0.3)
	rwing5weld.C1 = clerp(rwing5weld.C1, cf(-5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 32)), math.rad(0), math.rad(-62.5 - 15 * math.cos(sine / 32))), 0.3)
	rwing6weld.C1 = clerp(rwing6weld.C1, cf(-6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 32)), math.rad(0), math.rad(-75 - 17.5 * math.cos(sine / 32))), 0.3)
elseif ModeOfGlitch == 47 then
lwing1weld.C1=clerp(lwing1weld.C1,cf(2,-1.5,0)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(5 + 10 * math.cos(sine / 32)),math.rad(0),math.rad(12.5 + 5 * math.cos(sine / 32))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(3.8,-2,-1.5)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(10 + 15 * math.cos(sine / 32)),math.rad(0),math.rad(25 + 7.5 * math.cos(sine / 32))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(6.5,-2.5,-2.5)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(15 + 20 * math.cos(sine / 32)),math.rad(0),math.rad(37.5 + 10 * math.cos(sine / 32))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(-2,-1.5,0)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(5 + 10 * math.cos(sine / 32)),math.rad(0),math.rad(-12.5 - 5 * math.cos(sine / 32))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(-3.8,-2,-1.5)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(10 + 15 * math.cos(sine / 32)),math.rad(0),math.rad(-25 - 7.5 * math.cos(sine / 32))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(-6.5,-2.5,-2.5)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(15 + 20 * math.cos(sine / 32)),math.rad(0),math.rad(-37.5 - 10 * math.cos(sine / 32))),.3)

elseif ModeOfGlitch == 102341 then
lwing1weld.C1=clerp(lwing1weld.C1,cf(2,0,-0.4)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(5 + 10 * math.cos(sine / 32)),math.rad(0),math.rad(12.5 + 5 * math.cos(sine / 32))),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(3,1,-0.4)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(10 + 15 * math.cos(sine / 32)),math.rad(0),math.rad(25 + 7.5 * math.cos(sine / 32))),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(3.75,2,-0.4)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(15 + 20 * math.cos(sine / 32)),math.rad(0),math.rad(37.5 + 10 * math.cos(sine / 32))),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(-2,0,-0.4)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(5 + 10 * math.cos(sine / 32)),math.rad(0),math.rad(-12.5 - 5 * math.cos(sine / 32))),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(-3,1,-0.4)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(10 + 15 * math.cos(sine / 32)),math.rad(0),math.rad(-25 - 7.5 * math.cos(sine / 32))),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(-3.75,2,-0.3)*angles(math.rad(0),math.rad(0),math.rad(0))*angles(math.rad(15 + 20 * math.cos(sine / 32)),math.rad(0),math.rad(-37.5 - 10 * math.cos(sine / 32))),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0,2 - 1.5 * math.cos(sine / 32.5),0)*angles(math.rad(0),math.rad(0),math.rad(360 + 720 * math.cos(sine / 65))),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0,0 - 1 * math.cos(sine / 32.5),-0.8)*angles(math.rad(0 + 5 * math.cos(sine / 32.5)),math.rad(0),math.rad(360)),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0,2 - 1.5 * math.cos(sine / 32.5),0)*angles(math.rad(0),math.rad(0),math.rad(180 + 720 * math.cos(sine / 65))),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0,2 - 1.5 * math.cos(sine / 32.5),0)*angles(math.rad(0),math.rad(0),math.rad(-90 + 720 * math.cos(sine / 65))),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0,-1 + 1 * math.cos(sine / 32.5),-0.9)*angles(math.rad(0 + 5 * math.cos(sine / 32.5)),math.rad(0),math.rad(180)),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0,2 - 1.5 * math.cos(sine / 32.5),-0.9)*angles(math.rad(0),math.rad(0),math.rad(90 + 720 * math.cos(sine / 65))),.3)
	elseif ModeOfGlitch == 109124 then
	lwing1weld.C1 = clerp(lwing1weld.C1, cf(2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 100)), math.rad(0), math.rad(12.5 + 5 * math.cos(sine / 100))), 0.3)
	lwing2weld.C1 = clerp(lwing2weld.C1, cf(3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 100)), math.rad(0), math.rad(25 + 7.5 * math.cos(sine / 100))), 0.3)
	lwing3weld.C1 = clerp(lwing3weld.C1, cf(3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 100)), math.rad(0), math.rad(37.5 + 10 * math.cos(sine / 100))), 0.3)
	lwing4weld.C1 = clerp(lwing4weld.C1, cf(4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 100)), math.rad(0), math.rad(50 + 12.5 * math.cos(sine / 100))), 0.3)
	lwing5weld.C1 = clerp(lwing5weld.C1, cf(5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 100)), math.rad(0), math.rad(62.5 + 15 * math.cos(sine / 100))), 0.3)
	lwing6weld.C1 = clerp(lwing6weld.C1, cf(6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 100)), math.rad(0), math.rad(75 + 17.5 * math.cos(sine / 100))), 0.3)
	rwing1weld.C1 = clerp(rwing1weld.C1, cf(-2, 0, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(5 + 10 * math.cos(sine / 100)), math.rad(0), math.rad(-12.5 - 5 * math.cos(sine / 100))), 0.3)
	rwing2weld.C1 = clerp(rwing2weld.C1, cf(-3, 1, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(10 + 15 * math.cos(sine / 100)), math.rad(0), math.rad(-25 - 7.5 * math.cos(sine / 100))), 0.3)
	rwing3weld.C1 = clerp(rwing3weld.C1, cf(-3.75, 2, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(15 + 20 * math.cos(sine / 100)), math.rad(0), math.rad(-37.5 - 10 * math.cos(sine / 100))), 0.3)
	rwing4weld.C1 = clerp(rwing4weld.C1, cf(-4.75, 3, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(20 + 25 * math.cos(sine / 100)), math.rad(0), math.rad(-50 - 12.5 * math.cos(sine / 100))), 0.3)
	rwing5weld.C1 = clerp(rwing5weld.C1, cf(-5.75, 4, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(25 + 30 * math.cos(sine / 100)), math.rad(0), math.rad(-62.5 - 15 * math.cos(sine / 100))), 0.3)
	rwing6weld.C1 = clerp(rwing6weld.C1, cf(-6.75, 5, 0) * angles(math.rad(0), math.rad(0), math.rad(0)) * angles(math.rad(30 + 35 * math.cos(sine / 100)), math.rad(0), math.rad(-75 - 17.5 * math.cos(sine / 100))), 0.3)
elseif ModeOfGlitch == 146536 then
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 + 1 * math.cos(sine / 1)),math.rad(0 - 1),1 + 1),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 2),1 + 2),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 3),1 + 3),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 4),1 + 4),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 5),1 + 5),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0,1.5 + 0.75 * math.cos(sine / 21),0)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 6),1 + 6),.3)
lwing4weld.C1=clerp(lwing4weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 27),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 7),1 + 7),.3)
lwing5weld.C1=clerp(lwing5weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 28),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 8),1 + 8),.3)
lwing6weld.C1=clerp(lwing6weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 29),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 9),1 + 9),.3)
rwing4weld.C1=clerp(rwing4weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 30),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 10),1 + 10),.3)
rwing5weld.C1=clerp(rwing5weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 31),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 11),1 + 11),.3)
rwing6weld.C1=clerp(rwing6weld.C1,cf(0 - 7.5 * math.cos(sine / 180),1.5 + 0.75 * math.cos(sine / 32),-1)*angles(math.rad(0 + 1 * math.cos(sine / 1)),math.rad(0 - 12),1 + 12),.3)
elseif ModeOfGlitch == 9 or ModeOfGlitch == 4004 or ModeOfGlitch == 90909 or ModeOfGlitch == 5005 or ModeOfGlitch == 6006 or ModeOfGlitch == 2002 or ModeOfGlitch == 10 or ModeOfGlitch == 40044 then
handlexweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
lwing1weld.C1=clerp(lwing1weld.C1,cf(0,1,0 + 0.2 * math.cos(sine / 20))*angles(math.rad(0 - 5 * math.cos(sine / 20)),math.rad(0),math.rad(90 + rval)),.3)
lwing2weld.C1=clerp(lwing2weld.C1,cf(0,1,0 + 0.2 * math.cos(sine / 20))*angles(math.rad(0 - 5 * math.cos(sine / 20)),math.rad(0),math.rad(-147.5 + rval)),.3)
lwing3weld.C1=clerp(lwing3weld.C1,cf(0,1,0 + 0.2 * math.cos(sine / 20))*angles(math.rad(0 - 5 * math.cos(sine / 20)),math.rad(0),math.rad(-32.5 + rval)),.3)
rwing1weld.C1=clerp(rwing1weld.C1,cf(0,1,0 - 0.2 * math.cos(sine / 20))*angles(math.rad(0 + 5 * math.cos(sine / 20)),math.rad(0),math.rad(-90 - rval)),.3)
rwing2weld.C1=clerp(rwing2weld.C1,cf(0,1,0 - 0.2 * math.cos(sine / 20))*angles(math.rad(0 + 5 * math.cos(sine / 20)),math.rad(0),math.rad(147.5 - rval)),.3)
rwing3weld.C1=clerp(rwing3weld.C1,cf(0,1,0 - 0.2 * math.cos(sine / 20))*angles(math.rad(0 + 5 * math.cos(sine / 20)),math.rad(0),math.rad(32.5 - rval)),.3)
end
if ModeOfGlitch == 912345 and attack == false and ModeOfGlitch ~= 929292 then
hum.CameraOffset = vt(0 +  0.05 * math.cos(sine / 32),0  -  0.05 * math.cos(sine / 46),0 -  0.05 * math.cos(sine / 57))
handlex2weld.C1=clerp(handlex2weld.C1,cf(0,-2,-2.05)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlex2weld.C0=clerp(handlex2weld.C0,cf(0 + 0.25 * math.cos(sine / 63),0 + 0.25 * math.cos(sine / 70),0 + 0.25 * math.cos(sine / 57))*angles(math.rad(0 + 5 * math.cos(sine / 55)),math.rad(0 + 5 * math.cos(sine / 46)),math.rad(0 + 5 * math.cos(sine / 32))),.3)
elseif ModeOfGlitch ~= 912345 and attack == false and ModeOfGlitch == 929292 then
hum.CameraOffset = vt(0 +  0.05 * math.cos(kan.PlaybackSpeed / 32),0  -  0.05 * math.cos(kan.PlaybackSpeed / 23),0 -  0.05 * math.cos(kan.PlaybackSpeed / 32))
handlex2weld.C1=clerp(handlex2weld.C1,cf(0,-2,-2.05)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
handlex2weld.C0=clerp(handlex2weld.C0,cf(0 + 0.25 * math.cos(kan.PlaybackSpeed / 13),0 + 0.25 * math.cos(kan.PlaybackSpeed / 23),0 + 0.25 * math.cos(sine / 32))*angles(math.rad(0 + 5 * math.cos(kan.PlaybackSpeed / 33)),math.rad(0 + 5 * math.cos(kan.PlaybackSpeed / 23)),math.rad(0 + 5 * math.cos(kan.PlaybackSpeed / 12))),.3)
end
if attack == false and ActiveGia == false then
torsweld.C1=clerp(torsweld.C1,cf(2,5*4,-8)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.25*8,0)*angles(math.rad(0),math.rad(0),math.rad(20)),1)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.25*8,0)*angles(math.rad(0),math.rad(0),math.rad(-20)),1)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,0)*angles(math.rad(-10),math.rad(0),math.rad(0)),1)
elseif attack == false and ActiveGia == true then
if ModeOfGlitch ~= 6 and ModeOfGlitch ~= 1000000 and ModeOfGlitch ~= 666 and ModeOfGlitch ~= 8376532578634534 then
torsweld.C1=clerp(torsweld.C1,cf(0,-2 + 0.25 * math.cos(sine / 32) ,-8)*angles(math.rad(0),math.rad(0),math.rad(0)),.025)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(20)),0.025)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(-20)),0.025)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0)*angles(math.rad(0),math.rad(0),math.rad(0)),0.025)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,-0.2)*angles(math.rad(10),math.rad(0),math.rad(0)),0.025)
elseif ModeOfGlitch == 6 or ModeOfGlitch == 1000000 or ModeOfGlitch == 666 then
torsweld.C1=clerp(torsweld.C1,cf(0,-25 + 0.5 * math.cos(sine / 32) ,-8)*angles(math.rad(20),math.rad(0),math.rad(0)),.025)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(20)),0.025)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(-20)),0.025)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,1.5*8,0.6*8)*angles(math.rad(20),math.rad(0),math.rad(0)),0.025)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0.11*8)*angles(math.rad(10),math.rad(0),math.rad(0)),0.025)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,-0.2)*angles(math.rad(5),math.rad(0),math.rad(0)),0.025)
elseif ModeOfGlitch == 8376532578634534 then
torsweld.C1=clerp(torsweld.C1,cf(0,-25 + 0.5 * math.cos(sine / 32) ,-8)*angles(math.rad(20),math.rad(0),math.rad(0)),.025)
larmsweld.C1=clerp(larmsweld.C1,cf(1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(20)),0.025)
rarmsweld.C1=clerp(rarmsweld.C1,cf(-1.65*8,0.45*8,0)*angles(math.rad(10),math.rad(0),math.rad(-20)),0.025)
llegsweld.C1=clerp(llegsweld.C1,cf(0.5*8,1.5*8,0.6*8)*angles(math.rad(20),math.rad(0),math.rad(0)),0.025)
rlegsweld.C1=clerp(rlegsweld.C1,cf(-0.5*8,2*8,0.11*8)*angles(math.rad(10),math.rad(0),math.rad(0)),0.025)
hedsweld.C1=clerp(hedsweld.C1,cf(0,-1.5*8,-0.2)*angles(math.rad(5),math.rad(0),math.rad(0)),0.025)
end
end
	sine = sine + change
	SINE = SINE + change
rotingweld.C0=clerp(rotingweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(actualrotationvalue + 750 * math.cos(sine / 1000))),.3)
rotingweld2.C0=clerp(rotingweld2.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(-actualrotationvalue - 750 * math.cos(sine / 1000))),.3)
	local torvel = (RootPart.Velocity * Vector3.new(1, 0, 1)).magnitude
	local velderp = RootPart.Velocity.y
	hitfloor, posfloor = rayCast(RootPart.Position, CFrame.new(RootPart.Position, RootPart.Position - Vector3.new(0, 1, 0)).lookVector, 4, Character)
coroutine.resume(coroutine.create(function()
if ModeOfGlitch == 146536 or ModeOfGlitch == 778899 then
	if hitfloor ~= nil then
	sphere2(3,"Add",root.CFrame*CFrame.new(0,-3,0),vt(6,0.55,6),0.025,-0.01,0.025,MAINRUINCOLOR)
	elseif ModeOfGlitch == 699 then
slash(math.random(75,150)/10,5,true,"Round","Add","Out",root.CFrame*CFrame.new(0,-3,0)*CFrame.Angles(math.rad(math.random(-5,5)),math.rad(math.random(-360,360)),math.rad(math.random(-5,5))),vt(0.01,0.01,0.01),math.random(5,350)/250,BrickColor.new("Really red"))	
end
elseif ModeOfGlitch == 99999123778356 or ModeOfGlitch == 01010101000001 then
	if hitfloor ~= nil then
		sphere2(1.5,"Add",root.CFrame*CFrame.new(0,-3,0),vt(1,0.5,1),0.1,0.01,0.1,BrickColor.new("Lime green"),Color3.new(0,1,0))
end
end
end))
	if equipped == true or equipped == false then
		if attack == false then
			idle = idle + 1
		else
			idle = 0
		end
		if not (idle >= 500) or attack == false then
		end
		if RootPart.Velocity.y > 1 and hitfloor == nil then
			Anim = "Jump"
			if attack == false then
				RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(-20)), 0.1)
				LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(20)), 0.1)
				RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.05 * math.cos(sine / 25)) * angles(math.rad(-10), math.rad(0), math.rad(0)), 0.1)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-2.5), math.rad(0), math.rad(0)), 0.1)
				RW.C0 = clerp(RW.C0, cf(1.45, 0.5 + 0.1 * math.cos(sine / 25), 0) * angles(math.rad(-5), math.rad(0), math.rad(25)), 0.1)
				LW.C0 = clerp(LW.C0, cf(-1.45, 0.5 + 0.1 * math.cos(sine / 25), 0) * angles(math.rad(-5), math.rad(0), math.rad(-25)), 0.1)
			end
		elseif RootPart.Velocity.y < -1 and hitfloor == nil then
			Anim = "Fall"
			if attack == false then
				RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(-20)), 0.1)
				LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 25), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-5), math.rad(0), math.rad(20)), 0.1)
				RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.05 * math.cos(sine / 25)) * angles(math.rad(0), math.rad(0), math.rad(0)), 0.1)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(0), math.rad(0), math.rad(0)), 0.1)
				RW.C0 = clerp(RW.C0, cf(1.45, 0.5 + 0.1 * math.cos(sine / 25), 0) * angles(math.rad(-20), math.rad(0), math.rad(50)), 0.1)
				LW.C0 = clerp(LW.C0, cf(-1.45, 0.5 + 0.1 * math.cos(sine / 25), 0) * angles(math.rad(-20), math.rad(0), math.rad(-50)), 0.1)
			end
		elseif torvel < 1 and hitfloor ~= nil then
			Anim = "Idle"
			if attack == false then -- idling animation
				if ModeOfGlitch == 1 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-5),math.rad(-20 - 2 * math.cos(sine / 56)),math.rad(10 - 3 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 - 2 * math.cos(sine / 56)),math.rad(-10 + 3 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.03 * math.cos(sine / 32),0 + 0.1 * math.cos(sine / 32))*angles(math.rad(10 - 3 * math.cos(sine / 32)),math.rad(0),math.rad(20 + 2 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(17 - 6 * math.cos(sine / 37)),math.rad(0 + 5 * math.cos(sine / 43) - 5 * math.cos(sine / 0.25)),math.rad(-20 - 2 * math.cos(sine / 56))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(5 + 3 * math.cos(sine / 43)),math.rad(-16 - 5 * math.cos(sine / 52)),math.rad(23 + 4 * math.cos(sine / 37))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(160),math.rad(0),math.rad(25)),.1)
				elseif ModeOfGlitch == 2 or ModeOfGlitch == 6127843 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-7.5),math.rad(0),math.rad(0 - 2 * math.cos(sine / 34))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 + 2 * math.cos(sine / 34))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 34),0 + 0.05 * math.cos(sine / 28))*angles(math.rad(0 - 2 * math.cos(sine / 34)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 2.5 * math.cos(sine / 28)),math.rad(0 - 4 * math.cos(sine / 42)),math.rad(0 - 3 * math.cos(sine / 76))),.1)
RW.C0=clerp(RW.C0,cf(0.85,0.5 + 0.1 * math.cos(sine / 28),-0.65)*angles(math.rad(30 - 3 * math.cos(sine / 39)),math.rad(0),math.rad(-100 - 4 * math.cos(sine / 47))),.1)
LW.C0=clerp(LW.C0,cf(-0.85,0.5 + 0.1 * math.cos(sine / 28),-0.65)*angles(math.rad(40 - 2 * math.cos(		sine / 41)),math.rad(0),math.rad(90 + 7 * math.cos(sine / 53))),.1)
				elseif ModeOfGlitch == 5 then
					RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0 - 1 * math.cos(sine / 34))), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0 + 1 * math.cos(sine / 34))), 0.1)
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.05 * math.cos(sine / 28)) * angles(math.rad(0 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(-20)), 0.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(25 - 2.5 * math.cos(sine / 28)), math.rad(0), math.rad(20)), 0.1)
					RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(10), math.rad(-20), math.rad(30 + 2.5 * math.cos(sine / 25))), 0.1)
					LW.C0 = clerp(LW.C0, cf(-1.5, 0.75, 0) * angles(math.rad(170), math.rad(-20), math.rad(20)), 0.1)
				elseif ModeOfGlitch == 4 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.025 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-1.5),math.rad(0),math.rad(20 - 3 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.025 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-1.5),math.rad(0),math.rad(-20 + 3 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.2 + 0.03 * math.cos(sine / 32),-0.025 + 0.025 * math.cos(sine / 32))*angles(math.rad(20 - 3 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 5 * math.cos(sine / 0.5265)),math.rad(0 - 5 * math.cos(sine / 0.25)),math.rad(0 - 3 * math.cos(sine / 62))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(10 + 5 * math.cos(sine / 42)),math.rad(0 + 3 * math.cos(sine / 34)),math.rad(5 + 1 * math.cos(sine / 68))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(10 + 2 * math.cos(sine / 38)),math.rad(0 + 4 * math.cos(sine / 47)),math.rad(-5 + 2 * math.cos(sine / 31))),.1)
				elseif ModeOfGlitch == 3 then
					RH.C0 = clerp(RH.C0, cf(1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0 + 1 * math.cos(sine / 34))), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -1 - 0.05 * math.cos(sine / 28), 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(0 + 1 * math.cos(sine / 34))), 0.1)
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, 0 + 0.05 * math.cos(sine / 28)) * angles(math.rad(0 - 1 * math.cos(sine / 34)), math.rad(0), math.rad(0)), 0.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(5 - 2.5 * math.cos(sine / 28)), math.rad(0), math.rad(0)), 0.1)
					RW.C0 = clerp(RW.C0, cf(1, 0.5 + 0.1 * math.cos(sine / 28), 0.45) * angles(math.rad(-30), math.rad(0), math.rad(-30)), 0.1)
					LW.C0 = clerp(LW.C0, cf(-1, 0.5 + 0.1 * math.cos(sine / 28), 0.45) * angles(math.rad(-30), math.rad(0), math.rad(30)), 0.1)
				elseif ModeOfGlitch == 1000000 then
RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 2 * math.cos(sine / 34)),math.rad(0),math.rad(0 - 3 * math.cos(sine /61))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 + 3 * math.cos(sine / 67)),math.rad(0 + 2 * math.cos(sine / 53)),math.rad(0 + 4 * math.cos(sine / 73))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(5 + 4 * math.cos(sine / 48)),math.rad(0),math.rad(15 + 5 * math.cos(sine / 33))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(6 + 3 * math.cos(sine / 52)),math.rad(0),math.rad(-15 - 4 * math.cos(sine / 34))),.1)
				elseif ModeOfGlitch == 6 then
					local snap = math.random(1,8)
					if snap == 1 then
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(32 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),1)
					end
RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-10)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(10)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,1.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 2 * math.cos(sine / 34)),math.rad(0),math.rad(0 - 3 * math.cos(sine /61))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 + 3 * math.cos(sine / 67)),math.rad(0 + 2 * math.cos(sine / 53)),math.rad(0 + 4 * math.cos(sine / 73))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(5 + 4 * math.cos(sine / 48)),math.rad(0),math.rad(15 + 5 * math.cos(sine / 33))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(6 + 3 * math.cos(sine / 52)),math.rad(0),math.rad(-15 - 4 * math.cos(sine / 34))),.1)
                 elseif ModeOfGlitch == 8787 then
					local snap = math.random(1,4)
					if snap == 1 then
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(22 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),1)
					end
					sphere2(8,"Add",rleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
					sphere2(8,"Add",lleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
					RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(20),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-14 - 5 * math.cos(sine / 48))),.1)
					LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(20),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 7 * math.cos(sine / 51))),.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 43),0 - 0.25 * math.cos(sine / 53),6 + 1 * math.cos(sine / 32))*angles(math.rad(20 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(21 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
					RW.C0=clerp(RW.C0,cf(1,0.5 + 0.025 * math.cos(sine / 45),-0.2)*angles(math.rad(130 + 6 * math.cos(sine / 72) + MRANDOM(-20,20)),math.rad(3 - 2 * math.cos(sine / 58) + MRANDOM(-20,20)),math.rad(-38 + 2 * math.cos(sine / 45) + MRANDOM(-20,20))),.1)
					LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.2)*angles(math.rad(130 - 7 * math.cos(sine / 66) + MRANDOM(-20,20)),math.rad(4 - 3 * math.cos(sine / 59) + MRANDOM(-20,20)),math.rad(33 - 4 * math.cos(sine / 45) + MRANDOM(-20,20))),.1)
				elseif ModeOfGlitch == 9797 then
					RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-14 - 5 * math.cos(sine / 48))),.1)
					LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 7 * math.cos(sine / 51))),.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.25 * math.cos(sine / 50),0 + 0.25 * math.cos(sine / 43),6 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
					RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/0.5),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
					LW.C0=clerp(LW.C0,cf(-1,0.5+.2*math.cos(sine/0.5),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)
				elseif ModeOfGlitch == 8376532578634534 then
local snap = math.random(1,10)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),1)
end
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,MAINRUINCOLOR,0)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-14 - 5 * math.cos(sine / 48))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 7 * math.cos(sine / 51))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,4 + 0.5 * math.cos(sine / 24))*angles(math.rad(10 - 0.5 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 1 * math.cos(sine / 0.5265)),math.rad(0 - 1 * math.cos(sine / 0.25)),math.rad(0 - 1 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.3,0.7,0)*angles(math.rad(0 + 1 * math.cos(sine / 0.568)),math.rad(15 - 5 * math.cos(sine / 24)),math.rad(-145 - 15 * math.cos(sine / 24))),.1)
				elseif ModeOfGlitch == 146536 then
					RH.C0=clerp(RH.C0,cf(1, -1 - 0.025 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
					LH.C0=clerp(LH.C0,cf(-1, -1 - 0.05 * math.cos(sine/12), -0.01)*angles(math.rad(0),math.rad(-83),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0, 0, 0 + 0.05 * math.cos(sine / 12))*angles(math.rad(0),math.rad(0),math.rad(0)),0.1)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*cf(0, 0, 0 + ((1) - 1))*angles(math.rad(15 - 2.5 * math.sin(sine / 12)),math.rad(0),math.rad(0)),0.1)
					RW.C0=clerp(RW.C0,cf(1,0.35 + 0.125 * math.cos(sine / 12),-0.45)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
					LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.125 * math.cos(sine / 12),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(67 - 4 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 2332 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-6),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-0.5),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(1 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 + 3 * math.cos(sine / 42))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 2 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 58)),math.rad(0 + 1 * math.cos(sine / 53))),.1)
LW.C0 = aclerp(LW.C0,CFrame.new(-0.787155986, 0.248306945, -0.683226228, 0.0398273654, -0.999169707, 0.00859495346, 0.554963291, 0.0149663882, -0.831740201, 0.830920994, 0.0378959104, 0.555098593)*angles(math.rad(0+5*math.cos(sine/32)),0,0),Alpha)
RW.C0 = aclerp(RW.C0,CFrame.new(0.787632346, 0.574486911, -0.794373989, 0.0789790228, 0.995851278, 0.0451963581, 0.631366551, -0.0148838377, -0.775341749, -0.771452367, 0.0897712111, -0.629922688)*angles(math.rad(0+5*math.cos(sine/32)),0,0),Alpha)
elseif ModeOfGlitch == 2334 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.15)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(-20), Rad(0), Rad(0)), 0.3)
RH.C0 = clerp(RH.C0, CF(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-2.5), Rad(0), Rad(0)), 0.15)
LH.C0 = clerp(LH.C0, CF(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-2.5), Rad(0), Rad(0)), 0.15)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-0.95,0.65 + 0.075 * math.cos(sine / 28),-0.65)*angles(math.rad(90 + 2 * math.cos(sine / 73)),math.rad(25 + 5 * math.cos(sine / 24)),math.rad(73 - 3 * math.cos(sine / 65))),.1)
elseif ModeOfGlitch == 102341 then -- THEORETICAL --
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("New Yeller"),BrickColor.new("New Yeller").Color)
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Cyan"),BrickColor.new("Cyan").Color)
sphereMK(2,-0.5,"Add",root.CFrame*CFrame.new(math.random(-5,5),math.random(-10,5),8)*CFrame.Angles(math.rad(90),math.rad(0),math.rad(0)),0.5,0.5,20,-0.0075,MAINRUINCOLOR,0)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.65)*angles(math.rad(-15),math.rad(84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,-0.2)*angles(math.rad(-10),math.rad(-84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.15 * math.cos(sine / 32))*angles(math.rad(-5 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(20 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(-24.5 - 4 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 699 then
sphere2(8,"Add",LeftArm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Really black"),BrickColor.new("Really red").Color)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),1 + 0.15 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(10)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 2 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 58)),math.rad(-10 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0, cf(-1.1, 0.4 + 0.05 * math.cos(sine / 30), 0.025 * math.cos(sine / 20)) * angles(math.rad(-30), math.rad(0), math.rad(30)), 0.1)
elseif ModeOfGlitch == 109124 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(5), Rad(0), Rad(0)), 0.15)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(20), Rad(-10 - 2.5 * Sin(sine/ 20)), Rad(20 * Cos(sine / 20))), 0.3)
RH.C0 = clerp(RH.C0, cf(1, -0.9 - 0.1 * Cos(sine / 20), -.2 + 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-3.5), Rad(0), Rad(5)), 0.15)
LH.C0 = clerp(LH.C0, cf(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-7), Rad(0), Rad(-5)), 0.15)
RW.C0 = clerp(RW.C0, cf(1.4, 0.5 + 0.10 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(10 + 5 * Sin(sine/ 20))), 0.1)
LW.C0 = clerp(LW.C0, cf(-1.4, 0.5 + 0.10 * Sin(sine / 20), 0.025 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(-10 - 5 * Sin(sine/ 20))), 0.1)	
elseif ModeOfGlitch == 666 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-10 - 2.5 * math.cos(sine / 32)),math.rad(-20),math.rad(0)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(-10 + 2.5 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0 + 0.1 * math.cos(sine / 32))*angles(math.rad(10 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(20)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(55),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
					elseif ModeOfGlitch == 998877 then
						local dankmeme = math.random(1,15)
				RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(4), Rad(0), Rad(0)), 0.15)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(20), Rad(0), Rad(0)), 0.3)
				if dankmeme == 1 then
				sphere2(8,"Add",Head.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("White"),BrickColor.new("Really black").Color)
				 PixelBlock(2,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
				RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(90)), 0.1)
       			LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-0), math.rad(0), math.rad(-90)), 0.3)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * cf(0, 0, 0 + ((1) - 1)) * angles(Rad(Mrandom(-15,15)), Rad(Mrandom(-15,15)), Rad(Mrandom(-15,15))), 1)
				elseif dankmeme == 15 then
				RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
				LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0 + 15 * math.cos(sine / 30)), math.rad(0), math.rad(-1 + 0 * math.cos(sine / 30))), 0.1)
				PixelBlock(2,math.random(1,20),"Add",root.CFrame*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),2,2,2,0.04,MAINRUINCOLOR,0)
				sphere2(8,"Add",RightArm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
				sphere2(8,"Add",LeftArm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR2,MAINRUINCOLOR2.Color)
				end
				RH.C0 = clerp(RH.C0, cf(1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * RHCF * angles(Rad(-1.5), Rad(0), Rad(10)), 0.15)
				LH.C0 = clerp(LH.C0, cf(-1, -0.9 - 0.1 * Cos(sine / 20), 0.025 * Cos(sine / 20)) * LHCF * angles(Rad(-1.5), Rad(0), Rad(10)), 0.15)
				RW.C0 = clerp(RW.C0, cf(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(15 - 4 * Cos(sine / 20)), Rad(0), Rad(5)), 0.1)
				LW.C0 = clerp(LW.C0, cf(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(15 - 4 * Cos(sine / 20)), Rad(0), Rad(-5)), 0.1)
					elseif ModeOfGlitch == 9123851 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, -0.1 + 0.1 * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.15)
LH.C0 = aclerp(LH.C0,CFrame.new(-0.50538516, -1.00439715+.2*M.C(sine/16)*math.cos(kan.PlaybackLoudness/60), -0.54824096, 0.999878109, -9.59694546e-11, 0.015612145, -9.81408521e-05, 0.999980211, 0.00628542574, -0.0156118376, -0.00628619269, 0.999858439),Alpha)
RH.C0 = aclerp(RH.C0,CFrame.new(0.498537898, -0.990978718*math.cos(kan.PlaybackLoudness/60), 0.0154631268, 0.999878109, -9.59694546e-11, 0.015612145, -9.81408521e-05, 0.999980211, 0.00628542574, -0.0156118376, -0.00628619269, 0.999858439),Alpha)
LW.C0 = aclerp(LW.C0,CFrame.new(-1.42332602, 0.626581013*math.cos(kan.PlaybackLoudness/60), -0.328449368, 0.922103286, 0.304182172, -0.239162698, -0.178854272, -0.213036552, -0.960534513, -0.343127936, 0.92848742, -0.142037436)*cF.A(-M.R(kan.PlaybackLoudness/60),0,0),Alpha)
RW.C0 = aclerp(RW.C0,CFrame.new(1.0793153, 0.434256732*math.cos(kan.PlaybackLoudness/60), 0.60275507, 0.650267124, 0.696277916, -0.303891033, -0.505378187, 0.695125222, 0.511267006, 0.567226231, -0.178880244, 0.803900838),Alpha)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 + 2 * math.cos(sine / 28) * kan.PlaybackLoudness/60),math.rad(0 + 2 * math.cos(sine / 73)),math.rad(-30)),.1)
				elseif ModeOfGlitch == 778899 then
		RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, 0 + 0.05 * math.cos(sine / 12)) * angles(math.rad(-60 + 2.5 * math.sin(sine / 12)), math.rad(0), math.rad(5 + 1 * math.sin(sine / 12))), .1)
		Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0) * angles(math.rad(0 + 4.5 * math.sin(sine / 12)), math.rad(0), math.rad(-5 - 2.5 * math.sin(sine / 12))), .1)
		RW.C0 = clerp(RW.C0, CF(1.15, 0.50 + 0.05 * math.cos(sine / 12), 0.4) * angles(math.rad(-160), math.rad(0 - 2.5 * math.sin(sine / 12)), math.rad(-45 + 7.5 * math.sin(sine / 12))), .1)
		LW.C0 = clerp(LW.C0, CF(-1.15, 0.50 + 0.05 * math.cos(sine / 12), 0.4) * angles(math.rad(-160), math.rad(0 + 2.5 * math.sin(sine / 12)), math.rad(45 - 7.5 * math.sin(sine / 12))), .1)
		RH.C0 = clerp(RH.C0, CF(1, -1 - 0.15 * math.cos(sine / 12), -0.05) * angles(math.rad(35 - 7.5 * math.sin(sine / 12)), math.rad(75), math.rad(0)) * angles(math.rad(-8 - 2.5 * math.sin(sine / 12)), math.rad(0), math.rad(0)), .1)
		LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.15 * math.cos(sine / 12), -0.05) * angles(math.rad(35 - 7.5 * math.sin(sine / 12)), math.rad(-90), math.rad(0)) * angles(math.rad(-8 - 2.5 * math.sin(sine / 12)), math.rad(0), math.rad(0)), .1)
				elseif ModeOfGlitch == 1055 then
			RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0 - 0.04 * math.sin(sine / 24), 0 + 0.04 * math.sin(sine / 20), 0 + 0.05 * math.cos(sine / 20)) * angles(math.rad(0 - 2.5 * math.sin(sine / 20)), math.rad(0 - 2.5 * math.sin(sine / 24)), math.rad(0)), 0.1)
			Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1.1) - 1)) * angles(math.rad(25 - 4 * math.sin(sine / 20)), math.rad(0), math.rad(0)), 0.1)
			RW.C0 = clerp(RW.C0, CF(1.25, 0.5, 0.5) * angles(math.rad(-35), math.rad(-25 + 2.5 * math.sin(sine / 20)), math.rad(-55 + 2.5 * math.sin(sine / 20))), 0.1)
			LW.C0 = clerp(LW.C0, CF(-1.25, 0.5, 0.5) * angles(math.rad(-35), math.rad(25 - 2.5 * math.sin(sine / 20)), math.rad(55 - 2.5 * math.sin(sine / 20))), 0.1)
			RH.C0 = clerp(RH.C0, CF(1, -1 + 0.06 * math.sin(sine / 24) - 0.05 * math.cos(sine / 20), -0.01) * angles(math.rad(0 - 2.5 * math.sin(sine / 20)), math.rad(75), math.rad(0)) * angles(math.rad(-2 - 2.5 * math.sin(sine / 24)), math.rad(0), math.rad(0)), 0.1)
			LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.06 * math.sin(sine / 24) - 0.05 * math.cos(sine / 20), -0.01) * angles(math.rad(0 - 2.5 * math.sin(sine / 20)), math.rad(-75), math.rad(0)) * angles(math.rad(-2 + 2.5 * math.sin(sine / 24)), math.rad(0), math.rad(0)), 0.1)
				elseif ModeOfGlitch == 2339 then
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(0),math.rad(0),math.rad(0)),.1)
RW.C0=clerp(RW.C0,cf(1.35,1,0)*angles(math.rad(0),math.rad(0),math.rad(90)),.1)
LW.C0=clerp(LW.C0,cf(-1.35,1,0)*angles(math.rad(0),math.rad(0),math.rad(-90)),.1)
elseif ModeOfGlitch == 111111112 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 2 + 0.25* Player_Size * Cos(sine / 12)) * angles(Rad(25), Rad(0), Rad(0)), 0.1)
tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15 - 6.5 * Sin(sine / 12)), Rad(0), Rad(0)), 0.05)
RH.C0 = clerp(RH.C0, CF(1* Player_Size, -1 - 0.15 * Cos(sine / 20)* Player_Size, -0.1* Player_Size) * angles(Rad(0), Rad(76), Rad(0)) * angles(Rad(-8.5 - 6.5 * Sin(sine / 12)), Rad(0), Rad(15)), 0.1)
LH.C0 = clerp(LH.C0, CF(-1.1* Player_Size, -0.6 - 0.15 * Cos(sine / 20)* Player_Size, -0.3* Player_Size) * angles(Rad(0), Rad(-76), Rad(0)) * angles(Rad(-8.5 - 6.5 * Sin(sine / 12)), Rad(15), Rad(25)), 0.1)
RW.C0 = clerp(RW.C0, CF(1.4* Player_Size, 0.4 + 0.08 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(25 - 6.5 * Cos(sine / 12)), Rad(-.6), Rad(13 + 6.5 * Sin(sine / 12))), 0.1)
LW.C0 = clerp(LW.C0, CF(-1.4* Player_Size, 0.4 + 0.08 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(25 - 6.5 * Cos(sine / 12)), Rad(-.6), Rad(-13 - 6.5 * Sin(sine / 12))), 0.1)
			elseif ModeOfGlitch == 151353 then
			    hum.CameraOffset = hum.CameraOffset:lerp(Vector3.new(0,0,0),0.15)
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),-0.01,0.05,-0.01,BrickColor.new(r / 255, g / 255, b / 255),BrickColor.new(r / 255, g / 255, b / 255).Color)
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(0.5,0.5,0.5),-0.01,0.05,-0.01,BrickColor.new("Crimson"),BrickColor.new("Crimson").Color)
				RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, -0.1 + 0.1* Player_Size * Cos(sine / 12)) * angles(Rad(0), Rad(0), Rad(20)), 0.1)
				tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-6.5 * Sin(sine / 12)), Rad(0), Rad(-20)), 0.1)
				RH.C0 = clerp(RH.C0, CF(1* Player_Size, -0.9 - 0.1 * Cos(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(75), Rad(0)) * angles(Rad(-12.5), Rad(0), Rad(0)), 0.1)
				LH.C0 = clerp(LH.C0, CF(-1* Player_Size, -0.9 - 0.1 * Cos(sine / 12)* Player_Size, -0.2* Player_Size) * angles(Rad(0), Rad(-65), Rad(0)) * angles(Rad(-6.5), Rad(0), Rad(6)), 0.1)
				RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.2 + 0.05 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(110), Rad(6 + 6.5 * Sin(sine / 12)), Rad(25)), 0.1)
				LW.C0 = clerp(LW.C0, CF(-1.3* Player_Size, 0.2 + 0.05 * Sin(sine / 12)* Player_Size, -0.5* Player_Size) * angles(Rad(110), Rad(6 - 6.5 * Sin(sine / 12)), Rad(25)), 0.1)
			elseif ModeOfGlitch == 353567 then
RW.C0 = clerp(RW.C0, CF(1.5, .5, 0) * angles(math.rad(45), math.rad(-3), math.rad(-10)), 0.1)
LW.C0 = clerp(LW.C0, CF(-1.5, 0.5, 0) * angles(math.rad(45), math.rad(5), math.rad(20)), 0.1)
LH.C0 = clerp(LH.C0, CF(-0.3, -1.5, 0) * angles(math.rad(100), math.rad(0), math.rad(-10)), 0.1)
RH.C0 = clerp(RH.C0, CF(0.3, -1.5, 0) * angles(math.rad(100), math.rad(0), math.rad(10)), 0.1)
RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -1.6) * angles(math.rad(10 - 1.8 * math.cos(sine / 32)), math.rad(0), math.rad(20)), 0.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(30 - 5 * math.cos(sine / 0.5265)), math.rad(0 - 5 * math.cos(sine / 0.25)), math.rad(0 - 5 * math.cos(sine / 0.465))), 0.1)
elseif ModeOfGlitch == 67966 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(3),math.rad(0 + 3 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(6),math.rad(0 + 3 * math.cos(sine / 56)),math.rad(3 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.02 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(2 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 6 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-3 - 5 * math.cos(sine / 37)),math.rad(0 + 14 * math.cos(sine / 58)),math.rad(0 + 3 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.5 + 0.025 * math.cos(sine / 45),-0.45)*angles(math.rad(33 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(-33 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.45)*angles(math.rad(23 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(33 - 3 * math.cos(sine / 45))),.1)
				elseif ModeOfGlitch == 688 then
		RootJoint.C0 = clerp(RootJoint.C0,RootCF * CF(0, 0, 1.5 - 0.15 * COS(SINE / 24)) * ANGLES(RAD(0), RAD(5 - 25 * SIN(SINE / 15)), RAD(-45)), 0.1)
		Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15), RAD(0 - 25 * SIN(SINE / 25)), RAD(0 - 25 * SIN(SINE / 25))), .1)
		RW.C0 = clerp(RW.C0, CF(1.5, 0.5, 0) * ANGLES(RAD(15), RAD(15), RAD(0 - 25 * SIN(SINE / 15))), .1)
		LW.C0 = clerp(LW.C0, CF(-1.15, 0.5, 0.5) * ANGLES(RAD(-170), RAD(5 - 25 * SIN(SINE / 15)), RAD(35)), .1)
			RH.C0 = clerp(RH.C0, CF(1, -1, 0) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0 - 25 * SIN(SINE / 15))), 0.1)
			LH.C0 = clerp(LH.C0, CF(-1, -1, 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0 - 25 * SIN(SINE / 15)), RAD(0 - 25 * SIN(SINE / 15))), 0.1)

elseif ModeOfGlitch == 47 then
local snap = math.random(1,32)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),1)
end
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 7 * math.cos(sine / 56))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 52))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 43),0 - 0.25 * math.cos(sine / 53),6 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(21 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(67 - 4 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 808080 then
local snap = math.random(1,8)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(32 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),1)
end
sphere2(8,"Add",rleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Navy blue"),BrickColor.new("Navy blue").Color)
sphere2(8,"Add",lleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Alder"),BrickColor.new("Alder").Color)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3 + MRANDOM(-3,3)),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 6 * math.cos(sine / 39) + MRANDOM(-5,5))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3 + MRANDOM(-3,3)),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 45) + MRANDOM(-5,5))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.25 * math.cos(sine / 47),0 - 0.25 * math.cos(sine / 40),7 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(17)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(29 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(-17 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72) + MRANDOM(-10,10)),math.rad(3 - 2 * math.cos(sine / 58) + MRANDOM(-20,20)),math.rad(-82 + 2 * math.cos(sine / 45) + MRANDOM(-20,20))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(99 - 7 * math.cos(sine / 66) + MRANDOM(-20,20)),math.rad(4 - 3 * math.cos(sine / 59) + MRANDOM(-20,20)),math.rad(67 - 4 * math.cos(sine / 45) + MRANDOM(-20,20))),.1)
elseif ModeOfGlitch == 99999123778356 then
local snap = math.random(1,32)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(19 + math.random(-3,3)),math.rad(math.random(-3,3)),math.rad(-53 + math.random(-3,3))),1)
end
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,MAINRUINCOLOR,0)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-20),math.rad(0 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(9),math.rad(8 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),-0.1 + 0.05 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(43)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(19 - 2 * math.cos(sine / 37)),math.rad(0 + 5 * math.cos(sine / 55)),math.rad(-43)),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(2 + 11 * math.cos(sine / 73)),math.rad(18 - 6 * math.cos(sine / 57)),math.rad(17 + 5 * math.cos(sine / 52))),.1)
LW.C0=clerp(LW.C0,cf(-1.2,0.85 + 0.025 * math.cos(sine / 45),-0.65)*angles(math.rad(170 - 1 * math.cos(sine / 70)),math.rad(-3 - 1 * math.cos(sine / 59)),math.rad(47 - 1 * math.cos(sine / 60))),.1)
elseif ModeOfGlitch == 01010101000001 then
local snap = math.random(1,5)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(23 + math.random(-5,5)),math.rad(math.random(-5,5)),math.rad(22 + math.random(-5,5))),1)
end
PixelBlockX(3,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,MAINRUINCOLOR,0)
PixelBlockX(3,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new("Forest green"),0)

RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5 - 2 * math.cos(sine / 56)),math.rad(-12 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-6),math.rad(22 - 2 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.01 + 0.03 * math.cos(sine / 32),0 + 0.1 * math.cos(sine / 32))*angles(math.rad(1 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(-22 + 2 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(23 - 2 * math.cos(sine / 37)),math.rad(0 + 5 * math.cos(sine / 43) - 5 * math.cos(sine / 0.25)),math.rad(22 - 2 * math.cos(sine / 56))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*CFrame.Angles(-10,-0.3,-80),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*CFrame.Angles(0,0,-3),.1)
elseif ModeOfGlitch == 01010101000001 then
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.75,0.75,0.75,0.0075,BrickColor.new("Forest green"),0)
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.75,0.75,0.75,0.0075,BrickColor.new("Lime green"),0)
RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0* Player_Size, 0* Player_Size, -0.1) * angles(Rad(0), Rad(0), Rad(0)), 0.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,Torso.Neck.C0 * CFrame.Angles(Rad(math.random(-3,3)), Rad(math.random(-3,3)), Rad(math.random(-3,3))) , 0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko* cf(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(20 - 5 * Sin(sine / 20)), Rad(0), Rad(3 - 3 * Cos(sine / 16))), 0.1)
RW.C0 = clerp(RW.C0, cf(1.5 * Player_Size, 0.5 + 0.05 * Cos(sine / 20) * Player_Size, 0) * angles(Rad(130), Rad(0 + 2 * Sin(sine/16)), Rad(-40)), 0.1)
RW.C0 = clerp(RW.C0,RW.C0 * CFrame.Angles(Rad(math.random(-3,3)), Rad(math.random(-3,3)), Rad(math.random(-3,3))) , 0.5)
LW.C0 = clerp(LW.C0, cf(-1.5 * Player_Size, 0.5 + 0.05 * Cos(sine / 20) * Player_Size, 0) * angles(Rad(20), Rad(0 - 2* Sin(sine/16)), Rad(0)), 0.1)
LW.C0 = clerp(LW.C0,LW.C0 * CFrame.Angles(Rad(math.random(-3,3)), Rad(math.random(-3,3)), Rad(math.random(-3,3))) , 0.5)
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-6),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-0.5),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
elseif ModeOfGlitch == 765688533321 then
local snap = math.random(1,32)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),1)
end
sphere2(8,"Add",rleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Really red"),BrickColor.new("Really red").Color)
sphere2(8,"Add",lleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Really black"),BrickColor.new("Really black").Color)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.25 * math.cos(sine / 50),0 + 0.25 * math.cos(sine / 43),6 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(2 - 4 * math.cos(sine / 58)),math.rad(-65 + 1 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 66)),math.rad(6 - 5 * math.cos(sine / 59)),math.rad(73 - 3 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 90909 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.02 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(2 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 44))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(22 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.5 + 0.025 * math.cos(sine / 45),0.45)*angles(math.rad(-33 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(-33 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),0.45)*angles(math.rad(-23 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(33 - 3 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 2002 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.1 * math.cos(sine / 12),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-6),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.1 * math.cos(sine / 12),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-0.5),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.08 * math.sin(sine / 22),0 + 0.15 * math.cos(sine / 12))*angles(math.rad(0 - 2 * math.cos(sine / 12)),math.rad(0),math.rad(-25)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 2 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 58)),math.rad(15 + 1 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.45 + 0.125 * math.sin(sine / 13),-0.5)*angles(math.rad(62),math.rad(3),math.rad(-82)),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),0.45)*angles(math.rad(-23 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(33 - 3 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 3003 then
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 7 * math.cos(sine / 56))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 52))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.45 * math.cos(sine / 18))*angles(math.rad(0 - 2 * math.cos(sine / 18)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.125 * math.cos(sine / 18),0)*angles(math.rad(2 + 5 * math.cos(sine / 74)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(14 + 5 * math.sin(sine / 18))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.125 * math.cos(sine / 18),0)*angles(math.rad(5 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(-14 - 6 * math.sin(sine / 18))),.1)
elseif ModeOfGlitch == 7007 then
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 7 * math.cos(sine / 56))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 52))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.45 * math.cos(sine / 18))*angles(math.rad(0 - 2 * math.cos(sine / 18)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.125 * math.cos(sine / 18),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 32)),math.rad(3 - 2 * math.cos(sine / 18)),math.rad(-82 + 2 * math.cos(sine / 25))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.125 * math.cos(sine / 18),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 26)),math.rad(4 - 3 * math.cos(sine / 19)),math.rad(67 - 4 * math.cos(sine / 25))),.1)
elseif ModeOfGlitch == 6006 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 15),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-6),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 15),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-0.5),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.02 * math.cos(sine / 15),0 + 0.05 * math.cos(sine / 15))*angles(math.rad(1 - 2 * math.cos(sine / 15)),math.rad(0),math.rad(0 + 1 * math.cos(sine / 22))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(35 - 2 * math.cos(sine / 15)),math.rad(0 + 2 * math.cos(sine / 28)),math.rad(0 + 1 * math.cos(sine / 23))),.1)
RW.C0=clerp(RW.C0,cf(1.43,0.45 + 0.135 * math.cos(sine / 15),0)*angles(math.rad(12 + 6 * math.cos(sine / 22)),math.rad(3 - 2 * math.cos(sine / 28)),math.rad(18 + 6 * math.sin(sine / 15))),.1)
LW.C0=clerp(LW.C0,cf(-1.43,0.6 + 0.135 * math.cos(sine / 15),0)*angles(math.rad(9 - 7 * math.cos(sine / 16)),math.rad(4 - 3 * math.cos(sine / 29)),math.rad(-18 - 6 * math.sin(sine / 15))),.1)
elseif ModeOfGlitch == 5005 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-6),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-0.5),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.01 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(1 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 + 3 * math.cos(sine / 42))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 2 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 58)),math.rad(0 + 1 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(89 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(67 - 4 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 8 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, 2.25 + 0.75 * math.cos(sine / 32)) * angles(math.rad(0), math.rad(0), math.rad(0)), 0.15)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-2.5 * math.sin(sine / 32)), math.rad(0), math.rad(0)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 7 * math.cos(sine / 56))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 52))),.1)
RW.C0 = clerp(RW.C0, CFrame.new(1.1, 0.4 + 0.05 * math.sin(sine / 30),0.3 + 0.025 * math.cos(sine / 32)) * angles(math.rad(-30), math.rad(-0), math.rad(-30)), 0.1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.1, 0.4 + 0.05 * math.cos(sine / 30),0.3 + 0.025 * math.cos(sine / 32)) * angles(math.rad(-30), math.rad(0), math.rad(30)), 0.1)
elseif ModeOfGlitch == 9 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.15 * math.cos(sine / 22),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(-5.5 - 2 * math.cos(sine / 56)),math.rad(-12 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.15 * math.cos(sine / 22),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-6),math.rad(22 - 2 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.01 + 0.03 * math.cos(sine / 22),0 + 0.15 * math.cos(sine / 22))*angles(math.rad(1 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(22 + 2 * math.cos(sine / 56))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 - 2 * math.cos(sine / 37)),math.rad(0 + 5 * math.cos(sine / 43)),math.rad(-22 - 2 * math.cos(sine / 56))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.085 * math.cos(sine / 22),0.2)*angles(math.rad(148 + 3 * math.cos(sine / 23)),math.rad(0 - 1 * math.cos(sine / 32)),math.rad(-22)),.1)
LW.C0=clerp(LW.C0,cf(-1.35,0.5 + 0.125 * math.cos(sine / 22),0)*angles(math.rad(5 - 2 * math.cos(sine / 21)),math.rad(16 - 4 * math.cos(sine / 44)),math.rad(-13 - 6 * math.cos(sine / 25))),.1)
elseif ModeOfGlitch == 4004 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 45),0)*angles(math.rad(15),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 45),0)*angles(math.rad(15),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0 + 0.05 * math.cos(sine / 45))*angles(math.rad(15 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 44))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 10 * math.random(0,2)),math.rad(30 - 30 * math.random(0,2)),math.rad(30 - 30 * math.random(0,2))),.1)
RW.C0=clerp(RW.C0,cf(1.45,0.4 + 0.05 * math.cos(sine / 32),0)*angles(math.rad(190 - 27 * math.random(0,2)),math.rad(20 - 20 * math.random(0,2)),math.rad(-10 - 7 * math.random(0,2))),.1)
LW.C0=clerp(LW.C0,cf(-1.45,0.4 + 0.05 * math.cos(sine / 32),0)*angles(math.rad(190 - 27 * math.random(0,2)),math.rad(20 - 20 * math.random(0,2)),math.rad(17 - 7 * math.cos(sine / 1))),.1)
elseif ModeOfGlitch == 10 then
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 5 * math.cos(sine / 51))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 3 * math.cos(sine / 44))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.45 * math.cos(sine / 18))*angles(math.rad(0 - 2 * math.cos(sine / 18)),math.rad(0),math.rad(-36)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(36 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(3 + 7 * math.cos(sine / 79)),math.rad(1 - 3 * math.cos(sine / 53)),math.rad(33 + 10 * math.cos(sine / 46))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(15 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(-27 - 6 * math.cos(sine / 27))),.1)
elseif ModeOfGlitch == 676767 then
local snap = math.random(1,10)
if snap == 1 then
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 + math.random(-10,10)),math.rad(math.random(-10,10)),math.rad(math.random(-10,10))),1)
end
sphere2(8,"Add",rleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(8,"Add",lleg.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,MAINRUINCOLOR,MAINRUINCOLOR.Color)
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Alder"),Color3.new(0.7,0.7,1))
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-14 - 5 * math.cos(sine / 48))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 7 * math.cos(sine / 51))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,6 + 0.5 * math.cos(sine / 24))*angles(math.rad(10 - 0.5 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 1 * math.cos(sine / 0.5265)),math.rad(0 - 1 * math.cos(sine / 0.25)),math.rad(0 - 1 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(1,0.35 + 0.025 * math.cos(sine / 45),-0.5)*angles(math.rad(62 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(-82 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.3,0.7,0)*angles(math.rad(0 + 1 * math.cos(sine / 0.568)),math.rad(15 - 5 * math.cos(sine / 24)),math.rad(-145 - 15 * math.cos(sine / 24))),.1)
elseif ModeOfGlitch == 70077 then
RH.C0=clerp(RH.C0,cf(1,-.5,0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-14 - 5 * math.cos(sine / 48))),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.5,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(15 + 7 * math.cos(sine / 51))),.1)
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(-0.1 + 0.1 * math.cos(sine / 12), -0.1 + 0.1 * math.cos(sine / 12), -0.1 + 0.1 * math.cos(sine / 12)) * angles(math.random(-25,25),math.random(-25,25),math.random(-25,25)), 0.15)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-15 - 15 * math.cos(sine / 12)),math.rad(15 - 15 * math.cos(sine / 12)),math.rad(15 - 15 * math.cos(sine / 12))),.1)
RW.C0=clerp(RW.C0,cf(1.35,1,0)*angles(math.rad(15 - 15 * math.cos(sine / 12)),15 - 15 * math.cos(sine / 12),15 - 15 * math.cos(sine / 12)),.1)
LW.C0=clerp(LW.C0,cf(-1.35,1,0)*angles(math.rad(-15 - 15 * math.cos(sine / 12)),-15 - 15 * math.cos(sine / 12),-15 - 15 * math.cos(sine / 12)),.1)
elseif ModeOfGlitch == 0101 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(0 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(0 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),-0.1 + 0.05 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(-10)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(5 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(10 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.01 * math.cos(sine / 8))*angles(math.rad(90 - 1 * math.cos(sine / 8)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0 - 0.01 * math.cos(sine / 8))*angles(math.rad(90 + 1 * math.cos(sine / 8)),math.rad(0),math.rad(-0 + 1 * math.cos(sine / 4))),.1)

elseif ModeOfGlitch == 912 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-0 + 2 * math.cos(sine / 0.2))),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(0 - 2 * math.cos(sine / 0.2))),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.01 * math.cos(SINE / 32),0.3,5 + 0.5 * math.cos(sine / 24))*angles(math.rad(-30 - 0.01 * math.cos(SINE / 32)),math.rad(0 - 0.01 * math.cos(SINE / 32)),math.rad(0 - 0.01 * math.cos(SINE / 32))),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-30),math.rad(0),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(0 - 2 * math.cos(sine / 0.2)),math.rad(80 + 2 * math.cos(sine / 0.2))),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(0 + 2 * math.cos(sine / 0.2)),math.rad(-80 - 2 * math.cos(sine / 0.2))),.5)

elseif ModeOfGlitch == 9123 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(6),math.rad(0),math.rad(25 + 1 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(3),math.rad(0),math.rad(-35 + 1 * math.cos(sine / 34))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 47),0 + 0.25 * math.cos(sine / 35),7 + 1 * math.cos(sine / 32))*angles(math.rad(27 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(13)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-35 - 2.5 * math.cos(sine / 28)),math.rad(10 + 2.5 * math.cos(sine / 75)),math.rad(0)),.2)
RW.C0=clerp(RW.C0,cf(1.35,0.45 + 0.025 * math.cos(sine / 28),-0.2)*angles(math.rad(40),math.rad(0),math.rad(-1)),.2)
LW.C0=clerp(LW.C0,cf(-1.35,0.45 + 0.025 * math.cos(sine / 28),-0.2)*angles(math.rad(40),math.rad(0),math.rad(3)),.2)

elseif ModeOfGlitch == 91234 then
	local beepboop = math.random(1,2)
	if beepboop == 1 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(0 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(0 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),-0.1 + 0.05 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(-10)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(5 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(10 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.01 * math.cos(sine / 8))*angles(math.rad(90 - 1 * math.cos(sine / 8)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0 - 0.01 * math.cos(sine / 8))*angles(math.rad(90 + 1 * math.cos(sine / 8)),math.rad(0),math.rad(-0 + 1 * math.cos(sine / 4))),.1)
	end 
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 1 + 0.5 * Player_Size * Cos(sine / 20)) * angles(Rad(0), Rad(0), Rad(0)), 0.08)
tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15 - 2.5 * Sin(sine / 30)), Rad(20), Rad(0)), 0.08)
RH.C0 = clerp(RH.C0, CF(1* Player_Size, -0.3 - 0.1 * Cos(sine / 20)* Player_Size, -.4* Player_Size) * angles(Rad(0), Rad(80), Rad(0)) * angles(Rad(-10.5 + 3.5 * Sin(sine / 20)), Rad(0), Rad(-20)), 0.08)
LH.C0 = clerp(LH.C0, CF(-1* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-80), Rad(0)) * angles(Rad(-10.5 + 3.5 * Sin(sine / 20)), Rad(0), Rad(20)), 0.08)
RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(0), Rad(25 + 10.5 * Sin(sine / 20))), 0.08)
LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(0), Rad(-25 - 10.5 * Sin(sine / 20))), 0.08)

elseif ModeOfGlitch == 912345 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(1 - 2 * math.cos(sine / 32))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 32),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-1 + 2 * math.cos(sine / 32))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.02 + 0.02 * math.cos(sine / 32),0 + 0.05 * math.cos(sine / 32))*angles(math.rad(2 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0 - 1 * math.cos(sine / 44))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(22 - 3 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1,0.5 + 0.005 * math.cos(sine / 45),-0.5)*angles(math.rad(84 + 6 * math.cos(sine / 74)),math.rad(8 - 5 * math.cos(sine / 53)),math.rad(-80 + 3 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),0.45)*angles(math.rad(-23 - 3 * math.cos(sine / 73)),math.rad(2 - 1 * math.cos(sine / 55)),math.rad(33 - 3 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 9123456 then
	RH.C0=clerp(RH.C0,cf(1,-0.45,-0.45)*angles(math.rad(0),math.rad(90 + 2 * math.cos(SINE / 32)),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(20)),.6)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90 - 2 * math.cos(SINE / 32)),math.rad(0))*angles(math.rad(-3),math.rad(0),math.rad(40)),.6)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.5,-1)*angles(math.rad(20 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.6)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(15 - 10 * math.cos(kan.PlaybackLoudness/60)),math.rad(0 + 2 * math.cos(SINE / 32)),math.rad(0 + 2 * math.cos(SINE / 32))),.6)
RW.C0=clerp(RW.C0,cf(1.05,0.5,-0.5)*angles(math.rad(30 - 2 * math.cos(SINE / 32)),math.rad(0),math.rad(-30)),.6)
LW.C0=clerp(LW.C0,cf(-1.05,0.5,-0.5)*angles(math.rad(30 + 2 * math.cos(SINE / 32)),math.rad(0),math.rad(75 + 2 * math.cos(SINE / 32))),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0 - 0.01 * math.cos(SINE / 32),1,0 - 0.01 * math.cos(SINE / 32))*angles(math.rad(0),math.rad(65 + 2 * math.cos(SINE / 32)),math.rad(0)),.6)
elseif ModeOfGlitch == 91234567 then
		local snapo = math.random(1,8)
		if snapo == 1 then
		tors.Neck.C0=clerp(tors.Neck.C0,necko*angles(math.rad(32 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),1)
		end
		sphere23(8,"Add",rl.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(Rad(math.random(-360,360)),Rad(math.random(-360,360)),Rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Smoky grey"),BrickColor.new("Smoky grey").Color)
		sphere23(8,"Add",ra.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(Rad(math.random(-360,360)),Rad(math.random(-360,360)),Rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Smoky grey"),BrickColor.new("Smoky grey").Color)
		RH.C0=clerp(RH.C0,CF(1,-0.4,-0.5)*angles(Rad(0),Rad(90),Rad(0))*angles(Rad(-3),Rad(0 - 1 * Cos(sine / 56)),Rad(-10 - 9 * Cos(sine / 51))),.1)
		LH.C0=clerp(LH.C0,CF(-1,-1,0)*angles(Rad(0),Rad(-90),Rad(0))*angles(Rad(-3),Rad(0 - 1 * Cos(sine / 56)),Rad(10 + 7 * Cos(sine / 44))),.1)
		RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 47),0 + 0.25 * math.cos(sine / 35),7 + 1 * math.cos(sine / 32))*angles(math.rad(2 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(13)),.1)
		RW.C0=clerp(RW.C0,cf(1,0.5+.2*math.cos(sine/16),-.65)*angles(math.rad(45),0,math.rad(-90)),.1)
		LW.C0=clerp(LW.C0,cf(-1.35,1 + 0.025 * math.cos(sine / 45),-0.2)*angles(math.rad(148 - 2 * math.cos(sine / 51)),math.rad(0 - 4 * math.cos(sine / 64)),math.rad(22 - 2 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 7788 then
				Humanoid.CameraOffset = Vector3.new(0, 10.25 - 5.45 * math.cos(sine / 65), 0)
				RootJoint.C0 = clerp(RootJoint.C0, RootCF * CFrame.new(0, 0, 10.25 - 5.45 * math.cos(sine / 65)) * CFrame.Angles(math.rad(-90 - 15 * math.sin(sine / 60)), math.rad(0), math.rad(0)), 0.8)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-20 + 20 * math.cos(sine / 60)), math.rad(0 + 4 * math.sin(sine / 60)), math.rad(0)), 0.2)
				RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-90 + 25 * math.cos(sine / 60)), math.rad(0 + 20 * math.sin(sine / 60)), math.rad(0 + 55 * math.sin(sine / 60))), 0.3)
				LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-90 + 25 * math.cos(sine / 60)), math.rad(-20 - 20 * math.sin(sine / 60)), math.rad(0 - 55 * math.sin(sine / 60))), 0.3)
				LH.C0 = clerp(LH.C0, CFrame.new(-0.5, -0.86 + 0.03 * math.cos(sine / 65), -0.2) * CFrame.Angles(math.rad(15 - 45 * math.cos(sine / 70)), math.rad(3), math.rad(-4)), 0.8)
				RH.C0 = clerp(RH.C0, CFrame.new(0.5, -0.5 + 0.05 * math.cos(sine / 65), -0.2) * CFrame.Angles(math.rad(15 - 35 * math.cos(sine / 65)), math.rad(-3), math.rad(4)), 0.8)
elseif ModeOfGlitch == 912345678 then
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, 0 + 0.15 * COS(SINE / 10)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.1)
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0) * ANGLES(RAD(30 - 2.5 * SIN(SINE / 22)), RAD(15), RAD(0)), 0.1)
if math.random(1,6) == 1 then
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + math.random(-25,25) - 4 * COS(SINE / 12)), RAD(math.random(-25,25)), RAD(0)), 1.5)
end
RW.C0=clerp(RW.C0,cf(1.45,0.4 + 0.05 * math.cos(sine / 32),0)*angles(math.rad(190 - 27 * math.random(0,2)),math.rad(20 - 20 * math.random(0,2)),math.rad(-10 - 7 * math.random(0,2))),.1)
LW.C0 = clerp(LW.C0, CF(-1, 0.5, -0.5) * ANGLES(RAD(-40 + -11 * COS(SINE / 23)), RAD(25), RAD(75)), 0.1)
RH.C0 = clerp(RH.C0, CF(1, -1 - 0.15 * COS(SINE / 10), -0.01) * ANGLES(RAD(0), RAD(80), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.1)
LH.C0 = clerp(LH.C0, CF(-1, -1 - 0.15 * COS(SINE / 10), -0.01) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.1)

elseif ModeOfGlitch == 10101010 then -- BALANCED
RH.C0=clerp(RH.C0,cf(1,-0.25,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0-5*math.sin(sine/33)),math.rad(-10-5*math.sin(sine/53))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0+5*math.sin(sine/33)),math.rad(10+5*math.sin(sine/53))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,2.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(0 - 2 * math.cos(sine / 34)),math.rad(0),math.rad(0 - 4 * math.cos(sine /61))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 + 3 * math.cos(sine / 67)),math.rad(0 + 2 * math.cos(sine / 53)),math.rad(0 + 4 * math.cos(sine / 73))),.1)
RW.C0=clerp(RW.C0,cf(0.85,0.5 + 0.1 * math.cos(sine / 28),-0.65)*angles(math.rad(30 - 3 * math.cos(sine / 39)),math.rad(0),math.rad(-100 - 4 * math.cos(sine / 47))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(6 + 3 * math.cos(sine / 52)),math.rad(0+1.5*math.cos(sine/43)),math.rad(-15 - 4 * math.cos(sine / 34))),.1)
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Black',0)
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'White',0)

elseif ModeOfGlitch == 929292 then -- Dream
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Alder',0)--right
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Navy blue',0)
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Alder"),BrickColor.new("Alder").Color)--right
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Dark blue"),Color3.new(0,0,255))
RH.C0=clerp(RH.C0,cf(1,-1,-0.35)*angles(math.rad(-15),math.rad(84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,-0.2)*angles(math.rad(-10),math.rad(-84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.15 * math.cos(sine / 32))*angles(math.rad(-5 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(136 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(-140.3 - 4 * math.cos(sine / 45))),.1)
elseif ModeOfGlitch == 40044 then
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.25 * math.cos(sine / 50),0 + 0.25 * math.cos(sine / 43),6 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 5 * math.cos(sine / 0.5265)),math.rad(0 - 5 * math.cos(sine / 0.25)),math.rad(0 - 5 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(10 + 2.5 * math.cos(sine / 0.252)),math.rad(0 + 2.5 * math.cos(sine / 0.123)),math.rad(5 + 2.5 * math.cos(sine / 0.6))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(10 + 2.5 * math.cos(sine / 0.568)),math.rad(0 + 2.5 * math.cos(sine / 0.664)),math.rad(-5 + 2.5 * math.cos(sine / 0.23))),.1)

end
end
--sword welding
if equipped == true and ModeOfGlitch ~= 9123456 then
RW.C0=clerp(RW.C0,cf(1.45,0.5 + 0.05 * math.cos(sine / 28),0.1)*angles(math.rad(0),math.rad(0),math.rad(40 - 10 * math.cos(sine / 34))),.1)
weaponweld.C1=clerp(weaponweld.C1,cf(0,1,0)*angles(math.rad(0),math.rad(130),math.rad(0)),.3)
end
--walking anims
		elseif torvel > 2 and torvel < 22 and hitfloor ~= nil then
			Anim = "Walk"
			if attack == false then
				if ModeOfGlitch == 1 then
					RH.C0 = clerp(RH.C0, cf(1, -0.85, -0.15 - 0.15 * math.cos(sine / 4)) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 8)), math.rad(0 + 25 * math.cos(sine / 8))), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -0.85, -0.15 + 0.15 * math.cos(sine / 4)) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 8)), math.rad(0 + 25 * math.cos(sine / 8))), 0.1)
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -0.15 - 0.1 * math.cos(sine / 4)) * angles(math.rad(5), math.rad(0), math.rad(0 - 5 * math.cos(sine / 8))), 0.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(25 - 5 * math.cos(sine / 0.325)), math.rad(0 - 5 * math.cos(sine / 0.25)), math.rad(0 + 5 * math.cos(sine / 8))), 0.1)
					RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(0 - 45 * math.cos(sine / 8)), math.rad(0), math.rad(10 - 10 * math.cos(sine / 4))), 0.1)
					LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(160), math.rad(0), math.rad(25)), 0.1)
elseif ModeOfGlitch == 666 then
RH.C0=clerp(RH.C0,cf(1,-0.85,-0.15 - 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(5 + 25 * math.cos(sine / 12))),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.85,-0.15 + 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(-5 + 25 * math.cos(sine / 12))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-0.15 - 0.1 * math.cos(sine / 8))*angles(math.rad(12.5),math.rad(0),math.rad(0 - 5 * math.cos(sine / 12))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 5 * math.cos(sine / 0.5265)),math.rad(0 - 5 * math.cos(sine / 0.25)),math.rad(0 - 5 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
LW.C0=clerp(LW.C0,cf(-0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(20 - 2.5 * math.cos(sine / 28))),.1)
				elseif ModeOfGlitch == 998877 then
RH.C0=clerp(RH.C0,cf(1,-0.85,-0.15 - 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(5 + 25 * math.cos(sine / 12))),.1)
LH.C0=clerp(LH.C0,cf(-1,-0.85,-0.15 + 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(-5 + 25 * math.cos(sine / 12))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-0.15 - 0.1 * math.cos(sine / 8))*angles(math.rad(12.5),math.rad(0),math.rad(0 - 5 * math.cos(sine / 12))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 5 * math.cos(sine / 0.5265)),math.rad(0 - 5 * math.cos(sine / 0.25)),math.rad(0 - 5 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(1.3,0.5,0)*angles(math.rad(180),math.rad(-90),math.rad(15))*angles(math.rad(-35),0,0)*angles(math.rad(10 + 2.5 * math.cos(sine / 0.252)),math.rad(0 + 2.5 * math.cos(sine / 0.123)),math.rad(5 + 2.5 * math.cos(sine / 0.6)))*angles(0,math.rad(0 - 15 * math.cos(sine / 0.25)),math.rad(0 - 15 * math.cos(sine / 0.465))),.1)
LW.C0=clerp(LW.C0,cf(-1.3,0.5,0)*angles(math.rad(180),math.rad(90),math.rad(-15))*angles(math.rad(-35),0,0)*angles(math.rad(10 + 2.5 * math.cos(sine / 0.568)),math.rad(0 + 2.5 * math.cos(sine / 0.664)),math.rad(-5 + 2.5 * math.cos(sine / 0.23)))*angles(0,math.rad(0 - 15 * math.cos(sine / 0.25)),math.rad(0 - 15 * math.cos(sine / 0.465))),.1)

            elseif ModeOfGlitch == 91234 then
                RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 1 + 0.5 * Player_Size * Cos(sine / 20)) * angles(Rad(20), Rad(0), Rad(0)), 0.15)
                tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(15 - 2.5 * Sin(sine / 30)), Rad(0), Rad(0)), 0.3)
                RH.C0 = clerp(RH.C0, CF(1* Player_Size, -0.3 - 0.1 * Cos(sine / 20)* Player_Size, -.4* Player_Size) * angles(Rad(0), Rad(80), Rad(0)) * angles(Rad(-10.5 + 3.5 * Sin(sine / 20)), Rad(0), Rad(-20)), 0.15)
                LH.C0 = clerp(LH.C0, CF(-1* Player_Size, -0.9 - 0.1 * Cos(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(0), Rad(-80), Rad(0)) * angles(Rad(-10.5 + 3.5 * Sin(sine / 20)), Rad(0), Rad(20)), 0.15)
                RW.C0 = clerp(RW.C0, CF(1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(-35), Rad(0), Rad(25)), 0.1)
                LW.C0 = clerp(LW.C0, CF(-1.5* Player_Size, 0.5 + 0.02 * Sin(sine / 20)* Player_Size, 0* Player_Size) * angles(Rad(-35), Rad(0), Rad(-25)), 0.1)

elseif ModeOfGlitch == 912 then
RH.C0=clerp(RH.C0,cf(1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(-20 + 2 * math.cos(sine / 0.2))),.5)
LH.C0=clerp(LH.C0,cf(-1,-1 - 0.05 * math.cos(sine / 28),0)*angles(math.rad(-20 - 2 * math.cos(sine / 12)),math.rad(-90),math.rad(0))*angles(math.rad(-2.5),math.rad(0),math.rad(20 - 2 * math.cos(sine / 0.2))),.5)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0.3,5 + 0.05 * math.cos(sine / 24))*angles(math.rad(15 - 0.01 * math.cos(SINE / 32)),math.rad(0 - 0.01 * math.cos(SINE / 32)),math.rad(0 - 0.01 * math.cos(SINE / 32))),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(50 - 2 * math.cos(sine / 12)),math.rad(0 - 2 * math.cos(sine / 12)),math.rad(0 - 2.5 * math.cos(sine / 0.2))),.5)
RW.C0=clerp(RW.C0,cf(1.45,0.4,0)*angles(math.rad(-20),math.rad(150),math.rad(80 + 2 * math.cos(sine / 0.2))),.5)
LW.C0=clerp(LW.C0,cf(-1.45,0.4,0)*angles(math.rad(-20),math.rad(-150),math.rad(-80 - 2 * math.cos(sine / 0.2))),.5)

				elseif ModeOfGlitch == 0101 then --infected
RH.C0=clerp(RH.C0,cf(1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.05,-0.05 - 0.05 * math.cos(sine / 4))*angles(math.rad(5 + 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - root.RotVelocity.Y - 5 * math.cos(sine / 8))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - hed.RotVelocity.Y*1.5 + 5 * math.cos(sine / 8))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.25 * math.cos(sine / 8))*angles(math.rad(90 - 15 * math.cos(sine / 8)),math.rad(0),math.rad(5 - 2.5 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0 - 0.25 * math.cos(sine / 8))*angles(math.rad(90 + 15 * math.cos(sine / 8)),math.rad(0),math.rad(-5 + 2.5 * math.cos(sine / 4))),.1)


elseif ModeOfGlitch == 9123456 then
RH.C0=clerp(RH.C0,cf(1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.05,-0.05 - 0.05 * math.cos(sine / 4))*angles(math.rad(5 + 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - root.RotVelocity.Y - 5 * math.cos(sine / 8))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - hed.RotVelocity.Y*1.5 + 5 * math.cos(sine / 8))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.05 * math.cos(sine / 8))*angles(math.rad(0 - 2 * math.cos(sine / 8)),math.rad(0),math.rad(35 - 2 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.5,-0.5)*angles(math.rad(30 + 2 * math.cos(SINE / 32)),math.rad(0),math.rad(75 + 2 * math.cos(SINE / 32))),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0 - 0.01 * math.cos(SINE / 32),1,0 - 0.01 * math.cos(SINE / 32))*angles(math.rad(0),math.rad(-90 - 0.01 * math.cos(SINE / 32)),math.rad(0)),.6)

elseif ModeOfGlitch == 912345678 then
			Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(15 + MRANDOM(-5,5) - 1 * SIN(SINE / 2)), RAD(MRANDOM(-5,5)), RAD(0)), .1)
			if MRANDOM(1,10) == 1 then
				Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0 + ((1.2) - 1)) * ANGLES(RAD(0 + MRANDOM(-30,30) - 4 * COS(SINE / 12)), RAD(MRANDOM(-30,30)), RAD(0)), 1.5)
			end
			RW.C0 = clerp(RW.C0, CF(1, 0.5, -0.5) * ANGLES(RAD(55 + -11 * COS(SINE / 23)), RAD(-10), RAD(-75)), 1)
			LW.C0 = clerp(LW.C0, CF(-1, 0.5, -0.5) * ANGLES(RAD(-40 + -11 * COS(SINE / 23)), RAD(25), RAD(75)), 1)	
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, 0 + 0.15 * COS(SINE / 10)) * ANGLES(RAD(0), RAD(0), RAD(0)), .1)
		RH.C0 = clerp(RH.C0, CF(1, -1 - 0.125 * SIN(SINE / 16) - 0.15 * COS(SINE / 16*2), 0) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(35 * COS(SINE / 16))), 0.6)
		LH.C0 = clerp(LH.C0, CF(-1, -1 + 0.125 * SIN(SINE / 16) - 0.15 * COS(SINE / 16*2), 0) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(35 * COS(SINE / 16))), 0.6)
				elseif ModeOfGlitch == 111111112 then
                RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0* Player_Size, 0* Player_Size, 2 + 0.25* Player_Size * Cos(sine / 12)) * angles(Rad(25), Rad(0), Rad(0)), 0.1)
                tors.Neck.C0 = clerp(tors.Neck.C0, necko* CF(0, 0, 0 + ((1* Player_Size) - 1)) * angles(Rad(-15 - 6.5 * Sin(sine / 12)), Rad(20), Rad(0)), 0.1)
                RH.C0 = clerp(RH.C0, CF(1* Player_Size, -1 - 0.15 * Cos(sine / 20)* Player_Size, -0.1* Player_Size) * angles(Rad(0), Rad(76), Rad(0)) * angles(Rad(-18.5 - 6.5 * Sin(sine / 12)), Rad(0), Rad(-35)), 0.1)
                LH.C0 = clerp(LH.C0, CF(-1.1* Player_Size, -0.6 - 0.15 * Cos(sine / 20)* Player_Size, -0.2* Player_Size) * angles(Rad(0), Rad(-76), Rad(0)) * angles(Rad(-18.5 - 6.5 * Sin(sine / 12)), Rad(15), Rad(35)), 0.1)
                RW.C0 = clerp(RW.C0, CF(1.4* Player_Size, 0.4 + 0.08 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(-45 - 6.5 * Cos(sine / 12)), Rad(-.6), Rad(25 + 6.5 * Sin(sine / 12))), 0.1)
                LW.C0 = clerp(LW.C0, CF(-1.4* Player_Size, 0.4 + 0.08 * Sin(sine / 12)* Player_Size, 0* Player_Size) * angles(Rad(-45 - 6.5 * Cos(sine / 12)), Rad(-.6), Rad(-25 - 6.5 * Sin(sine / 12))), 0.1)
 				elseif ModeOfGlitch == 353567 then
					RH.C0 = clerp(RH.C0, cf(1, -0.85, -0.15 - 0.15 * math.cos(sine / 8)) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 12)), math.rad(5 + 25 * math.cos(sine / 12))), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -0.85, -0.15 + 0.15 * math.cos(sine / 8)) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 12)), math.rad(-5 + 25 * math.cos(sine / 12))), 0.1)
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -0.15 - 0.1 * math.cos(sine / 8)) * angles(math.rad(12.5), math.rad(0), math.rad(0 - 5 * math.cos(sine / 12))), 0.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(30 - 5 * math.cos(sine / 0.5265)), math.rad(0 - 5 * math.cos(sine / 0.25)), math.rad(0 - 5 * math.cos(sine / 0.465))), 0.1)
					RW.C0 = clerp(RW.C0, cf(0.85, 0.5 + 0.1 * math.cos(sine / 50), -0.65) * angles(math.rad(30 - 1 * math.cos(sine / 50)), math.rad(0), math.rad(-100 - 2.5 * math.cos(sine / 50))), 0.1)
					LW.C0 = clerp(LW.C0, cf(-0.85, 0.5 + 0.1 * math.cos(sine / 50), -0.65) * angles(math.rad(40 - 1 * math.cos(sine / 50)), math.rad(0), math.rad(90 + 2.5 * math.cos(sine / 50))), 0.1)
				elseif ModeOfGlitch == 4 then
					RH.C0 = clerp(RH.C0, cf(1, -0.85, -0.15 - 0.15 * math.cos(sine / 8)) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 12)), math.rad(5 + 25 * math.cos(sine / 12))), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -0.85, -0.15 + 0.15 * math.cos(sine / 8)) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(0), math.rad(0 + 5 * math.cos(sine / 12)), math.rad(-5 + 25 * math.cos(sine / 12))), 0.1)
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * cf(0, 0, -0.15 - 0.1 * math.cos(sine / 8)) * angles(math.rad(12.5), math.rad(0), math.rad(0 - 5 * math.cos(sine / 12))), 0.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(30 - 5 * math.cos(sine / 0.5265)), math.rad(0 - 5 * math.cos(sine / 0.25)), math.rad(0 - 5 * math.cos(sine / 0.465))), 0.1)
					RW.C0 = clerp(RW.C0, cf(1.5, 0.5, 0) * angles(math.rad(10 - 15 * math.cos(sine / 12)), math.rad(0 + 2.5 * math.cos(sine / 0.123)), math.rad(5 + 2.5 * math.cos(sine / 0.6))), 0.1)
					LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(10 + 15 * math.cos(sine / 12)), math.rad(0 + 2.5 * math.cos(sine / 0.664)), math.rad(-5 + 2.5 * math.cos(sine / 0.23))), 0.1)
				elseif ModeOfGlitch == 688 then
					RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-10)), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(10)), 0.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0.5 - 0.1 * math.cos(sine / 16))*angles(math.rad(12.5),math.rad(0),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 12))),.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(15 - 2.5 * math.cos(sine / 28)), math.rad(0), math.rad(0)), 0.1)
					RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
					LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
		elseif ModeOfGlitch == 7788 then
				Humanoid.CameraOffset = Vector3.new(0, 6 - 2.55 * math.cos(sine / 48.5), 0)
				Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(-4 + 2 * math.sin(sine / 48)), math.rad(0), math.rad(0)), 0.2)
				RW.C0 = clerp(RW.C0, cf(1.5, 0.5 + 0.1 * math.cos(sine / 45), 0) * angles(math.rad(90), math.rad(0), math.rad(90 - 20.5 * math.cos(sine / 45))), 0.3)
				LW.C0 = clerp(LW.C0, cf(-1.5, 0.5 + 0.1 * math.cos(sine / 45), 0) * angles(math.rad(90), math.rad(0), math.rad(-90 + 20.5 * math.cos(sine / 45))), 0.3)
				LH.C0 = clerp(LH.C0, CFrame.new(-0.5, -1 - 0.05 * math.cos(sine / 45), 0) * CFrame.Angles(math.rad(0), math.rad(3), math.rad(-4)), 0.8)
				RH.C0 = clerp(RH.C0, CFrame.new(0.5, -1 + 0.05 * math.cos(sine / 45), 0) * CFrame.Angles(math.rad(0), math.rad(-3), math.rad(4)), 0.8)

		elseif ModeOfGlitch == 109124 then
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,-0.15 - 0.1 * math.cos(sine / 8))*angles(math.rad(12.5),math.rad(0),math.rad(0 - 5 * math.cos(sine / 12))),.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0) - hed.RotVelocity.Y / 15), 0.3)
					RH.C0=clerp(RH.C0,cf(1,-0.85,-0.15 - 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(5 + 25 * math.cos(sine / 12))),.1)
					LH.C0=clerp(LH.C0,cf(-1,-0.85,-0.15 + 0.15 * math.cos(sine / 8))*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 12)),math.rad(-5 + 25 * math.cos(sine / 12))),.1)
					RW.C0=clerp(RW.C0,cf(0.75,0.5,-0.25)*angles(math.rad(140),math.rad(0),math.rad(-20 + 2.5 * math.cos(sine / 28))),.1)
					LW.C0 = clerp(LW.C0, cf(-1.5, 0.5, 0) * angles(math.rad(0 + 15 * math.cos(sine / 30)), math.rad(0), math.rad(-1 + 0 * math.cos(sine / 30))), 0.1)
				elseif ModeOfGlitch == 2334 then
					RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, -0.175 + 0.025 * Cos(sine / 3.5) + -Sin(sine / 3.5) / 7) * angles(Rad(9-2.5 * Cos(sine / 3.5)), Rad(0), Rad(10 * Cos(sine / 7))), 0.15)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(Rad(0), Rad(0), Rad(0)), 0.3)
					RH.C0 = clerp(RH.C0, CFrame.new(1, -0.925 - 0.5 * math.cos(sine / 7) / 2, 0.5 * math.cos(sine / 7) / 2) * angles(math.rad(-15 - 35 * math.cos(sine / 7)) + -math.sin(sine / 7) / 2.5, math.rad(90 - 2 * math.cos(sine / 7)), math.rad(0)) * angles(math.rad(0 + 2.5 * math.cos(sine / 7)), math.rad(0), math.rad(0)), 0.3)
					LH.C0 = clerp(LH.C0, CFrame.new(-1, -0.925 + 0.5 * math.cos(sine / 7) / 2, -0.5 * math.cos(sine / 7) / 2) * angles(math.rad(-15 + 35 * math.cos(sine / 7)) + math.sin(sine / 7) / 2.5, math.rad(-90 - 2 * math.cos(sine / 7)), math.rad(0)) * angles(math.rad(0 - 2.5 * math.cos(sine / 7)), math.rad(0), math.rad(0)), 0.3)
					RW.C0 = clerp(RW.C0, CF(1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(70) * Cos(sine / 7) , Rad(0), Rad(5)), 0.1)
					LW.C0 = clerp(LW.C0, CF(-1.5, 0.5 + 0.05 * Sin(sine / 30), 0.025 * Cos(sine / 20)) * angles(Rad(-70) * Cos(sine / 7) , Rad(0),	Rad(-5)), 0.1)
				elseif ModeOfGlitch ~= 1 or ModeOfGlitch ~= 4 and ModeOfGlitch ~= 2334 and ModeOfGlitch ~= 109124 and ModeOfGlitch ~= 666 and ModeOfGlitch ~= 99887 and ModeOfGlitch ~= 111111112 and ModeOfGlitch ~= 353567 and ModeOfGlitch ~= 688 and ModeOfGlitch ~= 0101 and ModeOfGlitch ~= 912 and ModeOfGlitch ~= 9123456 and ModeOfGlitch ~= 7788 and ModeOfGlitch ~= 912345678 then
RH.C0=clerp(RH.C0,cf(1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.05,-0.05 - 0.05 * math.cos(sine / 4))*angles(math.rad(5 + 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - root.RotVelocity.Y - 5 * math.cos(sine / 8))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - hed.RotVelocity.Y*1.5 + 5 * math.cos(sine / 8))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.25 * math.cos(sine / 8))*angles(math.rad(0 - 50 * math.cos(sine / 8)),math.rad(0),math.rad(5 - 10 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0 - 0.25 * math.cos(sine / 8))*angles(math.rad(0 + 50 * math.cos(sine / 8)),math.rad(0),math.rad(-5 + 10 * math.cos(sine / 4))),.1)
				end
			end
		elseif torvel >= 22 and hitfloor ~= nil then -- running anims
			Anim = "Run"
			if attack == false then
				if ModeOfGlitch ~= 6 and ModeOfGlitch ~= 1000000 and ModeOfGlitch ~= 9797 and ModeOfGlitch ~= 8376532578634534 and ModeOfGlitch ~= 8787 and ModeOfGlitch ~= 102341 and ModeOfGlitch ~= 699 and ModeOfGlitch ~= 666 and ModeOfGlitch ~= 778899 and ModeOfGlitch ~= 688 and ModeOfGlitch ~= 47 and ModeOfGlitch ~= 808080 and ModeOfGlitch ~= 765688533321 and ModeOfGlitch ~= 676767 and ModeOfGlitch ~= 3003 and ModeOfGlitch ~= 10 and ModeOfGlitch ~= 7007 and ModeOfGlitch ~= 8 and ModeOfGlitch ~= 70077 and ModeOfGlitch ~= 9123 and ModeOfGlitch ~= 91234 and ModeOfGlitch ~= 9123456 and ModeOfGlitch ~= 91234567 and ModeOfGlitch ~= 10101010 and ModeOfGlitch ~= 929292 and ModeOfGlitch ~= 40044 then
					RH.C0=clerp(RH.C0,cf(1,-1 - 0.15 * math.cos(sine / 3),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0 + 95 * math.cos(sine / 6))),.1)
					LH.C0=clerp(LH.C0,cf(-1,-1 - 0.15 * math.cos(sine / 3),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0),math.rad(0 + 95 * math.cos(sine / 6))),.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.3,-0.05 + 0.15 * math.cos(sine / 3))*angles(math.rad(25 - 4 * math.cos(sine / 3)),math.rad(0 + root.RotVelocity.Y*1.5),math.rad(0 - root.RotVelocity.Y - 1 * math.cos(sine / 6))),.1)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-6 + 2 * math.cos(sine / 3)),math.rad(0 + root.RotVelocity.Y*1.5),math.rad(0 - hed.RotVelocity.Y*1.5 + 1 * math.cos(sine / 6))),.1)
					RW.C0=clerp(RW.C0,cf(1.5,0.5,0.3)*angles(math.rad(-50 + 10 * math.cos(sine / 3)),math.rad(-10),math.rad(7 + 5 * math.cos(sine / 6))),.1)
					LW.C0=clerp(LW.C0,cf(-1.5,0.5,0.3)*angles(math.rad(-50 + 10 * math.cos(sine / 3)),math.rad(10),math.rad(-7 - 5 * math.cos(sine / 6))),.1)
elseif ModeOfGlitch == 808080 or ModeOfGlitch == 765688533321 or ModeOfGlitch == 676767 then
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,6.5 + 0.25 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.05)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
elseif ModeOfGlitch == 3003 or ModeOfGlitch == 10 or ModeOfGlitch == 7007 or ModeOfGlitch == 8 then
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,0.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
elseif ModeOfGlitch == 70077 then --Guest Glitcher xddd
RootJoint.C0 = clerp(RootJoint.C0, RootCF * CF(0, 0, 0 + 0.25 * COS(sine / 12)) * angles(RAD(25 + 2.5 * SIN(sine / 12)), RAD(0), RAD(5 + 2.5 * SIN(sine / 12))), 0.1)
Neck.C0 = clerp(Neck.C0, necko * CF(0, 0, 0) * angles(RAD(-25 + 4.5 * SIN(sine / 12)), RAD(0), RAD(-5 - 2.5 * SIN(sine / 12))), 0.1)
RW.C0=clerp(RW.C0,cf(1.35,1,0)*angles(math.rad(15 - 30 * math.cos(sine / 12)),15 - 30 * math.cos(sine / 12),15 - 30 * math.cos(sine / 12)),.1)
LW.C0=clerp(LW.C0,cf(-1.35,1,0)*angles(math.rad(-15 - 30 * math.cos(sine / 12)),-15 - 30 * math.cos(sine / 12),-15 - 30 * math.cos(sine / 12)),.1)
RH.C0 = clerp(RH.C0, CF(1, -1, -0.01) * angles(RAD(-25 - 2.5 * SIN(sine / 12)), RAD(75), RAD(0)) * angles(RAD(-8 - 5.5 * SIN(sine / 12)), RAD(0), RAD(0)), 0.1)
LH.C0 = clerp(LH.C0, CF(-1, -0.5, -0.5) * angles(RAD(-2.5 * SIN(sine / 12)), RAD(-90), RAD(0)) * angles(RAD(-8 - 2.5 * SIN(sine / 12)), RAD(0), RAD(0)), 0.1)

elseif ModeOfGlitch == 40044 then
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.25 * math.cos(sine / 50),0 + 0.25 * math.cos(sine / 43),6 + 1 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(30 - 5 * math.cos(sine / 0.5265)),math.rad(0 - 5 * math.cos(sine / 0.25)),math.rad(0 - 5 * math.cos(sine / 0.465))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0)*angles(math.rad(10 - 15 * math.cos(sine / 12)),math.rad(0 + 2.5 * math.cos(sine / 0.123)),math.rad(5 + 2.5 * math.cos(sine / 0.6))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5,0)*angles(math.rad(10 + 15 * math.cos(sine / 12)),math.rad(0 + 2.5 * math.cos(sine / 0.664)),math.rad(-5 + 2.5 * math.cos(sine / 0.23))),.1)

elseif ModeOfGlitch == 929292 then -- Dream
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Alder',0)--right
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Navy blue',0)
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Alder"),BrickColor.new("Alder").Color)--right
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Dark blue"),Color3.new(0,0,255))
RH.C0=clerp(RH.C0,cf(1,-0.4,-0.65)*angles(math.rad(-15),math.rad(84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(-10 - 2 * math.cos(sine / 39))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1,-0.2)*angles(math.rad(-10),math.rad(-84),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * math.cos(sine / 56)),math.rad(10 + 6 * math.cos(sine / 31))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0 + 0.02 * math.cos(sine / 32),2 + 0.15 * math.cos(sine / 32))*angles(math.rad(-320 - 2 * math.cos(sine / 32)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - root.RotVelocity.Y - 5 * math.cos(sine / 8))),.1)-- rootjoint
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-13 - 2 * math.cos(sine / 37)),math.rad(0 + 1 * math.cos(sine / 58)),math.rad(0 + 2 * math.cos(sine / 53))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 + 6 * math.cos(sine / 72)),math.rad(3 - 2 * math.cos(sine / 58)),math.rad(176 + 2 * math.cos(sine / 45))),.1)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.025 * math.cos(sine / 45),0)*angles(math.rad(-15 - 7 * math.cos(sine / 66)),math.rad(4 - 3 * math.cos(sine / 59)),math.rad(-180.3 - 4 * math.cos(sine / 45))),.1)

elseif ModeOfGlitch == 9123456 then
RH.C0=clerp(RH.C0,cf(1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
LH.C0=clerp(LH.C0,cf(-1,-1 + 0.05 * math.cos(sine / 4),0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(0),math.rad(0 + 5 * math.cos(sine / 8)),math.rad(0 + 35 * math.cos(sine / 8))),.1)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,-0.05,-0.05 - 0.05 * math.cos(sine / 4))*angles(math.rad(5 + 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - root.RotVelocity.Y - 5 * math.cos(sine / 8))),.1)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(10 - 3 * math.cos(sine / 4)),math.rad(0 + root.RotVelocity.Y/1.5),math.rad(0 - hed.RotVelocity.Y*1.5 + 5 * math.cos(sine / 8))),.1)
RW.C0=clerp(RW.C0,cf(1.5,0.5,0 + 0.05 * math.cos(sine / 8))*angles(math.rad(0 - 2 * math.cos(sine / 8)),math.rad(0),math.rad(35 - 2 * math.cos(sine / 4))),.1)
LW.C0=clerp(LW.C0,cf(-1.05,0.5,-0.5)*angles(math.rad(30 + 2 * math.cos(SINE / 32)),math.rad(0),math.rad(75 + 2 * math.cos(SINE / 32))),.6)
weaponweld.C1=clerp(weaponweld.C1,cf(0 - 0.01 * math.cos(SINE / 32),1,0 - 0.01 * math.cos(SINE / 32))*angles(math.rad(0),math.rad(-90 - 0.01 * math.cos(SINE / 32)),math.rad(0)),.6)

elseif ModeOfGlitch == 10101010 then
PixelBlockX(5,0.25,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'Black',0)
PixelBlockX(5,0.25,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(90 + math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),0.65,0.65,0.65,0.0065,BrickColor.new'White',0)
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,0.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)

elseif ModeOfGlitch == 91234567 then
			local snap = math.random(1,8)
			if snap == 1 then
			tors.Neck.C0=clerp(tors.Neck.C0,necko*angles(math.rad(32 + math.random(-20,20)),math.rad(math.random(-20,20)),math.rad(math.random(-20,20))),1)
			end
				sphere23(8,"Add",ra.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(Rad(math.random(-360,360)),Rad(math.random(-360,360)),Rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Smoky grey"),BrickColor.new("Smoky grey").Color)
				sphere23(8,"Add",rl.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(Rad(math.random(-360,360)),Rad(math.random(-360,360)),Rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Smoky grey"),BrickColor.new("Smoky grey").Color)
				RH.C0=clerp(RH.C0,CF(1,-0.4,-0.5)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * Cos(sine / 56)),math.rad(-10 - 9 * Cos(sine / 51))),.1)
				LH.C0=clerp(LH.C0,CF(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(-3),math.rad(0 - 1 * Cos(sine / 56)),math.rad(10 + 7 * Cos(sine / 44))),.1)
				RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,6.5 + 0.25 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.05)
				tors.Neck.C0=clerp(tors.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
				RW.C0=clerp(RW.C0,cf(1.4,0.5 + 0.025 * math.cos(sine / 45),-0.1)*angles(math.rad(160 + 3 * math.cos(sine / 74)),math.rad(0 - 1 * math.cos(sine / 53)),math.rad(-15 + 5 * math.cos(sine / 32))),.1)
				LW.C0=clerp(LW.C0,CF(-1,0.5+.2*Cos(sine/16),-.65)*angles(math.rad(-45),0,math.rad(100)),.1)

elseif ModeOfGlitch == 699 then
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,0.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
elseif ModeOfGlitch == 102341 then -- THEORETICAL 
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,0.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
sphere2(8,"Add",rarm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("New Yeller"),BrickColor.new("New Yeller").Color)
sphere2(8,"Add",larm.CFrame*CFrame.new(0,-1,0)*CFrame.Angles(math.rad(math.random(-360,360)),math.rad(math.random(-360,360)),math.rad(math.random(-360,360))),vt(1,1,1),-0.01,0.05,-0.01,BrickColor.new("Cyan"),BrickColor.new("Cyan").Color)
sphereMK(2,-0.5,"Add",root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),8)*CFrame.Angles(math.rad(90),math.rad(0),math.rad(0)),0.5,0.5,20,-0.0075,MAINRUINCOLOR,0)
				elseif ModeOfGlitch == 6 or ModeOfGlitch == 1000000 or ModeOfGlitch == 666 then
					RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
					LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,0.5 + 0.1 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
					RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
					LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
				elseif ModeOfGlitch == 778899 or ModeOfGlitch == 688 then
					RH.C0 = clerp(RH.C0, cf(1, -0.25, -0.5) * angles(math.rad(0), math.rad(90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(-10)), 0.1)
					LH.C0 = clerp(LH.C0, cf(-1, -1, 0) * angles(math.rad(0), math.rad(-90), math.rad(0)) * angles(math.rad(-2.5), math.rad(0), math.rad(10)), 0.1)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0.5 - 0.1 * math.cos(sine / 16))*angles(math.rad(12.5),math.rad(0),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 12))),.1)
					Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(15 - 2.5 * math.cos(sine / 28)), math.rad(0), math.rad(0)), 0.1)
					RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
					LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
				elseif ModeOfGlitch == 8376532578634534 then
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,5 + 1.5 * Cos(sine / 20))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.2)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
				elseif ModeOfGlitch == 9797 or ModeOfGlitch == 8787 or ModeOfGlitch == 9123 then
					RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
					LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
					RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 - 0.15 * math.cos(sine / 47),-0.5,6.5 + 0.25 * math.cos(sine / 28))*angles(math.rad(70),math.rad(0 - root.RotVelocity.Y),math.rad(0 - root.RotVelocity.Y *4.5 + 3 * math.cos(sine / 47))),.05)
					Torso.Neck.C0=clerp(Torso.Neck.C0,necko*angles(math.rad(-17 - 5 * math.cos(sine / 52)),math.rad(0 - 3 * math.cos(sine / 37)),math.rad(0 + 2 * math.cos(sine / 78))),.2)
					RW.C0=clerp(RW.C0,cf(1.5,0.5 + 0.05 * math.cos(sine / 28),0)*angles(math.rad(-8 - 4 * math.cos(sine / 59)),math.rad(-20 + 7 * math.cos(sine / 62)),math.rad(20 + 5 * math.cos(sine / 50))),.2)
					LW.C0=clerp(LW.C0,cf(-1.5,0.5 + 0.1 * math.cos(sine / 28),0)*angles(math.rad(-8 - 3 * math.cos(sine / 55)),math.rad(20 + 8 * math.cos(sine / 67)),math.rad(-20 - 4 * math.cos(sine / 29))),.2)
elseif ModeOfGlitch == 47 then
RH.C0=clerp(RH.C0,cf(1,-0.5,-0.6)*angles(math.rad(0),math.rad(90),math.rad(0))*angles(math.rad(1.5),math.rad(0),math.rad(-20 - 5 * math.cos(sine / 34))),.2)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0))*angles(math.rad(1),math.rad(0),math.rad(20 + 2 * math.cos(sine / 38))),.2)
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0 + 0.25 * math.cos(sine / 43),0 - 0.25 * math.cos(sine / 53),6 + 2.5 * math.cos(sine / 32))*angles(math.rad(0 - 2 * math.cos(sine / 32)),math.rad(0),math.rad(0)),.1)
Torso.Neck.C0 = clerp(Torso.Neck.C0, necko * angles(math.rad(15 - 2.5 * math.cos(sine / 28)), math.rad(0), math.rad(0)), 0.1)
RW.C0=clerp(RW.C0,cf(1,0.5 + 0.025 * math.cos(sine / 45),-0.35)*angles(math.rad(6 + 3 * math.cos(sine / 74)),math.rad(-14 - 1 * math.cos(sine / 53)),math.rad(-86 + 5 * math.cos(sine / 32))),.1)
LW.C0=clerp(LW.C0,cf(-1,0.5 + 0.025 * math.cos(sine / 45),-0.55)*angles(math.rad(-20 - 5 * math.cos(sine / 73)),math.rad(23 - 2.25 * math.cos(sine / 55)),math.rad(86 - 6 * math.cos(sine / 33))),.1)
if ModeOfGlitch == 765688533321 or ModeOfGlitch == 101 or ModeOfGlitch == 090 then
sphereMK(2,-0.5,"Add",root.CFrame*CFrame.new(math.random(-5,5),math.random(-5,5),8)*CFrame.Angles(math.rad(0),math.rad(0),math.rad(0)),0.5,0.5,20,-0.0075,MAINRUINCOLOR,0)
end
end
end
end
end
end
