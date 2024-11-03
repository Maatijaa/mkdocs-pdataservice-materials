# Introduction

pDataService - Advenced Data Managment for Roblox Games.

**pDataService** is a powerful data management module for Roblox that provides reliable data handling, automatic saving, backup functionality, and easy customization. It is designed to simplify data storage, versioning, and backup for player profiles and global data.

[Roblox Marketplace Download](https://create.roblox.com/store/asset/78951486721130/pDataService-RELEASE)

- Support Development

[Donate in Roblox game](https://www.roblox.com/games/130539550936036/ParaTech-Donations-Support-us)

[PayPal](https://paypal.me/matijamiric)

# Full Feature List

### Full Feature List of pDataService

1. **Data Store Configuration**:
  * Customizable DataStore key (`DataStoreKey`).
  * Versioning support (`DataVersion`).
  * Configurable intervals for auto-saving and profile backups.
2. **Auto-Save Functionality**:
  * Automatically saves player profiles at regular intervals.
3. **Profile Management**:
  * Active management of player profiles, including loading and saving.
  * Supports default data values for new profiles.
4. **Profile Backup and Restore**:
  * Automatic backups of player profiles.
  * Ability to restore profiles from backups using a designated backup key suffix.
5. **Data Compression**:
  * Option to enable or disable data compression for storage efficiency.
6. **Rate Limiting**:
  * Implements rate limiting on save requests to prevent spamming.
7. **Profile Locking Mechanism**:
  * Locks profiles during modifications to prevent concurrent changes.
8. **Event Hooks**:
  * Custom event hooks for various profile actions (load, save, delete).
  * Allows for custom callbacks on these events.
9. **Data Validation**:
  * Ensures that all player data meets required specifications before saving or loading.
  * Checks for required fields and their data types.
10. **Logging System**:
  * Comprehensive logging with different levels (INFO, ERROR, WARNING).
  * Tracks important events and errors for debugging.
11. **Async Data Operations**:
  * Non-blocking data saving with coroutines, enhancing performance during player interactions.
12. **Retry Mechanism**:
  * Retries failed save and load operations up to a specified maximum number of attempts.
13. **Global Data Handling**:
  * Ability to save and load global data separate from player profiles.
14. **Profile Expiration**:
  * Supports profile expiration with configurable expiration times.
15. **Statistics Tracking**:
  * Maintains statistics for each player’s profile save operations.
16. **Snapshot Management**:
  * Ability to manage snapshots of player profiles for historical tracking.
17. **Profile Clearing**:
  * Functionality to clear all active profiles from memory.
18. **Customizable Error Handling**:
  * Defined error messages for different failure scenarios during data operations.
19. **Initialization Method**:
  * Initializes the service and starts the auto-save coroutine upon setup.
20. **Profile Data Updates**:
  * Allows for updating existing player profile data efficiently.
21. **Last Save Time Tracking**:
  * Tracks the last time a profile was saved for each player.

# Configuration Tips

!!! note
     Make sure that you configurate the **WHOLE** config file because everything is managed from there.

**Quick glance at Config module script:**

```lua
local Config = {}

-- Data store settings
Config.DataStoreKey = "CHANGE_ME" 
assert(Config.DataStoreKey ~= "CHANGE_ME", "DataStoreKey must be set!")

Config.DataVersion = "1.0.1"

-- Auto-saving settings
Config.AutoSaveInterval = 60 -- Time in seconds between automatic saves
Config.ProfileBackupInterval = 300 -- Time in seconds between backups

-- Request settings
Config.RequestRateLimit = 5 -- Minimum time in seconds between requests for the same player

-- Encryption settings
Config.EnableEncryption = true -- Enable or disable encryption
Config.EncryptionKey = 123 -- Key used for encryption/decryption (should be a number)
assert(type(Config.EncryptionKey) == "number", "EncryptionKey must be a number!")

-- Logging settings
Config.EnableLogging = true -- Enable or disable logging
Config.LogLevel = "INFO" -- Log level: INFO, WARNING, ERROR

-- Profile management settings
Config.MaxInactiveDuration = 3600 -- Maximum duration in seconds to keep inactive profiles in memory
Config.CleanupInterval = 600 -- Time in seconds between profile cleanup checks
Config.MaxBackupsPerPlayer = 5 -- Maximum number of backups to keep per player

Config.MaxRetries = 3 -- Maximum number of retries for saving/loading profiles
Config.UseBackup = true -- Whether to use backups for profiles
Config.BackupKeySuffix = "_backup" -- Suffix for backup keys
Config.CompressionEnabled = true -- Enable or disable data compression
Config.ProfileExpirationTime = 3600 -- Duration in seconds before profiles expire

return Config
```