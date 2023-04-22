# Configuring the damage logs

After launching your server with the addon, it will generate a configuration file in your data folder.


> `gmod_server/garrysmod/data/damagelog/config.json`
> 
> `C:\Program Files (x86)\Steam\steamapps\common\GarrysMod\garrysmod\data\damagelog\config.json`

You can modify this file to change how the addon works.


<br><br>


## Older versions
Before version 3.6.0, configuration was done through the addon's file:<br>
`lua/damagelogs/config/config.lua`<br>

> **Note**: 
> **If you are on version 3.6.0 or later, do not modify this file!**
> 
> Otherwise, you may accidentally delete your configuration changes!<br>
> Use the JSON file mentioned at the top of this page.



<br>

---

<br>
<br>


# Configuration example
```json
{
	"Reports": {
		"MoreReportsPerRound": false,
		"ReportsBeforePlaying": false,
		"NoStaffReports": false
	},
	"DiscordWebhookMode": 0.0,
	"PrivateMessagePrefix": "[RDM Manager]",
	"AbuseMessageMode": 0.0,
	"ForcedLanguage": "",
	"RDM_Manager_Enabled": true,
	"HideDonateButton": false,
	"Autoslay": {
		"Autoslay_CheckCustom": false,
		"DefaultReason11": "Trolling",
		"DefaultReason9": "Prop kill",
		"DefaultReason3": "2x RDM",
		"DefaultReason5": "Mass RDM",
		"DefaultReason6": "Super Mass",
		"ShowRemainingSlays": false,
		"DefaultReason10": "Consistent RDM",
		"DefaultReason8": "Hacking",
		"DefaultReason1": "Random Damage",
		"DefaultReason2": "RDM",
		"DefaultReason12": "Minge",
		"ULX_Autoslay_ForceRole": false,
		"DefaultReason": "Breaking Rules",
		"DefaultReason4": "Attempted Mass",
		"DefaultReason7": "Ghosting",
		"ULX_AutoslayMode": 1.0
	},
	"Use_MySQL": false,
	"LogDays": 61.0,
	"UseWorkshop": true,
	"Commands": {
		"RDM_Manager_Command": "!report",
		"Respond_Command": "!respond"
	},
	"Key": 99.0,
	"Permissions": {
		"owner": {
			"access_level": 4.0,
			"can_access_rdm_manager": true
		},
		"founder": {
			"access_level": 4.0,
			"can_access_rdm_manager": true
		},
		"admin": {
			"access_level": 4.0,
			"can_access_rdm_manager": true
		},
		"superadmin": {
			"access_level": 4.0,
			"can_access_rdm_manager": true
		},
		"operator": {
			"access_level": 3.0,
			"can_access_rdm_manager": false
		},
		"user": {
			"access_level": 2.0,
			"can_access_rdm_manager": false
		}
	},
	"Ban": {
		"DefaultReason6": "Super Mass",
		"DefaultReason7": "Ghosting",
		"DefaultReason8": "Hacking",
		"DefaultReason11": "Random Damage",
		"DefaultReason1": "Random Damage and leave",
		"AllowBanningThruManager": true,
		"DefaultReason2": "RDM and leave",
		"DefaultReason12": "Trolling",
		"DefaultReason3": "2x RDM and leave",
		"DefaultReason10": "Attempted RDM",
		"DefaultReason4": "Attempted Mass and leave",
		"DefaultReason9": "Consistent RDM",
		"DefaultReason5": "Mass RDM"
	}
}
```

<br><br><br><br>

---

<br>

