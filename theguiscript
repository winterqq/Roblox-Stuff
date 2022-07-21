-- Stop Looking At My Messy Code
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({Name = "Mow The Lawn", HidePremium = false, SaveConfig = true, ConfigFolder = "MTL"})
local Tab = Window:MakeTab({Name = "Auto Farm",	Icon = "rbxassetid://4483345998",PremiumOnly = false})
local Section = Tab:AddSection({Name = "Grass"})

local z1 = "1"
local v1 = false
local v2 = false
local v3 = false
local p1 = 1
local pu1 = false
local pu2 = false
local pu3 = false
local e1 = ""

Tab:AddParagraph("Info","If auto mow isn't working, teleport to the zone to load in the grass. After having auto mow on for a while it will take a bit to stop. You can only auto mow in zones you have unlocked!")
Tab:AddDropdown({Name = "Choose Current Zone",Default = "1",Options = {"1", "2", "3", "4", "5", "6", "7", "8", "9", "10"},Callback = function(ZoneValue)
	z1 = ZoneValue
	print(z1)
end 
})
Tab:AddToggle({Name = "Auto Mow",Default = false,Callback = function(Value)
	v1 = Value
    while v1 do
        wait()
		game:GetService("ReplicatedStorage").Remotes.Game.ClientMowGrass:FireServer(z1)
        end
    end
})
Tab:AddToggle({Name = "Auto Refuel",Default = false,Callback = function(Value)
	v3 = Value
    while v3 do
		game:GetService("ReplicatedStorage").Remotes.Game.ClientToggleUseGasStation:FireServer(workspace.Map.Zones:FindFirstChild(z1).GasStation.GasPumps, true)
		wait(5)
        end
    end
})

local Section = Tab:AddSection({Name = "Money"})
Tab:AddParagraph("Info","Spam Gift requires you to play for at least 5 minutes, also very laggy. TPing to the end will make you most money when spam gifting.")
Tab:AddToggle({Name = "Spam Gift",Default = false,Callback = function(Value)
	v2 = Value
    while v2 do
        wait()
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(1)
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(2)
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(3)
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(4)
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(5)
		game:GetService("ReplicatedStorage").Remotes.Shop.ClientClaimPlaytimeGift:FireServer(6)
        end
    end
})
Tab:AddButton({Name = "TP to end",Callback = function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Zones[10].EggPurchaseStand.Eggs["Lucky Egg"]["Meshes/huevitos_pasted__pasted__pasted__pasted__pSphere3"].CFrame
end   
})
local Tab = Window:MakeTab({Name = "Pets",	Icon = "rbxassetid://4483345998",PremiumOnly = false})
local Section = Tab:AddSection({Name = "Pet Upgrades"})
local CoolLabel = Tab:AddLabel("Pet Number Selected: "..p1)
Tab:AddTextbox({
	Name = "Pet Number",
	Default = p1,
	TextDisappear = true,
	Callback = function(PetValue)
		p1 = PetValue
		p1 = tonumber(p1)
		print(p1)
		CoolLabel:Set("Pet Number Selected: "..p1)
	end  
})
Tab:AddToggle({Name = "Upgrade AttacksPerSecond",Default = false,Callback = function(APSValue)
	pu1 = APSValue
    while pu1 do
        wait()
		print(p1)
		game:GetService("ReplicatedStorage").Remotes.Game.Pet.ClientUpgradePetStat:InvokeServer(p1, "AttacksPerSecond")
        end
    end
})
Tab:AddToggle({Name = "Upgrade WalkSpeed",Default = false,Callback = function(WSValue)
	pu2 = WSValue
    while pu2 do
        wait()
		game:GetService("ReplicatedStorage").Remotes.Game.Pet.ClientUpgradePetStat:InvokeServer(p1, "WalkSpeed")
        end
    end
})
Tab:AddToggle({Name = "Upgrade Damage",Default = false,Callback = function(UDValue)
	pu3 = UDValue
    while pu3 do
        wait()
		game:GetService("ReplicatedStorage").Remotes.Game.Pet.ClientUpgradePetStat:InvokeServer(p1, "Damage")
        end
    end
})

local Section = Tab:AddSection({Name = "Eggs"})
Tab:AddDropdown({Name = "Select Egg",Default = "1",Options = {"Ant Egg", "Striped Egg", "Painted Egg", "Cute Egg", "Flying Egg", "Frozen Egg", "Techno Egg", "Golden Egg", "Cloudy Egg", "Purple Ore Egg", "Lucky Egg", "Magma Egg"},Callback = function(EggValue)
	e1 = EggValue
	print(e1)
end
})
Tab:AddButton({Name = "Purchase Egg",Callback = function()
    game:GetService("ReplicatedStorage").Remotes.Shop.ClientBuyEgg:InvokeServer(e1)
end    
})
OrionLib:Init()
