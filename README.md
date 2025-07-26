-- Auto clicker melee para Roblox (delay de 0.1s entre ataques)
local delayEntreAtaques = 0.1 -- segundos

local player = game.Players.LocalPlayer

local function encontrarTool()
    local char = player.Character or player.CharacterAdded:Wait()
    -- Procura arma equipada ou no backpack
    return char:FindFirstChildOfClass("Tool") or player.Backpack:FindFirstChildOfClass("Tool")
end

task.spawn(function()
    while true do
        local tool = encontrarTool()
        if tool then
            tool:Activate()
        end
        task.wait(delayEntreAtaques)
    end
end)
