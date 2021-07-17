# Configuring the damage logs
Most of the configuration is done through a lua configuration file: `lua/damagelogs/config/config.lua`<br>
The current version of this file can be found here - [tttdamagelogs/lua/damagelogs/config/config.lua](https://github.com/BadgerCode/tttdamagelogs/blob/master/lua/damagelogs/config/config.lua)

<br>

> **Note**: When updating your copy of the damage logs addon, backup your configuration files!
> 
> Otherwise, you may accidentally delete your configuration changes!


<br>

---

# Damagelog.UseWorkshop
`Default value: true`

When true, clients will download the custom content for the damage logs via the following workshop addon:<br>
https://steamcommunity.com/sharedfiles/filedetails/?id=1129792694

The custom content includes the notification sounds used when a player is reported.

Set this to false if you wish to use FastDL instead.

<br> 

---

# Damagelog.ShowRemainingSlays
`Default value: false`

When true, on round start, all players are informed of any players that have slays remaining.

![remaining slays](https://user-images.githubusercontent.com/5206198/126043953-088034e1-d5fc-4e31-8096-6507ce235f9d.png)


