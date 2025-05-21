-- Carregar a biblioteca Fluent
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Fluent/master/Addons/InterfaceManager.lua"))()

local version = "2" -- Versão manual

-- Criar Janela Principal (inicialmente invisível)
local Window = Fluent:CreateWindow({
    Title = "Angels hub " .. version,
    SubTitle = "by nightmare",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true,
    Theme = "Dark",
    Visible = false, -- começa escondido
})

-- Criar abas
local Tabs = {
    Creditos = Window:AddTab({ Title = "Créditos", Icon = "heart" }),
    Scripts = Window:AddTab({ Title = "Scripts", Icon = "code" })
}

-- Adicionar créditos
Tabs.Creditos:AddParagraph({
    Title = "Créditos",
    Content = "Script feito por:\nNightmare"
})

local scripts = {
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
    -- Removi os scripts solicitados
    {"Nameless Admin", "https://raw.githubusercontent.com/FilteringEnabled/NamelessAdmin/main/Source"},
    {"Sander X",       "https://raw.githubusercontent.com/kigredns/SanderXV4.2.2/refs/heads/main/New.lua"},
    {"System Broken",  "https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"},
    {"View Itens",     "https://raw.githubusercontent.com/Shadow6698/View-itens/main/main.txt"},
    {"View Players",   "https://raw.githubusercontent.com/Shadow6698/View/main/main.txt"},
    {"Void",           "https://raw.githubusercontent.com/Shadow6698/Void-fe/main/main.txt"},
    {"Portal Gun",     "https://raw.githubusercontent.com/Shadow6698/Portal-gun-/main/Main.txt"},
    {"aimemotes",      "https://raw.githubusercontent.com/Shadow6698/Lockemotes/main/Main.txt"}
}

-- Adicionar botões para scripts antigos
for _, script in ipairs(scripts) do
    Tabs.Scripts:AddButton({
        Title = script[1],
        Description = "Clique para executar",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Adicionar botões para scripts novos
for _, script in ipairs(scriptsNovos) do
    Tabs.Scripts:AddButton({
        Title = script[1],
        Description = "Clique para executar",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Integrar com Add-ons
SaveManager:SetLibrary(Fluent)
InterfaceManager:SetLibrary(Fluent)

-- Selecionar a aba de créditos por padrão
Window:SelectTab(1)

-- Notificação de carregamento
Fluent:Notify({
    Title = "Fluent",
    Content = "Script carregado com sucesso!"
})

-- O hub inicia invisível, sem botão para abrir
