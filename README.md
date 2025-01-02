local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/shlexware/Orion/main/source"))()

local KeyWindow = OrionLib:MakeWindow({Name = "Key System", HidePremium = false, SaveConfig = true, ConfigFolder = "KeyConfig"})
local KeyTab = KeyWindow:MakeTab({Name = "Key", Icon = "rbxassetid://4483345998", PremiumOnly = false})

local attempts = 0

KeyTab:AddTextbox({
    Name = "Insira a Key",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        if Value == "c00lkid" then
            print("Key correta!")
            KeyWindow:Destroy()
            local Window = OrionLib:MakeWindow({Name = "Xfocos Hub", HidePremium = false, SaveConfig = true, ConfigFolder = "XfocosHubConfig"})

            for i = 1, 50 do
                local Tab = Window:MakeTab({Name = "Aba " .. i, Icon = "rbxassetid://4483345998", PremiumOnly = false})
                for j = 1, 10 do
                    Tab:AddButton({
                        Name = "Opção " .. j,
                        Callback = function()
                            print("Opção " .. j .. " da Aba " .. i .. " foi clicada!")
                        end
                    })
                end
            end

            local DiscordTab = Window:MakeTab({Name = "Discord", Icon = "rbxassetid://4483345998", PremiumOnly = false})
            DiscordTab:AddButton({
                Name = "Copiar Discord",
                Callback = function()
                    setclipboard("https://discord.gg/aaDHdjdB")
                    print("Link do Discord copiado!")
                end
            })

            local TrollTab = Window:MakeTab({Name = "Troll", Icon = "rbxassetid://4483345998", PremiumOnly = false})
            TrollTab:AddButton({
                Name = "Cleitin Hub",
                Callback = function()
                    loadstring(game:HttpGet("https://rawscripts.net/raw/Brookhaven-RP-CLEITI6966-HUBS-22818"))()
                end
            })

            local PremiumTab = Window:MakeTab({Name = "Premium", Icon = "rbxassetid://4483345998", PremiumOnly = false})
            PremiumTab:AddButton({
                Name = "Templarios Brook (OP)",
                Callback = function()
                    loadstring(game:HttpGet("https://raw.githubusercontent.com/TemplariosScriptS2/TemplariosHubNewUpdate1/main/TemplariosHubNewUpdate1.txt"))()
                end
            })
            PremiumTab:AddButton({
                Name = "BLUE Lock Rivals",
                Callback = function()
                    loadstring(game:HttpGet("https://raw.githubusercontent.com/SkibidiCen/MainMenu/main/Code"))()
                end
            })
            PremiumTab:AddButton({
                Name = "Alexcirer Universal",
                Callback = function()
                    loadstring(game:HttpGet("https://raw.githubusercontent.com/Alexcirer/Alexcirer/refs/heads/main/Station"))()
                end
            })
        else
            attempts = attempts + 1
            local waitTime = attempts * 5
            print("Key incorreta! Bloqueado por " .. waitTime .. " segundos.")
            wait(waitTime)
        end
    end
})

KeyTab:AddButton({
    Name = "Iniciar",
    Callback = function()
        if attempts == 0 then
            print("Insira a Key primeiro.")
        end
    end
})

