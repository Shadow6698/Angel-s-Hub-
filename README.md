-- Carregar biblioteca Fluent
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local version = "2.0"

-- Criar janela principal
local Window = Fluent:CreateWindow({
    Title = "Angels hub " .. version,
    SubTitle = "by nightmare",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true,
    Theme = "Dark",
    Visible = true,
})

-- Criar abas
local Tabs = {
    Creditos = Window:AddTab({ Title = "Créditos", Icon = "heart" }),
    Scripts = Window:AddTab({ Title = "Scripts", Icon = "code" }),
    DeadRealls = Window:AddTab({ Title = "Dead Realls [Trilhos Mortos]", Icon = "skull" }),
    Comandos = Window:AddTab({ Title = "Scripts de Comandos", Icon = "terminal" }),
    BloxFruits = Window:AddTab({ Title = "Blox Fruits", Icon = "swords" }),
    Outros = Window:AddTab({ Title = "Outros", Icon = "grid" }),
    Brookhaven = Window:AddTab({ Title = "Brookhaven", Icon = "home" }),
    ScriptsExtras = Window:AddTab({ Title = "Scripts Extras", Icon = "zap" }),
    Plugins = Window:AddTab({ Title = "Plugins", Icon = "plug" })
}

-- Créditos
Tabs.Creditos:AddParagraph({
    Title = "Créditos",
    Content = "Script feito por:\nNightmare e julia"
})

-- Scripts principais
local scripts = {
    {"Fê Emotes",       "https://scriptblox.com/raw/Brookhaven-RP-all-emotes-6849"},
    {"Ghost Hub",       "https://raw.githubusercontent.com/GhostPlayer352/Test4/main/GhostHub"},
    {"Infinite Yield",  "https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"},
    {"Kill Players",    "https://raw.githubusercontent.com/Shadow6698/Kill/main/main.txt"},
    {"Pesquisar Scripts", "https://raw.githubusercontent.com/AZYsGithub/chillz-workshop/main/ScriptSearcher"},
    {"R4D",             "https://raw.githubusercontent.com/M1ZZ001/BrookhavenR4D/main/Brookhaven%20R4D%20Script"},
    {"Rael Hub",        "https://raw.githubusercontent.com/Laelmano24/Rael-Hub/main/main.txt"},
    {"Save Servers",    "https://raw.githubusercontent.com/Shadow6698/Sabe-servers/main/Main.txt"},
    {"Nameless Admin",  "https://raw.githubusercontent.com/ltseverydayyou/Nameless-Admin/main/Source.lua"},
    {"Sander X",        "https://raw.githubusercontent.com/kigredns/SanderXV4.2.2/refs/heads/main/New.lua"},
    {"System Broken",   "https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"},
    {"View Itens",      "https://raw.githubusercontent.com/Shadow6698/View-itens/main/main.txt"},
    {"View Players",    "https://raw.githubusercontent.com/Shadow6698/View/main/main.txt"},
    {"Void",            "https://raw.githubusercontent.com/Shadow6698/Void-fe/main/main.txt"},
    {"Portal Gun",      "https://raw.githubusercontent.com/Shadow6698/Portal-gun-/main/Main.txt"},
    {"aimemotes",       "https://raw.githubusercontent.com/Shadow6698/Lockemotes/main/Main.txt"},
    {"Tiger Hub",       "https://raw.githubusercontent.com/balintTheDevX/Tiger-X-V3/main/Tiger%20X%20V3.5%20Fixed"},
    {"Aimbot",          "https://pastebin.com/raw/qtZt0Nzb"},
    {"Hub Universal",   "https://raw.githubusercontent.com/scripthubekitten/SCRIPTHUBV3/main/SCRIPTHUBV3"},
    {"Salvatore",       "https://raw.githubusercontent.com/H20CalibreYT/Salvatore/main/loader.lua", "Pode conter sistema de chave (key system)"},
    {"Draw FE",         "https://raw.githubusercontent.com/Affexter/Programs/refs/heads/main/scripts/tooldrawFE.lua"},
    {"Multiplicar Tools", "https://raw.githubusercontent.com/kigredns/NeonDuplicator/refs/heads/main/Script.lua"},
    {"Chaos Hub",       "https://raw.githubusercontent.com/Luscaa22/Calabocaa/refs/heads/main/ChaosHub"},
}

