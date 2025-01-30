-- Icon personalizado
local ScreenGui = Instance.new("ScreenGui")
local ImageButton = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

-- Propriedades
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton.Parent = ScreenGui
ImageButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageButton.BorderSizePixel = 0
ImageButton.Position = UDim2.new(0.005, 0, 0.010, 0)
ImageButton.Size = UDim2.new(0, 45, 0, 45)
ImageButton.Image = "rbxassetid://139166819013498" -- Id da icon aqui

UICorner.Parent = ImageButton

-- FunÃ§Ã£o para tornar o botÃ£o arrastÃ¡vel
local UIS = game:GetService("UserInputService")
local dragging, dragInput, startPos, startMousePos
local hasMoved = false

ImageButton.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = true
        hasMoved = false
        startPos = ImageButton.Position
        startMousePos = UIS:GetMouseLocation()

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

ImageButton.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        dragInput = input
    end
end)

UIS.InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        local delta = UIS:GetMouseLocation() - startMousePos
        if math.abs(delta.X) > 5 or math.abs(delta.Y) > 5 then 
            hasMoved = true
        end
        ImageButton.Position = UDim2.new(
            startPos.X.Scale, startPos.X.Offset + delta.X,
            startPos.Y.Scale, startPos.Y.Offset + delta.Y
        )
    end
end)

ImageButton.MouseButton1Down:Connect(function()
    task.wait(0.1) -- Isso serve pro icone nao abrir quando a pessoa for arrastar ele, mexe aqui nÃ£o
    if not hasMoved then
        game:GetService("VirtualInputManager"):SendKeyEvent(true, Enum.KeyCode.LeftControl, false, game)
    end
end)

local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local MarketplaceService = game:GetService("MarketplaceService")
local PlaceId = game.PlaceId
local ProductInfo = MarketplaceService:GetProductInfo(PlaceId)
local GameName = ProductInfo.Name

Fluent:Notify({ Title = "Script executado com sucesso", Content = "VocÃª esta usando Mender_hub" })

local Window = Fluent:CreateWindow({
    Title = "Mender_hub",
    SubTitle = "-- " .. GameName,
    TabWidth = 102,
    Size = UDim2.fromOffset(450, 320),
    Acrylic = false,
    Theme = "Amethyst",
    MinimizeKey = Enum.KeyCode.LeftControl
})
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "" })    
}
Tabs.Main:AddParagraph({
        Title = "Esse script esta em update",
        Content = "Script atualizando "
    })

local Tabs = {
    Main= Window:AddTab({ Title = "| Farm", Icon = "rbxassetid://18831424669" }),
     Tp = Window:AddTab({ Title = "| Tp", Icon = "rbxassetid://18831424669" })
}
local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Auto energy", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
    --remote
    
game:GetService("ReplicatedStorage"):WaitForChild("Click"):FireServer()
game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Sasuke"):FireServer()
            wait(0)
           end
        end)

local Tabs = {
    Main= Window:AddTab({ Title = "| Hath", Icon = "rbxassetid://18831424669" })
}
local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Fast egg Naruto", Default = false})

AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Naruyu Egg"
}

game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Eclicked"):FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Fast egg Piece", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Pyocy Egg"
}

game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Eclicked"):FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Fast egg Demon", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Sleyer Egg"
}

game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Eclicked"):FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Fast egg City mortal", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Sword Egg"
}

game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Eclicked"):FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Naruto", {Title = "Fast egg Clover", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
local args = {
    [1] = "Clovery Egg"
}

game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvents"):WaitForChild("Eclicked"):FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Fast egg", {Title = "Fast egg DBZ", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
    local args = {
        [1] = "DBZ Egg"
    }
    game:GetService("ReplicatedStorage").RemoteEvents.Eclicked:FireServer(unpack(args))
        wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Fast egg", {Title = "Fast egg Crazy village", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
    local args = {
        [1] = "CrazyVillageEgg"
    }
    game:GetService("ReplicatedStorage").RemoteEvents.Eclicked:FireServer(unpack(args))
      wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Fast egg", {Title = "Fast egg cursed", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
--remote
    local args = {
        [1] = "Cursed Egg"
    }
    game:GetService("ReplicatedStorage").RemoteEvents.Eclicked:FireServer(unpack(args))
      wait(0)
    end
end)

local AutoClick= Tabs.Main:AddToggle("Fast egg", {Title = "Fast egg one hero", Default = false})
AutoClick:OnChanged(function()
    while AutoClick.Value do
    local args = {
        [1] = "OneHeroEgg"
    }
    game:GetService("ReplicatedStorage").RemoteEvents.Eclicked:FireServer(unpack(args))
      wait(0)
    end
end)

Main:AddButton({
    Title = "Naruto",
    Callback = function()
--naruto
local targetCFrame = CFrame.new(-726.696594, 13.8924885, -970.772095, 
    -4.30345535e-05, 0.984805167, 0.173663586, 
    1.00000012, 4.27365303e-05, 3.75509262e-06, 
    -3.75509262e-06, 0.173663586, -0.984805346)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "one piece",
    Callback = function()
--one piece island
local targetCFrame = CFrame.new(822.80011, 16.3026886, 8962.32031, 0.984812498, 0, 0.173621148, 0, 1, 0, -0.173621148, 0, 0.984812498)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "demon slayer",
    Callback = function()
--demon slayer
local targetCFrame = CFrame.new(-6692.2417, 21.1733074, 1327.24316, 0, 0, 1, 0, 1, -0, -1, 0, 0)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "nanatsu",
    Callback = function()
--nanatsu
local targetCFrame = CFrame.new(3941.05078, 14.6696835, -2489.9209, 0.965929627, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, 0.965929627)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "clover sland",
    Callback = function()
--clover island
local targetCFrame = CFrame.new(-3975.57617, 76.8834457, 9807.3916, -0.978162646, 0, -0.20784153, 0, 1, 0, 0.20784153, 0, -0.978162646)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "dragon ball",
    Callback = function()
--dragon ball
local targetCFrame = CFrame.new(-726.287842, 12.9664917, 1175.84937, 0.984812498, -0, -0.173621148, 0, 1, -0, 0.173621148, 0, 0.984812498)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "crazy",
    Callback = function()
--crazy village
local targetCFrame = CFrame.new(49047.3164, 125.852577, 1175.00879, 0.984812498, -0, -0.173621148, 0, 1, -0, 0.173621148, 0, 0.984812498)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
print("Concluido")
    end
})

Main:AddButton({
    Title = "Cursed dojo",
    Callback = function()
--cursed dojo
local targetCFrame = CFrame.new(49047.3164, 125.852577, 1175.00879, 0.984812498, -0, -0.173621148, 0, 1, -0, 0.173621148, 0, 0.984812498)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFram
print("Concluido")
    end
})

Main:AddButton({
    Title = "One punch",
    Callback = function()
local targetCFrame = CFrame.new(-23691.7109, -21.3596802, 473.658325, 0.977745593, 0, 0.209794015, 0, 1, 0, -0.209794015, 0, 0.977745593)


local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local HRT = character:WaitForChild("HumanoidRootPart")

HRT.CFrame = targetCFrame
 print("Concluido")
    end
})
