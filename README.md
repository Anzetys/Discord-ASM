# XASM
![1ed935c75af4f2925ab1072dc59346d2](https://github.com/Anzetys/Discord-ASM/assets/150568341/e76cc475-e40f-415e-a90b-c35ecb1a31c3)





## :fire: Key Features:

# :computer: Server Monitoring
"RestartIfShutdown": true, // enables the server monitoring feature
"CheckEvery": 60, // Check if the server is down every 60 minutes

# :video_game: Server Control
 ## Start, Stop, Update And Rcon Commander.

# :alarm_clock: Advanced Backups
**Configurable for Multiple Servers**
**Scheduled Backups** Cron https://crontab.guru/#0_*/1_*_*_*
**Selective File Copying** *(Enhances efficiency by backing up only the files that have changed since the last backup.)*
**Compression level** for 7-Zip, Ranges from 0 (no compression) to 9 (maximum compression)


# :globe_with_meridians: Real-Time Status Updates
## Get instant, dynamic updates on server status And player counts
:green_circle: Online
:red_circle: Offline

# :joystick: Interactive Control Panel
 Dive into our user-friendly control panel with interactive customizable buttons. Manage your server from discord!


# :computer: RCON Integration 
## Rcon Button your next message in the control panel is sent to the game server directly. It's like having telepathic powers over your server!

# :wrench: Customizable Settings
## Personalize each server's settings with our easy-to-edit config file. Your server, your rules!
# :lock: Enhanced Security Access Control
## Keep your server safe with restricted bot commands, ensuring only the chosen ones can wield its power.


**Commented_Config.json**
```
{
  "discordBot": {
    "token": "BOTtoken", // Discord Bot Token
    "controlChannelId": "PanelChannelID", // Panel Channel ID where control messages will be sent
    "allowedUsers": [
      "1236723133604514",
      "1236723133604514",
      "1236723133604514",
      "1236723133604514"
    ], // List of Discord User IDs allowed to interact with the bot
    "allowedRoles": [
      "12367133323332114"
    ], // List of Discord Role IDs allowed to interact with the bot
    "steamcmd_path": "C:\\SteamCMD\\steamcmd.exe", // Path to SteamCMD executable
    "updatePanelsInterval": 120000, // Update the player Count and server status cooldown
    "servers": [
      {
        "Panel_MessageID": null, // Discord message ID for the control panel (null to send a new one)
        "installDir": "C:\\server3", // Folder where your server files are
        "name": "SessionName", // server Name
        "exePath": "C:\\server3\\ShooterGame\\Binaries\\Win64\\ArkAscendedServer.exe", // Path to the server executable
        "mapName": "TheIsland_WP", // Name of the map to load
        "multiHome": "192.198.3.1", // IP address for binding
        "serverPort": "7777", // Port for game client connections
        "queryPort": "25565", // Port for server query
        "RCONIp": "192.198.3.1", // IP address for RCON
        "RCONPort": "RCONPort", // Port for RCON
        "RconPassword": "RconPassword", // Password for RCON
        "extraParameters": "ForceFlyerExplosives=false? -ActiveEvent=none -ForceAllowCaveFlyers -EnableIdlePlayerKick -clusterid -ClusterDirOverride=\"D:\\cluster\" -NoTransferFromFiltering -UseBattlEye -forcerespawndinos -servergamelog -NoHangDetection -nosteamclient -game -server -log -MinimumTimeBetweenInventoryRetrieval=3600 -nomansky -gameplaylogging -servergamelog -servergamelogincludetribelogs -crossplay", // Additional parameters for the server launch command
        "winLiveMaxPlayers": "70", // Maximum number of players
        "RespawnWildDinosInterval": "14400", // Interval for wild dino Wipess
        "AllowCrateSpawnsOnTopOfStructures": "True", // Enable/Disable crate spawns on top of structures
        "RCONEnabled": "True", // Enables RCON
        "RCONServerGameLogBuffer": "600", // Buffer size for RCON server game log
        "mods": "", // Mods to be loaded on the server
        "description": "Panel Description", // Description for the server control panel
        "embedColor": "#0099ff", // Color of the embed in the control panel
        "thumbnailUrl": "https://example.com/thumbnail.png", // URL of the thumbnail image for the embed
        "footerImageUrl": "https://example.com/footerimage.png", // URL of the footer image for the embed
        "startButtonLabel": "✅ Start", // Label for the 'Start' button. Defaults if empty
        "stopButtonLabel": "🛑 Stop", // Label for the 'Stop' button. Defaults if empty
        "killButtonLabel": "☠️ Kill", // Label for the 'Kill' button. Defaults if empty
        "saveworldButtonLabel": "💾 SaveWorld", // Label for the 'SaveWorld' button. Defaults if empty
        "updateButtonLabel": "🕒 Update", // Label for the 'Update' button. Defaults if empty
        "PlayerListButtonLabel": "Online Players", // Label for the 'Online Players' button. Defaults if empty
        "rconButtonLabel": "Rcon", // Label for the 'Rcon' button. Defaults if empty
        "Add_Description_Fields_Below_This_Line": "As many as you want, must be DescriptionField(number) and have a matching Field(number)", // Just an spacer. remove if you wish
        "DescriptionField1": "✅ Start",
        "Field1": "Starts the server using the specified settings.",
        "DescriptionField2": "🛑 Stop",
        "Field2": "Stops the server with a 15-minute warning.",
        "DescriptionField3": "☠️ Kill",
        "Field3": "Stops server immediately without warnings.",
        "DescriptionField4": "💾 SaveWorld",
        "Field4": "Saves the current world state via RCON.",
        "DescriptionField5": "🕒 Update",
        "Field5": "Updates the server. Must be stopped first.",
        "DescriptionField6": "Player List",
        "Field6": "Displays the Player List and their unique IDs"
        // Add more fields as needed. As many as you want, must be DescriptionField(number) and have a matching Field(number)"
      }
    ]
  },
  "backupConfig": [
    {
      "serverName": "server1",
      "sourceDirectory": "C:\\server1\\ShooterGame\\Saved\\SavedArks\\TheIsland_WP", // path to the files you wish to backup
      "backupDirectory": "C:\\_Backups_\\server1", // path to the folder where your files will be backed up
      "cronSchedule": "0 */1 * * *", // Cron schedule string for automated backups. // Example: "0 */6 * * *" means every 6 hours.
      "zipCommand": "C:\\Program Files\\7-Zip\\7z.exe", // Full path to the 7-Zip executable. Ensure this is correctly set.
      "compressionLevel": 1, // Compression level for 7-Zip. Ranges from 0 (no compression) to 9 (maximum compression).
      "backupMode": "modified", // modified only backups the files that changed since last backup. all backups all files
      "backupOnStartup": false // true/false setting to backup On Startup
    },
    {
      "serverName": "Server2",
      "sourceDirectory": "C:\\path\\ShooterGame\\Saved\\SavedArks\\TheIsland_WP",
      "backupDirectory": "C:\\_Backups_\\Server2",
      "cronSchedule": "20 */1 * * *",
      "zipCommand": "C:\\Program Files\\7-Zip\\7z.exe",
      "compressionLevel": 1,
      "backupMode": "modified",
      "backupOnStartup": false
    }
  ]
}
```