for _, script in ipairs(scripts) do
    Tabs.Scripts:AddButton({
        Title = script[1],
        Description = script[3] or "Clique para executar",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Scripts de comandos/admins
local comandos = {
    {"Nameless Admin", "https://raw.githubusercontent.com/ltseverydayyou/Nameless-Admin/main/Source.lua"},
    {"Infinite Yield", "https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"},
    {"Reviz Admin", "https://pastebin.com/raw/Caniwq2N"},
    {"CMD-X", "https://raw.githubusercontent.com/CMD-X/CMD-X/master/Source"},
    {"Fates Admin", "https://raw.githubusercontent.com/fatesc/fates-admin/main/main.lua"},
}

for _, script in ipairs(comandos) do
    Tabs.Comandos:AddButton({
        Title = script[1],
        Description = "Painel/Admin de comandos",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Aba Dead Realls com 5 hubs
Tabs.DeadRealls:AddButton({
    Title = "Hub 1",
    Description = "Script com chave (key system)",
    Callback = function()
        local script_key = "PASTEKEYHERE"
        (loadstring or load)(game:HttpGet("https://getnative.cc/script/loader"))()
    end
})

Tabs.DeadRealls:AddButton({
    Title = "Hub 2",
    Description = "Than Hub v1",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/thantzy/thanhub/refs/heads/main/thanv1"))()
    end
})

Tabs.DeadRealls:AddButton({
    Title = "Hub 3",
    Description = "The Fastest Bond Stealer",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/DonjoScripts/Public-Scripts/refs/heads/Slap-Battles/TheFastestBondStealer.lua'))()
    end
})

Tabs.DeadRealls:AddButton({
    Title = "Hub 4",
    Description = "Tbao Hub Dead Rails",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/tbao143/thaibao/refs/heads/main/TbaoHubDeadRails"))()
    end
})

Tabs.DeadRealls:AddButton({
    Title = "Hub 5",
    Description = "FernHub DeadRailsFarm",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Mrpopcatfrombupge/FernHub/refs/heads/main/DeadRailsFarm", true))()
    end
})

-- Scripts para Blox Fruits
local bloxFruitsScripts = {
    {"Zen Hub", "https://raw.githubusercontent.com/Kaizenofficiall/ZenHub/main/Main"},
    {"Hoho Hub", "https://raw.githubusercontent.com/acsu123/HOHO_H/main/HOHOHub.lua", "Pode ter key system"},
    {"Mukuro Hub", "https://raw.githubusercontent.com/xQuartyx/DonateMe/main/ScriptLoader"},
    {"BlxWare Hub", "https://raw.githubusercontent.com/BLXWareBLX/BLXWare-HUB/main/Main.lua"},
    {"Thunder Z Hub", "https://raw.githubusercontent.com/ThunderZ-05/HUB/main/BloxFruits"},
    {"Neva Hub", "https://raw.githubusercontent.com/DevNeva/NevaHub/main/NevaHubLoader.lua"}
}

for _, script in ipairs(bloxFruitsScripts) do
    Tabs.BloxFruits:AddButton({
        Title = script[1],
        Description = script[3] or "Clique para executar",
        Callback = function()
            loadstring(game:HttpGet(script[2]))()
        end
    })
end

-- Aba Outros
Tabs.Outros:AddButton({
    Title = "Angel Executor",
    Description = "Executor Angel incorporado",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Executor-script/main/Main.txt"))()
    end
})

Tabs.Outros:AddButton({
    Title = "Sky Hub",
    Description = "Sky Hub FE Trolling GUI",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/yofriendfromschool1/Sky-Hub/main/FE%20Trolling%20GUI.luau"))()
    end
})

-- Aba Brookhaven
Tabs.Brookhaven:AddButton({
    Title = "Gumball Hub",
    Description = "Gumball Hub Brookhaven",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/JaozinScripts/Gumball-Hub/refs/heads/main/GumballHubRetorn2.1.1.1.lua"))()
    end
})

Tabs.Brookhaven:AddButton({
    Title = "Sander X",
    Description = "Sander X v3.30",
    Callback = function()
        loadstring(game:HttpGet(('https://raw.githubusercontent.com/sXPiterXs1111/Sanderxv3.30/main/sanderx3.30')))()
    end
})

Tabs.Brookhaven:AddButton({
    Title = "Chaos Hub",
    Description = "Chaos Hub Brookhaven",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Luscaa22/Calabocaa/refs/heads/main/ChaosHub"))()
    end
})

-- Scripts Extras
Tabs.ScriptsExtras:AddButton({
    Title = "Anti Lag Universal",
    Description = "Reduz o lag no jogo",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Anti-Lag/main/Main.txt"))()
    end
})

Tabs.ScriptsExtras:AddButton({
    Title = "Item Finder",
    Description = "Localizador de itens FE",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Item-Finder/main/Main.txt"))()
    end
})

-- Plugins (novos adicionados)
Tabs.Plugins:AddButton({
    Title = "Script Anti Crash",
    Description = "Previne bugs que causam crash",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Script-Anti-Crash/main/Main.txt"))()
    end
})

Tabs.Plugins:AddButton({
    Title = "Script Anti Reset",
    Description = "Impede que você resete",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Shadow6698/Script-Anti-Reset/main/Main.txt"))()
    end
})
