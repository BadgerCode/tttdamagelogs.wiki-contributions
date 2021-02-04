You can enable Discord notifications for report events and have them sent to a specific channel in your Discord server.<br>
The following events will result in a Discord notification:

* Report Submitted
* Report Forgiven
* Report Kept
* Report Finished (by an admin)
* Report Conclusion Changed (by an admin)

## Example
Badger reports Bot01:<br>
![report-submitted](https://i.imgur.com/3wsIjfr.png)

Bot01 responds, but Badger decides to keep the report:<br>
![report-kept](https://i.imgur.com/k1a4Nek.png)

The admin Badger handles the report and sets the status to "Finished":<br>
![report-finished](https://i.imgur.com/kHZtEDu.png)

<br>

For more examples, see [this imgur album](https://imgur.com/a/kKgondH).

<br><br>

---

<br>


## Enabling Discord Notifications

<br>

### 1. Install CHTTP
_Discord blocks requests from Garry's Mod clients/servers using the built-in HTTP capabilities._<br>
_You must the CHTTP Lua module (recommended) or use a proxy HTTP server (hard)._

1. Go to https://github.com/timschumi/gmod-chttp/releases
2. Download the correct version
    * If you are running on a **Windows server**, on the **32-bit Gmod branch** (currently the default branch for servers)
        * Download `gmsv_chttp_win32.dll`
    * If you are running on a **Windows server**, on the **x86-64 Gmod branch**
        * Download `gmsv_chttp_win64.dll`
    * If you are running on a **Linux server**, on the **32-bit Gmod branch** (currently the default branch for servers)
        * Download `gmsv_chttp_linux.dll`
    * If you are running on a **Linux server**, on the **x86-64 Gmod branch**
        * Download `gmsv_chttp_linux64.dll`
3. If it does not already exist in your server's files, create the `garrysmod/lua/bin/` folder on your server.
    * E.g. If your Garry's Mod server is located at `myserver/garrysmod/gameinfo.txt`
    * Then this folder should be made at `myserver/garrysmod/lua/bin`
4. Drop the file you downloaded into this folder

_Thanks to [GMod Store](https://www.gmodstore.com/help/addon/6016/discord/topics/curl-http) for this guide._

<br>

### 2. Create a Discord Webhook URL
_You must have edit channel permissions_

1. In Discord, right click on the channel you want notifications to appear in
2. Select Edit Channel
3. Go to Integrations
4. View Webhooks
5. New Webhook
6. Fill in the information and click "Copy Webhook URL"

The webhook URL should look something like `https://discord.com/api/webhooks/700000000123456789/EXAMPLEEXAMPLEEXAMPLE`

<br>

### 3. Set up your GMod server's configuration
1. Open the file `garrysmod/cfg/server.cfg` on your server.
2. Add the line - `ttt_dmglogs_discordurl "https://discord.com/api/webhooks/700000000123456789/EXAMPLEEXAMPLEEXAMPLE"`
3. Replace `https://discord.com/api/webhooks/700000000123456789/EXAMPLEEXAMPLEEXAMPLE` with the Discord Webhook URL in step 2.

<br>

### 4. Enable Discord Notifications
Open the configuration file for your copy of the damage logs addon:<br>
`lua/damagelogs/config/config.lua`


Find the following line:
```lua
Damagelog.DiscordWebhookMode = 0
```

And replace it with:
```lua
Damagelog.DiscordWebhookMode = 2
```

<br>

If you only want report notifications when there are no admins online, replace the line above with:<br>
```lua
Damagelog.DiscordWebhookMode = 1
```

<br><br>

## Using Discord notifications without CHTTP

If you don't want to use the CHTTP module, you can proxy your Discord notifications through a website.

GMod server => Website => Discord API

This requires some experience with creating web services.

In `garrysmod/cfg/server.cfg`, set the `ttt_dmglogs_discordurl` to your proxy website URL.<br>
E.g.<br>
`ttt_dmglogs_discordurl "https://example.com/report-notifications"`
