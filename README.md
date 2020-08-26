
# Discord - Features
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/DiscordFeatures.PNG?raw=true)
## Table of content
1. [Downloading the SDK](#1-download-the-sdk)<br/>
	1.1. [With the editor](#11-download-the-sdk-from-the-editor)<br/>
	1.2. [Manually](#12-download-the-sdk-manually)<br/>
2. [Configure the SDK](#2-configure-the-sdk)</br>
3. [Modules](#3-modules)<br/>
	3.1. [Discord SDK](#31-discord-sdk)<br/>
	3.2. [Discord Core](#32-discord-core)<br/>
	3.3. [Discord Achievement](#33-discord-achievement)<br/>
	3.4. [Discord Activity](#34-discord-activity)<br/>
	3.5. [Discord Application](#35-discord-application)<br/>
	3.6. [Discord Voice](#36-discord-voice)<br/>
	3.7. [Discord Image](#37-discord-image)<br/>
	3.8. [Discord Lobby](#38-discord-lobby)<br/>
	3.9. [Discord Networking](#39-discord-networking)<br/>
	3.10. [Discord Overlay](#310-discord-overlay)<br/>
	3.11. [Discord Relationship](#311-discord-relationship)<br/>
	3.12. [Discord Storage](#312-discord-storage)<br/>
	3.13. [Discord Store](#313-discord-store)<br/>
	3.14. [Discord User](#314-discord-user)<br/>
4. [Getting started](#4-getting-started)<br/>
5. [Examples](#5-examples)<br/>
	5.1. [Blueprint Examples](#51-blueprint-examples)<br/>
	5.2. [C++ Examples](#52-c-examples)<br/>
5. [Contact](#6-contact)<br/>

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
# 2. Configure the SDK
Open the configuration window by clicking on the Discord icon and choosing `Configure the Discord SDK`: 

![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/OpenConfigureWindow.png?raw=true)

In the window, set your application ID with the one of your application. You can create and get your application ID from [Discord]([https://discord.com/developers/applications](https://discord.com/developers/applications)).
You can set your secret bot token as well if you plan to use the Discord editor tools.
| :warning: |The secret bot token is stored in an Editor-only config file called `DiscordSdkEditor.ini`. Think to exclude it from source control if needed. |
|:--:|:---|
# 3. Modules
The Discord Features Plugin is separated in several modules. Each module contains a set of functionalities.
To use one in C++, you have to add the module to your `Build.cs` file:
```csharp
PrivateDependencyModuleNames.Add("DiscordCore");
```
You don't need to do anything for Blueprints and can just start using these modules. 
## 3.1 Discord SDK
This module handles the Discord SDK and load it correctly. It is done for you internally so you won't have to use it.
## 3.2. Discord Core
This is the core of the SDK. This is from where you have access to the managers.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/discord](https://discord.com/developers/docs/game-sdk/discord)</br>
C++ Module Name: `DiscordCore`
## 3.3. Discord Achievement
This is where are handled the achievements.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/achievements](https://discord.com/developers/docs/game-sdk/achievements)</br>
C++ Module Name: `DiscordAchievement`
## 3.4. Discord Activity
This is where are handled the users' activity and the so famous `Rich Presence`.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/activities](https://discord.com/developers/docs/game-sdk/activities)</br>
C++ Module Name: `DiscordActivity`
## 3.5. Discord Application
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/applications](https://discord.com/developers/docs/game-sdk/applications)</br>
C++ Module Name: `DiscordApplication`
## 3.6. Discord Voice
This is where to look if you want to implement voice chat in your game.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/discord-voice](https://discord.com/developers/docs/game-sdk/discord-voice)</br>
C++ Module Name: `DiscordVoice`
## 3.7. Discord Image
This is where images are handle, including users avatars.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/images](https://discord.com/developers/docs/game-sdk/images)</br>
C++ Module Name: `DiscordImage`
## 3.8. Discord Lobby
This is where multiplayer and lobbies are handled.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/lobbies](https://discord.com/developers/docs/game-sdk/lobbies)</br>
C++ Module Name: `DiscordLobby`
## 3.9. Discord Networking
If you want to use Discord's Networking.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/networking](https://discord.com/developers/docs/game-sdk/networking)</br>
C++ Module Name: `DiscordNetworking`
## 3.10. Discord Overlay
To manage the build-in Discord overlay.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/overlay](https://discord.com/developers/docs/game-sdk/overlay)</br>
C++ Module Name: `DiscordOverlay`
## 3.11. Discord Relationship
To manage the relationship between your players.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/relationships](https://discord.com/developers/docs/game-sdk/relationships)</br>
C++ Module Name: `DiscordRelationship`
## 3.12. Discord Storage
To store data on Discord's servers.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/storage](https://discord.com/developers/docs/game-sdk/storage)</br>
C++ Module Name: `DiscordStorage`
## 3.13. Discord Store
For in-app purchases and DLC.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/store](https://discord.com/developers/docs/game-sdk/store)</br>
C++ Module Name: `DiscordStore`
## 3.14. Discord User
To retrieve and manage user data.</br>
Official Discord Documentation: [https://discord.com/developers/docs/game-sdk/users](https://discord.com/developers/docs/game-sdk/users)</br>
C++ Module Name: `DiscordUser`
# 4. Getting started
## 4.1. About the `RunCallbacks` function
If you read the Discord Game SDK documentation or you already worked with the Discord Game SDK, you might know that the `RunCallbacks` should be called every tick. However, you don't have to worry anymore for it ! Discord Features automatically call the `RunCallbacks` function of Discord Core as well as the `Flush` function of Discord Network Manager.
## 4.2. Blueprints
Discord Features tries to look as much as possible like the  [official Discord Game SDK documentation]([https://discord.com/developers/docs/game-sdk/sdk-starter-guide](https://discord.com/developers/docs/game-sdk/sdk-starter-guide)). You can refer to it to integrate Discord into your game and to the [Blueprint Examples]().

Nodes that require a callback as parameter have been implemented as a single asynchronous node with multiple output pins. It allows a faster development and to have a better view of your code:
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpAsyncNode.png?raw=true)

## 4.3. C++
### 4.3.1. Includes
Here is an exhaustive list of includes available:
```cpp
#include "DiscordCore.h"                // For UDiscordCore
#include "DiscordAchievementManager.h"  // For UDiscordAchievementManager
#include "DiscordActivityManager.h"     // For UDiscordActivityManager
#include "DiscordApplicationManager.h"  // For UDiscordApplicationManager
#include "DiscordImageManager.h"        // For UDiscordImageManager
#include "DiscordLobbyManager.h"        // For UDiscordLobbyManager
#include "DiscordNetworkManager.h"      // For DiscordNetworkManager
#include "DiscordOverlayManager.h"      // For UDiscordOverlayManager
#include "DiscordRelationshipManager.h" // For UDiscordRelationshipManager
#include "DiscordStorageManager.h"      // For UDiscordStorageManager
#include "DiscordStoreManager.h"        // For UDiscordStoreManager
#include "DiscordUserManager.h"         // For UDiscordUserManager
#include "DiscordVoiceManager.h"        // For UDiscordVoiceManager
```
### 4.3.2. Getting a Manager
The Discord Game SDK has several managers to handle functionalities. You can get those managers from a `Discord Core`.
To get a manager in C++, you have to do the following:
```cpp
UDiscordNetworkManager* Manager = UDiscordNetworkManager::GetNetworkManager(DiscordCore);
if (Manager)
{
    // Do stuff with the manager
    if (Manager->OpenChannel(456, 123, true) == EDiscordResult::Ok)
    {
        // ...   
    }
}
```
### 4.3.3. Using the Discord Game SDK
Aside from the specificity of getting a manager, Discord Features is used the *exact* same way as the official SDK. Each method has the same signature with the types of the Unreal Engine instead: `Delegates` for `Callbacks`, `FString` for `string`, etc. 
This is why you can safely refer to the [official Discord Game SDK documentation]([https://discord.com/developers/docs/game-sdk/sdk-starter-guide](https://discord.com/developers/docs/game-sdk/sdk-starter-guide)).
# 5. Examples
## 5.1. Blueprint Examples
### 5.1.1. Creating the Core
Creating the core is the starting point when you plan to integrate Discord in you game.
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpCreateCore.png?raw=true)
| :warning: |Make sure the Discord Core doesn't get garbage collected !|
|:--:|:---|

| :information_source: |If you run this code in editor without Discord in background, the Editor will close and launch Discord.|
|:--:|:---|
### 5.1.2. Rich Presence
Rich Presence is really easy to implement: 
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpRichPresence.png?raw=true)
## 5.2. C++ Examples
### 5.2.1. Creating the Core
```cpp
UDiscordCore* DiscordCore = UDiscordCore::CreateDiscordCore(EDiscordCoreCreationFlags::Default);
if (DiscordCore)
{
    // We have a valid Discord Core !
    // We should keep it as a UPROPERTY() to prevent it
    // from being garbage collected...
}
```
### 5.2.2. Rich Presence
```cpp
UDiscordActivityManager* ActivityManager = UDiscordActivityManager::GetActivityManager(DiscordCore);
if (ActivityManager)
{
    FDiscordActivity Activity;
    Activity.State   = TEXT("In a dungeon...");
    Activity.Details = TEXT("Slaying monsters !");
    
    ActivityManager->UpdateActivity(Activity, FDiscordResultCallback::CreateLambda([](EDiscordResult Result) 
    {
        if (Result == EDiscordResult::Ok)
        {
            // Activity has been updated !
        }
        else
        {
            // An error occured !
        }
    }));
}
```
# 6. Contact
If you need help, spotted a bug, have a feature request or experience troubles, please contact us at [pandores.marketplace@gmail.com](mailto:pandores.marketplace+DiscordFeatures@gmail.com?subject=DiscordFeatures%20-%20).
