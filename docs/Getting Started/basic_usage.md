!!! note 
      If auto-saving is enabled in pDataService, manual saves on PlayerRemoving are not strictly necessary but recommended for data integrity. To ensure reliability, consider adding error handling for network or server issues, especially if saving to an external database. Additionally, define all required data fields in `SetDefaultProfile()` to prevent missing data errors during gameplay.

Heres a simple implementation example:
[SimpleDataManager.rbxm](https://github.com/Maatijaa/pdataservice-docs/releases/tag/1.0.1)

And also heres code example:

``` lua
-- Require the pDataService module
local pDataService = require(game.ServerScriptService.pDataService)

-- Define default player data to ensure all profiles have these initial values
pDataService:SetDefaultProfile({
    Coins = 0,
    Level = 1,
    Inventory = {}
})

-- Load player profile when they join
game.Players.PlayerAdded:Connect(function(player)
    local success, profile = pDataService:LoadProfile(player.UserId)
    
    if success then
        print("Profile loaded successfully for", player.Name)
        
        -- Example of modifying data: Adding 10 coins to the player’s profile
        profile.Data.Coins = (profile.Data.Coins or 0) + 10
    else
        warn("Failed to load profile for", player.Name)
    end
end)

-- Save player profile when they leave
game.Players.PlayerRemoving:Connect(function(player)
    pDataService:SaveProfile(player.UserId)
end)

```

