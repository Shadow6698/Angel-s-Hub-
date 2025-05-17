-- GUI base
local screenGui = Instance.new("ScreenGui", game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"))
screenGui.Name = "AngelsHubGui"
screenGui.ResetOnSpawn = false

-- Função para tornar GUI arrastável
local function makeDraggable(gui)
	local dragging, dragInput, dragStart, startPos

	local function update(input)
		local delta = input.Position - dragStart
		gui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end

	gui.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			dragging = true
			dragStart = input.Position
			startPos = gui.Position

			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragging = false
				end
			end)
		end
	end)

	gui.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)

	game:GetService("UserInputService").InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			update(input)
		end
	end)
end

-- Botão principal
local mainButton = Instance.new("TextButton")
mainButton.Size = UDim2.new(0, 200, 0, 50)
mainButton.Position = UDim2.new(0.1, 0, 0.1, 0)
mainButton.Text = "🥼 Angel\"s hub 🥼"
mainButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
mainButton.TextColor3 = Color3.fromRGB(0, 0, 0)
mainButton.Parent = screenGui
mainButton.Active = true
mainButton.AutoButtonColor = true

makeDraggable(mainButton)

-- Abrir biblioteca
local libraryOpen = false

mainButton.MouseButton1Click:Connect(function()
	if libraryOpen then return end
	libraryOpen = true

	local libraryFrame = Instance.new("Frame")
	libraryFrame.Size = UDim2.new(0, 700, 0, 500)
	libraryFrame.Position = UDim2.new(0.5, -350, 0.5, -250)
	libraryFrame.BackgroundColor3 = Color3.fromRGB(200, 200, 200)
	libraryFrame.Parent = screenGui

	local title = Instance.new("TextLabel")
	title.Size = UDim2.new(1, 0, 0, 50)
	title.Text = "🥼 Angel\"s hub 🥼 - Biblioteca de Scripts"
	title.TextSize = 20
	title.TextColor3 = Color3.fromRGB(0, 0, 0)
	title.BackgroundColor3 = Color3.fromRGB(150, 150, 150)
	title.Parent = libraryFrame

	local closeButton = Instance.new("TextButton")
	closeButton.Size = UDim2.new(0, 40, 0, 40)
	closeButton.Position = UDim2.new(1, -50, 0, 5)
	closeButton.Text = "X"
	closeButton.TextSize = 24
	closeButton.TextColor3 = Color3.fromRGB(255, 0, 0)
	closeButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	closeButton.Parent = libraryFrame

	closeButton.MouseButton1Click:Connect(function()
		libraryFrame:Destroy()
		libraryOpen = false
	end)

	local tabFrame = Instance.new("Frame")
	tabFrame.Size = UDim2.new(1, 0, 0, 40)
	tabFrame.Position = UDim2.new(0, 0, 0, 50)
	tabFrame.BackgroundColor3 = Color3.fromRGB(180, 180, 180)
	tabFrame.Parent = libraryFrame

	local antigosTab = Instance.new("TextButton")
	antigosTab.Size = UDim2.new(0.5, 0, 1, 0)
	antigosTab.Text = "Antigos"
	antigosTab.BackgroundColor3 = Color3.fromRGB(150, 150, 150)
	antigosTab.TextColor3 = Color3.fromRGB(0, 0, 0)
	antigosTab.Parent = tabFrame

	local novosTab = Instance.new("TextButton")
	novosTab.Size = UDim2.new(0.5, 0, 1, 0)
	novosTab.Position = UDim2.new(0.5, 0, 0, 0)
	novosTab.Text = "Novos"
	novosTab.BackgroundColor3 = Color3.fromRGB(150, 150, 150)
	novosTab.TextColor3 = Color3.fromRGB(0, 0, 0)
	novosTab.Parent = tabFrame

	local scriptListAntigos = Instance.new("ScrollingFrame")
	scriptListAntigos.Size = UDim2.new(1, -20, 1, -90)
	scriptListAntigos.Position = UDim2.new(0, 10, 0, 90)
	scriptListAntigos.CanvasSize = UDim2.new(0, 0, 0, 800)
	scriptListAntigos.ScrollBarThickness = 8
	scriptListAntigos.Parent = libraryFrame

	local scriptListNovos = scriptListAntigos:Clone()
	scriptListNovos.Parent = libraryFrame
	scriptListNovos.Visible = false

	antigosTab.MouseButton1Click:Connect(function()
		scriptListAntigos.Visible = true
		scriptListNovos.Visible = false
	end)

	novosTab.MouseButton1Click:Connect(function()
		scriptListAntigos.Visible = false
		scriptListNovos.Visible = true
	end)

	local scriptsAntigos = {
		{"Fê Emotes",         "https://scriptblox.com/raw/Brookhaven-RP-all-emotes-6849"},
		{"Ghost Hub",         "https://raw.githubusercontent.com/GhostPlayer352/Test4/main/GhostHub"},
		{"Infinite Yield",    "https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"},
		{"Kill Players",      "https://raw.githubusercontent.com/Shadow6698/Kill/main/main.txt"},
		{"Pesquisar Scripts", "https://raw.githubusercontent.com/AZYsGithub/chillz-workshop/main/ScriptSearcher"},
		{"R4D",               "https://raw.githubusercontent.com/M1ZZ001/BrookhavenR4D/main/Brookhaven%20R4D%20Script"},
		{"Rael Hub",          "https://raw.githubusercontent.com/Laelmano24/Rael-Hub/main/main.txt"},
		{"Save Servers",      "https://raw.githubusercontent.com/Shadow6698/Sabe-servers/main/Main.txt"}
	}

	local scriptsNovos = {
		{"Chaos Hub",      "https://rawscript.net/raw/Brookhaven-RP-Chaoshub-V2-35722"},
		{"Chat Logs",      "https://raw.githubusercontent.com/Shadow6698/Chat-logs/main/main.txt"},
		{"Free Gamepass",  "https://raw.githubusercontent.com/Kaitofyp/Gamepass-Script-V.1/refs/heads/main/Op%20script"},
		{"Grude Mira",     "https://raw.githubusercontent.com/Shadow6698/Aimbot/main/Main.txt"},
		{"Hub Novo",       "https://raw.githubusercontent.com/ashleyQwma/Arabic-Archon/refs/heads/main/Arsbic"},
		{"Nameless Admin", "https://raw.githubusercontent.com/FilteringEnabled/NamelessAdmin/main/Source"},
		{"Sander X",       "https://raw.githubusercontent.com/kigredns/SanderXV4.2.2/refs/heads/main/New.lua"},
		{"System Broken",  "https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"},
		{"View Itens",     "https://raw.githubusercontent.com/Shadow6698/View-itens/main/main.txt"},
		{"View Players",   "https://raw.githubusercontent.com/Shadow6698/View/main/main.txt"},
		{"Void",           "https://raw.githubusercontent.com/Shadow6698/Void-fe/main/main.txt"},
		{"Portal Gun",     "https://raw.githubusercontent.com/Shadow6698/Portal-gun-/main/Main.txt"},
		{"aimemotes",      "https://raw.githubusercontent.com/Shadow6698/Lockemotes/main/Main.txt"}
	}

	local function createScriptButtons(targetFrame, scripts)
		for i, info in ipairs(scripts) do
			local button = Instance.new("TextButton")
			button.Size = UDim2.new(1, -10, 0, 40)
			button.Position = UDim2.new(0, 5, 0, (i - 1) * 45 + 5)
			button.Text = info[1]
			button.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			button.TextColor3 = Color3.fromRGB(0, 0, 0)
			button.Parent = targetFrame

			button.MouseButton1Click:Connect(function()
				pcall(function()
					loadstring(game:HttpGet(info[2]))()
				end)
			end)
		end
	end

	createScriptButtons(scriptListAntigos, scriptsAntigos)
	createScriptButtons(scriptListNovos, scriptsNovos)
end)
