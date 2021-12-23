# Discord Game SDK

# Examples
## Blueprint Examples
### Creating the Core
Creating the core is the starting point when you plan to integrate Discord in you game.
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpCreateCore.png?raw=true)

!> Make sure the Discord Core doesn't get garbage collected! The Core keeps a hard reference to the managers. 
The managers are valid while the Core is not garbage collected.

!> If you run this code in editor without Discord in background, the Editor will close and launch Discord.
### Rich Presence
Rich Presence is really easy to implement: 
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpRichPresence.png?raw=true)
### Create a Lobby
![](https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpCreateLobby.png?raw=true)
##  C++ Examples
### Creating the Core
```cpp
UDiscordCore* DiscordCore = UDiscordCore::CreateDiscordCore(EDiscordCoreCreationFlags::Default);
if (DiscordCore)
{
    // We have a valid Discord Core !
    // We should keep it as a UPROPERTY() to prevent it
    // from being garbage collected...
}
```
### Rich Presence
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
### Create a Lobby
```cpp

UDiscordLobbyManager* LobbyManager = UDiscordLobbyManager::GetLobbyManager(DiscordCore);
UDiscordUserManager*  UserManager  = UDiscordUserManager::GetUserManager(DiscordCore);
if (LobbyManager && UserManager)
{
    const FDiscordUser User = UserManager->GetCurrentUser();
    
    FDiscordLobbyTransaction Transaction = LobbyManager->GetLobbyCreateTransaction();
    Transaction.SetCapacity(10);
    Transaction.SetLocked(false);
    Transaction.SetMetadata(TEXT("SomeKey"), TEXT("SomeValue"));
    Transaction.SetOwner(User.Id);
    Transaction.SetType(EDiscordLobbyType::Private);

    LobbyManager->CreateLobby(Transaction, FLobbyCallback::CreateLambda([](EDiscordResult Result, FDiscordLobby& Lobby)
    {
        if (Result == EDiscordResult::Ok)
        {
            // Lobby created.
        }
        else
        {
            // An error occured !
        }
    }));
}
```