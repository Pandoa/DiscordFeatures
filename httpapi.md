# Discord HTTP API

## Webhooks

Webhooks are a low-effort way to post messages to channels in Discord. They do not require a bot user or authentication to use.
Discord Features offers a library to easily interact with the Discord HTTP API without needing to touch HTTP requests.

### Configuration
To use the Webhooks, you need to have enough credentials to do so. An easy way to do it is to create a bot and 
[get a secret bot token](https://discord.com/developers/applications/). Copy the secret Bot Token to the Discord HTTP API settings window 
located in `Project Settings > Plugins > Discord HTTP API`.

<div class="centered">
<img alt="Discord HTTP API config window" src="https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/WebhookConfigWindow.png?raw=true"/>
</div>

!> This method should be used for Dedicated Servers. Be careful that your token doesn't get distributed with your game to the players. The token is stored in `DiscordHttpApi.ini`, see [Unreal Engine Config System](https://docs.unrealengine.com/en-US/Programming/Basics/ConfigurationFiles/index.html) to make per-build config files. 

### Methods available

<br/>

|Name|Description|
|:---|:---|
|`CreateWebhook`|Create a new WebHook.|
|`GetChannelWebhooks`|Returns a list of channel webhook objects. Requires the `MANAGE_WEBHOOKS` permission.|
|`GetGuildWebhooks`|Returns a list of channel webhook objects. Requires the `MANAGE_WEBHOOKS` permission.|
|`GetWebhook`|Returns the webhook object for the given id.|
|`GetWebhookWithToken`|Returns the webhook object for the given id.|
|`ModifyWebhook`|Modify a webhook. Requires the `MANAGE_WEBHOOKS` permission. Returns the updated webhook object on success.|
|`ModifyWebhookWithToken`|Modify a webhook. Requires the `MANAGE_WEBHOOKS` permission. Returns the updated webhook object on success.|
|`DeleteWebhook`|Delete a webhook permanently.|
|`DeleteWebhookWithToken`|Delete a webhook permanently.|
|`ExecuteWebhook`|Execute the Webhook.|


### Send a message with Webhooks
You can send a message to a channel with Webhooks. These messages can contain embed content as well.


<div class="code-switcher show-cpp-false">
<div class="switcher" >
<span class="sw-bp" onclick="switchBp()">Blueprints</span><span class="sw-cpp" onclick="switchCpp()">C++</span>
</div>
<div class="cpp">

```cpp
#include "DiscordWebhookLibrary.h"

// ...

// Get information about the Webhook we want to execute.
FDiscordWebhookLibrary::GetWebhook
(
    9823290121, // Webhook Snowflake. 

    // Callback called when the information about the Webhook has been received.
    FDiscordGetWebhook::CreateLambda([](const FDiscordWebhook& Webhook) -> void 
    {
        FDiscordWebhookData MessageToSend;

        MessageToSend.Username    = TEXT("My UE4 Bot");        // Username displayed with the message
        MessageToSend.Avatar      = TEXT("...");               // Avatar displayed with the message
        MessageToSend.Content     = TEXT("Hello @everyone.");  // Message content.
            
        // MessageToSend.Embeds for embeds, MessageToSend.File for files, ...

        // Finally execute the Webhook.
        FDiscordWebhookLibrary::ExecuteWebhook
        (
            Webhook.Id,
            Webhook.Token,
            MessageToSend,
            FDiscordExecuteWebhook::CreateLambda([](const bool bExecuted) -> void
            {
                if (bExecuted)
                {
                    // Message posted.
                }
                else
                {
                    // An error occured, see the output log!
                }
            })
        );
    })
);
```

</div>
<div class="bp">
<div class="bpcode">
<textarea readonly>
</textarea>
<img src="https://github.com/Pandoa/DiscordFeatures/blob/master/Doc/BpExecuteWebhook.png?raw=true"/>
<button onclick="copyBlueprintCode(this)">Copy Code</button>
</div>
</div>
</div>
