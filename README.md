-- Function to highlight all players
local function highlightPlayers()
    -- Loop through all players in the game
    for _, player in pairs(game.Players:GetPlayers()) do
        -- Ensure the player has a character and it is loaded
        if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            -- Check if the player already has a Highlight to prevent duplicates
            if not player.Character:FindFirstChild("Highlight") then
                -- Create the highlight object
                local highlight = Instance.new("Highlight")
                highlight.Parent = player.Character
                highlight.Adornee = player.Character
                highlight.FillColor = Color3.fromRGB(255, 0, 0)  -- Red highlight
                highlight.FillTransparency = 0.5  -- Semi-transparent
                highlight.OutlineColor = Color3.fromRGB(255, 255, 255)  -- White outline
                highlight.OutlineTransparency = 0.8  -- More transparent outline
            end
        end
    end
end

-- Continuously refresh the highlighting every 1 second
while true do
    highlightPlayers()  -- Refresh the player highlights
    wait(1)  -- Wait for 1 second before running again
end
