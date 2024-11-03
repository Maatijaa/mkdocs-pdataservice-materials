### Changelog for pDataService

!!! note
      This is the **latest** update.

#### Version 1.0.1

* **Initial Release**: Launched the pDataService to manage player data profiles with various features.

#### Features Added

* **Data Store Integration**: Implemented integration with Roblox DataStoreService for saving and loading player profiles.
* **Configurable Parameters**: Introduced a configuration module allowing customization of key parameters such as `DataStoreKey`, `AutoSaveInterval`, `ProfileBackupInterval`, and others.
* **Profile Management**: Enabled loading and saving of player profiles, with data validation to ensure integrity.
* **Auto-Save Functionality**: Added automatic saving of profiles at user-defined intervals.
* **Profile Backup**: Implemented a backup feature to create backups of player profiles, with the ability to restore from backup if needed.
* **Data Compression**: Introduced data compression for storage optimization.
* **Rate Limiting**: Added rate limiting to manage save requests and prevent server overload.
* **Profile Locking**: Implemented profile locking to prevent concurrent modifications during data operations.
* **Event Hooks**: Introduced event hooks for `OnProfileLoad`, `OnProfileSave`, and `OnProfileDelete` to allow custom actions on these events.
* **Logging System**: Implemented a logging system for tracking data operations and errors with various log levels.

#### Bug Fixes

* **Error Handling**: Improved error handling during data loading and saving to provide clearer error messages.
* **Validation Checks**: Enhanced validation checks for data consistency and integrity before processing.

#### Performance Improvements

* **Async Data Operations**: Converted data save operations to use coroutines for non-blocking execution.
* **Retry Mechanism**: Added a retry mechanism for data save and load operations to enhance reliability.