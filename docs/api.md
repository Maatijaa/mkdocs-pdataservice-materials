!!! warning
      Regularly back up player data to prevent data loss.

!!! note
      Ensure proper error handling to manage potential failures during data operations.
  

### 1. `pDataService:Log(message, level)`

Logs messages with a timestamp and specified log level.

* **Parameters**:
  * `message` (string) - The message to log.
  * `level` (string) - The log level (default: "INFO").
* **Returns**: None.

**Example:**
 
``` lua
pDataService:Log("Player has logged in.", "INFO")
```

---

### 2. `pDataService:GenerateKey(playerId)`

Generates a unique data store key for a given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (string) - The generated key for the player.

**Example:**

``` lua
local playerKey = pDataService:GenerateKey(player.UserId)
print("Generated key: " .. playerKey)
```

---

### 3. `pDataService:GetDataStore()`

Retrieves the data store instance based on the configured key.

* **Parameters**: None.
* **Returns**: (DataStore) - The data store instance.

**Example:**

``` lua
local dataStore = pDataService:GetDataStore()
```

---

### 4. `pDataService:CompressData(data)`

Compresses data using JSON encoding if compression is enabled.

* **Parameters**:
  * `data` (table) - The data to compress.
* **Returns**: (string) - The compressed data as a JSON string.

**Example:**

``` lua
local compressedData = pDataService:CompressData(playerData)
```

---

### 5. `pDataService:DecompressData(data)`

Decompresses data using JSON decoding if compression is enabled.

* **Parameters**:
  * `data` (string) - The compressed data.
* **Returns**: (table) - The decompressed data.

**Example:**

``` lua
local decompressedData = pDataService:DecompressData(compressedData)
```

---

### 6. `pDataService:RateLimit(playerId)`

Checks and manages the rate limit for saving profiles based on the last save time.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (boolean) - `true` if the player can save, `false` otherwise.

**Example:**

``` lua
if pDataService:RateLimit(player.UserId) then
    print("You can save your profile.")
end
```

---

### 7. `pDataService:ValidateData(data)`

Validates data to ensure it meets the required structure and types.

* **Parameters**:
  * `data` (table) - The data to validate.
* **Returns**: (boolean) - `true` if valid, `false` otherwise.

**Example:**

``` lua
if pDataService:ValidateData(playerData) then
    print("Data is valid.")
else
    print("Data is invalid.")
end
```

---

### 8. `pDataService:LoadProfile(playerId, defaultData)`

Loads the player profile for the given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
  * `defaultData` (table) - The default data to return if loading fails.
* **Returns**: (table) - The loaded profile data.

**Example:**

``` lua
local profileData = pDataService:LoadProfile(player.UserId, defaultProfile)
```

---

### 9. `pDataService:SaveProfile(playerId)`

Saves the active profile data for the given player ID to the data store.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (boolean) - `true` if saved successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:SaveProfile(player.UserId) then
    print("Profile saved successfully.")
end
```

---

### 10. `pDataService:ReleaseProfile(playerId)`

Releases the profile data for the given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: None.

**Example:**

``` lua
pDataService:ReleaseProfile(player.UserId)
```

---

### 11. `pDataService:AutoSaveProfiles()`

Automatically saves profiles at specified intervals.

* **Parameters**: None.
* **Returns**: None.

**Example:**

``` lua
pDataService:AutoSaveProfiles()
```

---

### 12. `pDataService:BackupProfile(playerId)`

Creates a backup of the active profile data for the given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (boolean) - `true` if backup created successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:BackupProfile(player.UserId) then
    print("Profile backup created.")
end
```

---

### 13. `pDataService:RestoreBackup(playerId)`

Restores the profile data from a backup for the given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (boolean) - `true` if restored successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:RestoreBackup(player.UserId) then
    print("Profile restored from backup.")
end
```

---

### 14. `pDataService:SaveGlobalData(key, data)`

Saves global data under a specified key to the data store.

* **Parameters**:
  * `key` (string) - The key under which to save the data.
  * `data` (table) - The data to save.
* **Returns**: (boolean) - `true` if saved successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:SaveGlobalData("serverSettings", settingsData) then
    print("Global data saved.")
end
```

---

### 15. `pDataService:LoadGlobalData(key, defaultData)`

Loads global data from the data store under the specified key.

* **Parameters**:
  * `key` (string) - The key to load data from.
  * `defaultData` (table) - The default data to return if loading fails.
* **Returns**: (table) - The loaded global data.

**Example:**

``` lua
local globalData = pDataService:LoadGlobalData("serverSettings", defaultSettings)
```

---

### 16. `pDataService:LockProfile(playerId)`

Locks the profile for the given player ID to prevent concurrent modifications.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: None.

**Example:**

``` lua
pDataService:LockProfile(player.UserId)
```

---

### 17. `pDataService:UnlockProfile(playerId)`

Unlocks the profile for the given player ID to allow modifications.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: None.

**Example:**

``` lua
pDataService:UnlockProfile(player.UserId)
```

---

### 18. `pDataService:IsProfileLocked(playerId)`

Checks if a player’s profile is locked.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (boolean) - `true` if locked, `false` otherwise.

**Example:**


``` lua
if pDataService:IsProfileLocked(player.UserId) then
    print("Profile is locked.")
end
```

---

### 19. `pDataService:GetLastSaveTime(playerId)`

Retrieves the last save time for the given player's profile.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
* **Returns**: (DateTime) - The last save time.

**Example:**

``` lua
local lastSaveTime = pDataService:GetLastSaveTime(player.UserId)
print("Last save time: " .. lastSaveTime)
```

---

### 20. `pDataService:UpdateProfile(playerId, updates)`

Updates the active profile with new data for the given player ID.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
  * `updates` (table) - The data to update in the profile.
* **Returns**: (boolean) - `true` if updated successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:UpdateProfile(player.UserId, {level = 5}) then
    print("Profile updated.")
end
```

---

### 21. `pDataService:AsyncSaveData(playerId, data)`

Asynchronously saves data for the given player ID after validating it.

* **Parameters**:
  * `playerId` (number) - Unique ID of the player.
  * `data` (table) - The data to save.
* **Returns**: (boolean) - `true` if saved successfully, `false` otherwise.

**Example:**

``` lua
if pDataService:AsyncSaveData(player.UserId, playerData) then
    print("Async save successful.")
end
```