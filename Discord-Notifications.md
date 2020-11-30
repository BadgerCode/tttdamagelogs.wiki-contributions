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

<br>


## Enabling Discord Notifications

> **NOTE**: Discord's servers block requests from Garry's Mod servers.
> 
> You will need to proxy all of your discord notifications through a website. <br>
> See [this issue](https://github.com/BadgerCode/tttdamagelogs/pull/2)

<br>

### 1. Create a Discord Webhook URL
_You must have edit channel permissions_

1. In Discord, right click on the channel you want notifications to appear in
2. Select Edit Channel
3. Go to Integrations
4. View Webhooks
5. New Webhook
6. Fill in the information and click "Copy Webhook URL"

<br>

### 2. Set up your Discord Proxy Website
1. As mentioned before, Discord blocks requests from Garry's Mod servers
2. Set up your proxy website to use the webhook URL you made in step 1
3. Write down the URL to your discord proxy
    * E.g. https://example.com/report-notifications

<br>

### 3. Set up your GMod server's configuration
Open the file `garrysmod/cfg/server.cfg` on your server.

Add the line:<br>
```
ttt_dmglogs_discordurl "https://example.com/report-notifications"
```

_Replace `https://example.com/report-notifications` with the URL to your Discord Proxy Website in step 2._

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
