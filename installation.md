# Discord Features Installation

## Download the SDK
Before using the plugin, you have to download the Discord Game SDK. To do so you have two options:

### 1. Download the SDK from the Editor

### 1.1. Open the configuration window
Start to open the configuration window by clicking on the Discord icon and choosing `Configure the Discord SDK`: 

<div class="centered">
<img src="https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/OpenConfigureWindow.png?raw=true"/>
</div>

#### 1.2. Download the SDK
In the configuration window, click on `Download the SDK`:

<div class="centered">
<img src="https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/InvalidSdkWindow.png?raw=true"/>
</div>

Wait until the process is over, and it's already done, the Discord SDK is installed and ready to be used.

!> If the installation fails, you'll have to download the SDK manually. Don't worry, it's not that difficult !

### 2. Download the SDK manually
First, start by downloading the last release of the Discord Game SDK from Discord's servers: 
[discord_game_sdk.zip](https://dl-game-sdk.discordapp.net/latest/discord_game_sdk.zip).

You then need to extract it to `/DiscordFeatures/ThirdParty/DiscordSdk/`.  

If it is installed correctly, the `Discord Configuration Window` won't ask you to download the SDK.
## Configure the SDK
Open the configuration window by clicking on the Discord icon and choosing `Configure the Discord SDK`: 


<div class="centered">
<img src="https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/OpenConfigureWindow.png?raw=true"/>
</div>


In the window, set your application ID with the one of your application. You can create and get your application ID from [Discord]([https://discord.com/developers/applications](https://discord.com/developers/applications)).
You can set your secret bot token as well if you plan to use the Discord editor tools.

!> The secret bot token is stored in an Editor-only config file called `DiscordSdkEditor.ini`. Think to exclude it from source control if needed.

## C++ Setup

### Link the Modules
The Discord Features Plugin is separated in several modules. Each module contains a set of functionalities.
To use one in C++, you have to add the module to your `Build.cs` file:
```csharp
PrivateDependencyModuleNames.Add("DiscordCore"); // Add one module
```
or to add more than one:
```csharp
PrivateDependencyModuleNames.AddRange(new string[]
{
    "DiscordLobby",    // Add one...
    "DiscordNetwork",  // two...
    "DiscordImage"     // three modules
});
```

### Includes
The following includes are available:
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
#include "DiscordGatewaySocket.h"       // For UDiscordGatewaySocket
#include "DiscordWebhookLibrary.h"      // For FDiscordWebhookLibrary
```


!> You don't need to do anything for Blueprints and can just start using these modules. 

