print('Yes Sam Kak MakMak ')
local placeId = game.PlaceId
if placeId == 2753915549 or placeId == 4442272183 or placeId == 7449423635 then
    BF = true
elseif placeId == 3237168 then
    OPL = true
elseif placeId == 914010731 then
    RO = true
elseif placeId == 6299805723 then
    AFS = true
elseif placeId == 4520749081 or placeId == 6381829480 or placeId == 5931540094 then
	KL = true
elseif placeId == 4042427666 then
    ANS = true
elseif placeId == 2809202155 then
    YBA = true
    print("\n game not support")
end
spawn(function()
	while wait() do 
		print("JayKung#8973 ")
	end
end)
if BF then
	repeat wait() until game:IsLoaded()
	if getgenv().Setting then else
		getgenv().Setting = {
			["Join Team"] = "Pirate", -- "Pirate","Marine"
			["Auto Farm Level"] = false,
		
			-- Setting etc
			["Select Weapon"] = "",
			["Auto Rejoin"] = false,
		
			-- Old World
			["Auto New World"] = false,
		
			-- New World
			["Auto Factory"] = false,
			["Auto third World"] = false,
		
			-- New Fighting Styles & etc
			["Auto Superhuman"] = false,
			["Auto Superhuman [Full]"] = false,
			["Auto Death Step"] = false,
			["Auto Dragon Talon"] = false,
			["Auto Electric Clow"] = false,
			["Auto Buy Legendary Sword"] = false,
			["Auto Buy Legendary Sword Hop"] = false,
			["Auto Buy Enhancement"] = false,
			["Auto Farm Select Boss Hop"] = false,
		
			-- Auto Stats
			["Melee"] = false,
			["Defense"] = false,
			["Sword"] = false,
			["Gun"] = false,
			["Demon Fruit"] = false,
		
			-- Use Candy
			["Auto Buy Exp x2"] = false,
			["Auto Buy Exp x2[ Exp Expire ]"] = false,
	
			-- Players
			["Bounty Hop"] = false
		}
	end
	
	if not game:IsLoaded() then game.Loaded:Wait() end
	repeat wait() until game.Players
	repeat wait() until game.Players.LocalPlayer
	repeat wait() until game.ReplicatedStorage
	repeat wait() until game.ReplicatedStorage:FindFirstChild("Remotes");
	repeat wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui");
	repeat wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");
	repeat wait()
		if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
			if getgenv().Setting["Join Team"] == "Pirate" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			elseif getgenv().Setting["Join Team"] == "Marine" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			else
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			end
		end
	until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded() 
	
	wait(1)
	
	if game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui") then game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui"):Destroy() end
	local library = {RainbowColorValue = 0, HueSelectionPosition = 0}
	local PresetColor = Color3.fromRGB(255, 0, 0)
	local UserInputService = game:GetService("UserInputService")
	local TweenService = game:GetService("TweenService")
	local RunService = game:GetService("RunService")
	local LocalPlayer = game:GetService("Players").LocalPlayer
	local MyNameIs = LocalPlayer.Name
	local Mouse = LocalPlayer:GetMouse()
	local CloseBind = Enum.KeyCode.RightControl
	
	local ScreenGui = Instance.new("ScreenGui")
	local TabButtonLayout = Instance.new("UIListLayout")
	
	ScreenGui.Name = "Voice Chat Ui"
	ScreenGui.Parent = game.CoreGui.RobloxGui
	local uitoggled = false
	UserInputService.InputBegan:Connect(function(io, p)
		if io.KeyCode == Enum.KeyCode.RightControl then
			if uitoggled == false then
				ScreenGui.Enabled = false
				uitoggled = true
			else
				ScreenGui.Enabled = true
				uitoggled = false
			end
		end
	end)
	
	coroutine.wrap(
		function()
			while wait() do
				library.RainbowColorValue = library.RainbowColorValue + 1 / 255
				library.HueSelectionPosition = library.HueSelectionPosition + 1
	
				if library.RainbowColorValue >= 1 then
					library.RainbowColorValue = 0
				end
	
				if library.HueSelectionPosition == 80 then
					library.HueSelectionPosition = 0
				end
			end
		end
	)()
	
	local function MakeDraggable(topbarobject, object)
		local Dragging = nil
		local DragInput = nil
		local DragStart = nil
		local StartPosition = nil
	
		local function Update(input)
			local Delta = input.Position - DragStart
			local pos =
				UDim2.new(
					StartPosition.X.Scale,
					StartPosition.X.Offset + Delta.X,
					StartPosition.Y.Scale,
					StartPosition.Y.Offset + Delta.Y
				)
			object.Position = pos
		end
	
		topbarobject.InputBegan:Connect(
			function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
					Dragging = true
					DragStart = input.Position
					StartPosition = object.Position
	
					input.Changed:Connect(
						function()
							if input.UserInputState == Enum.UserInputState.End then
								Dragging = false
							end
						end
					)
				end
			end
		)
	
		topbarobject.InputChanged:Connect(
			function(input)
				if
					input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch
				then
					DragInput = input
				end
			end
		)
	
		UserInputService.InputChanged:Connect(
			function(input)
				if input == DragInput and Dragging then
					Update(input)
				end
			end
		)
	end
	
	local function RippleEffect(object)
		spawn(function()
			local Ripple = Instance.new("ImageLabel")
			Ripple.Name = "Ripple"
			Ripple.Parent = object
			Ripple.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Ripple.BackgroundTransparency = 1.000
			Ripple.ZIndex = 8
			Ripple.Image = "rbxassetid://2708891598"
			Ripple.ImageTransparency = 0.800
			Ripple.ScaleType = Enum.ScaleType.Fit
			Ripple.Position = UDim2.new((Mouse.X - Ripple.AbsolutePosition.X) / object.AbsoluteSize.X, 0, (Mouse.Y - Ripple.AbsolutePosition.Y) / object.AbsoluteSize.Y, 0)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Position = UDim2.new(-5.5, 0, -15, 0), Size = UDim2.new(12, 0, 30, 0)}):Play()
			wait(0.5)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageTransparency = 1}):Play()
			wait(0.5)
			Ripple:Destroy()
		end)
	end
	
	function library:Window(name,game)
		if getgenv().Theme ~= nil then
			ColorII = getgenv().Theme.Tab.Color
	
			ColorIII = getgenv().Theme.Line.LeftColor
			ColorIIII = getgenv().Theme.Line.RightColor
	
			ColorIIIII = getgenv().Theme.Toggle.LeftColor
			ColorIIIIII = getgenv().Theme.Toggle.RightColor
	
			ColorIIIIIII = getgenv().Theme.Slider.LeftColor
			ColorIIIIIIII = getgenv().Theme.Slider.RightColor
		else
			ColorII = Color3.fromRGB(255, 0, 0)
	
			ColorIII = Color3.fromRGB(255, 0, 0)
			ColorIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIIIII = Color3.fromRGB(0, 0, 255)
		end
	
		local Main = Instance.new("Frame")
		local ShowName = Instance.new("TextLabel")
		local MainUICorner = Instance.new("UICorner")
		local TopMain = Instance.new("Frame")
		local TopMainUICorner = Instance.new("UICorner")
		local TopMainLine = Instance.new("Frame")
		local NameHub = Instance.new("TextLabel")
		local Toggleui = Instance.new("TextLabel")
		local HideTab = Instance.new("ImageButton")
		local SizeFullSection = Instance.new("Frame")
	
		Main.Name = "Main"
		Main.Parent = ScreenGui
		Main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
		Main.ClipsDescendants = true
		Main.Position = UDim2.new(0.5, -325, 0.5, -175)
		Main.Size = UDim2.new(0, 650, 0, 425)
	
		MainUICorner.Name = "MainUICorner"
		MainUICorner.Parent = Main
	
		TopMain.Name = "TopMain"
		TopMain.Parent = Main
		TopMain.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMain.Size = UDim2.new(0, 650, 0, 30)
	
		MakeDraggable(TopMain, Main)
	
		TopMainUICorner.Name = "TopMainUICorner"
		TopMainUICorner.Parent = TopMain
	
		TopMainLine.Name = "TopMainLine"
		TopMainLine.Parent = TopMain
		TopMainLine.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMainLine.BorderSizePixel = 0
		TopMainLine.Position = UDim2.new(0, 0, 0.833333313, 0)
		TopMainLine.Size = UDim2.new(1, 0, 0, 5)
	
		ShowName.Name = "MyName"
		ShowName.Parent = Main
		ShowName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ShowName.BackgroundTransparency = 1.000
		ShowName.Position = UDim2.ne
