# Discord - Features
## Table of content
1. [Download the SDK](#installation)<br/>
	1.1. [With the editor](#manual)<br/>
	1.2. [Manually](#manual)<br/>
3. [Modules](#managers)<br/>
	2.1. [Discord SDK]()<br/>
	2.2. [Discord Core]()<br/>
	2.3. [Discord Achievement]()<br/>
	2.4. [Discord Activity]()<br/>
	2.5. [Discord Application]()<br/>
	2.6. [Discord Voice]()<br/>
	2.7. [Discord Image]()<br/>
	2.8. [Discord Lobby]()<br/>
	2.9. [Discord Networking]()<br/>
	2.10. [Discord Overlay]()<br/>
	2.11. [Discord Relationship]()<br/>
	2.12. [Discord Storage]()<br/>
	2.13. [Discord Store]()<br/>
	2.14. [Discord User]()<br/>
4. [Examples]()<br/>
	3.1. [Blueprint Examples]()<br/>
	3.2. [C++ Examples]()<br/>
5. [Troubleshooting]()<br/>
6. [Contact]()<br/>

# 1. Download the SDK
Before using the plugin, you have to download the Discord Game SDK. To do so you have two options:
## 1.1. Download the SDK from the Editor
### 1.1.1. Open the configuration window
Start to open the configuration window by clicking on the Discord icon and choosing `Configure the Discord SDK`: 
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/OpenConfigureWindow.png?raw=true)
### 1.1.2. Download the SDK
In the configuration window, click on `Download the SDK`:
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/InvalidSdkWindow.png?raw=true)
Wait until the process complete, and it's already done, the Discord SDK is installed and ready to be used.
| :information_source: |If the installation fails, you'll have to download the SDK manually. Don't worry, it's not that difficult !|
|:--:|---|
## 1.2. Download the SDK manually
First, start by downloading the last release of the Discord Game SDK from Discord's servers: [discord_game_sdk.zip](https://dl-game-sdk.discordapp.net/latest/discord_game_sdk.zip).

You then need to extract it to `/DiscordFeatures/ThirdParty/DiscordSdk/`.  

If it is installed correctly, the `Discord Configuration Window` won't ask you to download the SDK.

# 2. Modules
The Discord Features Plugin is separated in several modules. Each module contains a set of functionalities.
To use one in C++, you have to add the module to your `Build.cs` file:
```csharp
PrivateDependencyModuleNames.Add("DiscordCore");
```
You don't need to do anything for Blueprints and can just start using these modules. 
## 2.1 Discord SDK
This module handles the Discord SDK and load it correctly. It is done for you internally so you won't have to use it.
## 2.2. Discord Core
This is the core of the SDK. This is from where you have access to the managers.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/discord](https://discord.com/developers/docs/game-sdk/discord)
C++ Module Name: `DiscordCore`
## 2.3. Discord Achievement
This is where are handled the achievements.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/achievements](https://discord.com/developers/docs/game-sdk/achievements)
C++ Module Name: `DiscordAchievement`
## 2.4. Discord Activity
This is where are handled the users' activity and the so famous `Rich Presence`.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/activities](https://discord.com/developers/docs/game-sdk/activities)
C++ Module Name: `DiscordActivity`
## 2.5. Discord Application
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/applications](https://discord.com/developers/docs/game-sdk/applications)
C++ Module Name: `DiscordApplication`
## 2.6. Discord Voice
This is where to look if you want to implement voice chat in your game.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/discord-voice](https://discord.com/developers/docs/game-sdk/discord-voice)
C++ Module Name: `DiscordVoice`
## 2.7. Discord Image
This is where images are handle, including users avatars.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/images](https://discord.com/developers/docs/game-sdk/images)
C++ Module Name: `DiscordImage`
## 2.8. Discord Lobby
This is where multiplayer and lobbies are handled.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/lobbies](https://discord.com/developers/docs/game-sdk/lobbies)
C++ Module Name: `DiscordLobby`
## 2.9. Discord Networking
If you want to use Discord's Networking.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/networking](https://discord.com/developers/docs/game-sdk/networking)
C++ Module Name: `DiscordNetworking`
## 2.10. Discord Overlay
To manage the build-in Discord overlay.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/overlay](https://discord.com/developers/docs/game-sdk/overlay)
C++ Module Name: `DiscordOverlay`
## 2.11. Discord Relationship
To manage the relationship between your players.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/relationships](https://discord.com/developers/docs/game-sdk/relationships)
C++ Module Name: `DiscordRelationship`
## 2.12. Discord Storage
To store data on Discord's servers.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/storage](https://discord.com/developers/docs/game-sdk/storage)
C++ Module Name: `DiscordStorage`
## 2.13. Discord Store
For in-app purchases and DLC.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/store](https://discord.com/developers/docs/game-sdk/store)
C++ Module Name: `DiscordStore`
## 2.14. Discord User
To retrieve and manage user data.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/users](https://discord.com/developers/docs/game-sdk/users)
C++ Module Name: `DiscordUser`