# Configuration Breakdown
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| AbuseMessageMode | number | 0 | When set to 1, a message will be shown to all players when an alive player/admin opens the damage logs. |
| Autoslay | object |  | See [autoslay settings](#autoslay-settings) |
| Ban | object |  | See [ban settings](#ban-settings) |
| Commands | object |  | See [command settings](#command-settings) |
| DiscordWebhookMode | number | 0 | Enables/disables Discord notifications for reports. See [Discord Notifications](https://github.com/BadgerCode/tttdamagelogs/wiki/Discord-Notifications#4-enable-discord-notifications) |
| ForcedLanguage | string | "english" | Force the damage logs to use the same language for all players.<br>This shouldn't ever be used, as players can pick their preferred language.<br>Use the name of a language in `lua/damagelogs/shared/lang` |
| HideDonateButton | boolean | false | Hide the Donate button on the top-right corner.<br>Donations are made to the original addon author- Tommy228 |
| Key | number | 99 | The keyboard key used to open the damagelogs. Default is F8 (99). See [keys](https://wiki.facepunch.com/gmod/Enums/KEY#KEY_F1) |
| LogDays | number | 61 | The number of days to keep logs for. Older logs are deleted on map change. |
| Permissions | object |  | See [permission settings](#permission-settings) |
| PrivateMessagePrefix | string | "[RDM Manager]" | The damage logs allows admins to private message players. This text will appear at the start of the message. |
| Reports | Object | | Contains various report-related settings. See [Report settings](#report-settings) |
| RDM_Manager_Enabled | boolean | true | Enables/disables the RDM manager part of the damage logs addon |
| Use_MySQL | boolean | false | Enables/disables using a MySQL database to store old logs.<br>When false, SQLite will be used (`gmod_server/garrysmod/garrysmod/sv.db`) |
| UseWorkshop | boolean | true | When true, custom content required by the addon (e.g. notification sounds) will be downloaded via a workshop addon- [TTT Damagelogs content](https://steamcommunity.com/sharedfiles/filedetails/?id=1129792694) |




<br><br><br><br>

## Autoslay settings
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| Autoslay_CheckCustom | boolean | false | Automatically tick the "Custom slay reason" tickbox |
| DefaultReason | string | "Breaking Rules" | One of the options for the slay reason. |
| DefaultReason... | string | "Random Damage" | 12 extra options for the slay reason.<br>DefaultReason1, DefaultReason2, ..., DefaultReason12 |
| ShowRemainingSlays | boolean | false | When true, at the start of the round, all players will be notified of any players that have remaining slays. |
| ULX_Autoslay_ForceRole | boolean | true | Force autoslain players to be innocents (ULX/SAM only).<br>Do not enable this if another addon interferes with roles (Pointshop roles for example) |
| ULX_AutoslayMode | number | 1 | 0: Disable autoslay<br>1: Enables auto-slay system (!aslay, !aslayid)<br>2: Enables auto-jail system (!ajail, !ajailid) |

<br><br><br><br>


## Ban settings
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| AllowBanningThruManager | boolean | true | Allow admins to ban players through the RDM manager |
| DefaultReason... | string | "Random Damage and leave" | 12 options for the ban reason.<br>DefaultReason1, DefaultReason2, ..., DefaultReason12 |

<br><br><br><br>


## Command settings
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| Respond_Command | string | "!resond" | The chat command players can type to respond to an RDM report made against them. |
| RDM_Manager_Command | string | "!report" | The chat command players can type to report another player of RDMing. |

<br><br><br><br>


## Permission settings
A dictionary of permissions, where the key is the role name and the value is the permission settings.

**Example**
```json
{
    "owner": {
        "access_level": 4.0,
        "can_access_rdm_manager": true
    },
    "founder": {
        "access_level": 4.0,
        "can_access_rdm_manager": true
    }
}
```

<br>

### Permissions
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| access_level | number | 4 | 4: Can always view the logs of the current round.<br>3: Can only view the logs of the current round when spectating.<br>2: Can never view the logs of the current round.<br>1: Same as 2, but the player also cannot see "Logs before your death" when reporting someone. |
| can_access_rdm_manager | boolean | true | Allows players with this role access the RDM manager.<br>Should only be given to administrator/moderator roles. |

<br><br><br><br>



## Report settings
| Setting | Type | Example | Description |
| -- | -- | -- | -- |
| MoreReportsPerRound | boolean | false | Allow more than 2 reports per round |
| NoStaffReports | boolean | false | Allow reports even with no staff online |
| ReportsBeforePlaying | boolean | false | Allow reports before playing |
