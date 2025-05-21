-- Carregar biblioteca Fluent
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local version = "2"

-- Criar janela principal (já visível)
local Window = Fluent:CreateWindow({
    Title = "Angels hub " .. version,
    SubTitle = "by nightmare",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true,
    Theme = "Dark",
    Visible = true, -- janela já aparece
})

-- Criar abas
local Tabs = {
    Creditos = Window:AddTab({ Title = "Créditos", Icon = "heart" }),
    Scripts = Window:AddTab({ Title = "Scripts", Icon = "code" })
}

-- Créditos
Tabs.Creditos:AddParagraph({
    Title = "Créditos",
    Content = "Script feito por:\nNightmare"
})

-- Scripts válidos
local scripts = {
    {"Fê Emotes",         "https://scriptblox.com/raw/Brookhaven-RP-all-emotes-6849"},
    {"Ghost Hub",         "https://raw.githubusercontent.com/GhostPlayer352/Test4/main/GhostHub"},
    {"Infinite Yield",    "https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"},
    {"Kill Players",      "https://raw.githubusercontent.com/Shadow6698/Kill/main/main.txt"},
    {"Pesquisar Scripts", "https://raw.githubusercontent.com/AZYsGithub/chillz-workshop/main/ScriptSearcher"},
    {"R4D",               "https://raw.githubusercontent.com/M1ZZ001/BrookhavenR4D/main/Brookhaven%20R4D%20Script"},
    {"Rael Hub",          "https://raw.githubusercontent.com/Laelmano24/Rael-Hub/main/main.txt"},
    {"Save Servers",      "https://raw.githubusercontent.com/Shadow6698/Sabe-servers/main/Main.txt"},
    {"Nameless Admin",    "https://raw.githubusercontent.com/FilteringEnabled/NamelessAdmin/main/Source"},
    {"Sander X",          "https://raw.githubusercontent.com/kigredns/SanderXV4.2.2/refs/heads/main/New.lua"},
    {"System Broken",     "https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"},
    {"View Itens",        "https://raw.githubusercontent.com/Shadow6698/View-itens/main/main.txt"},
    {"View Players",      "https://raw.githubusercontent.com/Shadow6698/View/main/main.txt"},
    {"Void",              "https://raw.githubusercontent.com/Shadow6698/Void-fe/main/main.txt"},
    {"Portal Gun",        "https://raw.githubusercontent.com/Shadow6698/Portal-gun-/main/Main.txt"},
    {"aimemotes",         "https://raw.githubusercontent.com/Shadow6698/Lockemotes/main/Main.txt"}
}

-- Adicionar botões para cada script
for _, script in ipairs(scripts) do
    Tabs.Scripts:AddButton({
        Title = script[1],
        Description = "Clique para executar",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Notificação ao abrir
Fluent:Notify({
    Title = "Angel Hub",
    Content = "Script carregado com sucesso!",
    Duration = 5
})
