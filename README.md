-- Carregar biblioteca Fluent
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local version = "2"

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
}

-- Créditos
Tabs.Creditos:AddParagraph({
    Title = "Créditos",
    Content = "Script feito por:\nNightmare"
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
    {"Nameless Admin",  "https://raw.githubusercontent.com/FilteringEnabled/NamelessAdmin/main/Source"},
    {"Sander X",        "https://raw.githubusercontent.com/kigredns/SanderXV4.2.2/refs/heads/main/New.lua"},
    {"System Broken",   "https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"},
    {"View Itens",      "https://raw.githubusercontent.com/Shadow6698/View-itens/main/main.txt"},
    {"View Players",    "https://raw.githubusercontent.com/Shadow6698/View/main/main.txt"},
    {"Void",            "https://raw.githubusercontent.com/Shadow6698/Void-fe/main/main.txt"},
    {"Portal Gun",      "https://raw.githubusercontent.com/Shadow6698/Portal-gun-/main/Main.txt"},
    {"aimemotes",       "https://raw.githubusercontent.com/Shadow6698/Lockemotes/main/Main.txt"},
    {"Tiger Hub",       "https://raw.githubusercontent.com/balintTheDevX/Tiger-X-V3/main/Tiger%20X%20V3.5%20Fixed"},
    {"Aimbot",          "https://pastebin.com/raw/qtZt0Nzb"},
    {"Hub Universal",   "https://raw.githubusercontent.com/scripthubekitten/SCRIPTHUBV3/main/SCRIPTHUBV3"}
}

for _, script in ipairs(scripts) do
    Tabs.Scripts:AddButton({
        Title = script[1],
        Description = "Clique para executar",
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
