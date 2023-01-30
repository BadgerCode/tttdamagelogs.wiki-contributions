# Prerequisites

* Update version in version.md (e.g. 3.3.4)
* Update version in `tttdamagelogs/lua/autorun/damagelog_autorun.lua` (e.g. 3.3.4)
* Test with bots- Kill some bots, damage some bots, check the current round logs, check old logs, create a report (see [Testing Guide](Testing-Guide))
* (Optional) Test the addon with other players
* (Optional) Release a beta


# Create release on GitHub
https://github.com/BadgerCode/tttdamagelogs/releases

* Tag: E.g. `v3.3.4`
* Title: E.g. `v3.3.3 - Major bug fixes`
* Description

```markdown
To download the update, follow the steps in the [Installation Guide](https://github.com/BadgerCode/tttdamagelogs#installation).

> **Note**: When updating your copy of the damage logs addon, backup your configuration files!
> 
> Otherwise, you may accidentally delete your configuration changes!

[Read more](https://github.com/BadgerCode/tttdamagelogs/wiki/Configuring-the-damage-logs)

---

<br>

# Release Notes

## Bug Fixes
* #22 - Fixes some issue (this should link to the pull request)
    * Fixes #16 (this should link to related issues)
    * Thanks X (person that fixed the issue)


## Features
* #123 - Description of feature (link to pull request)
    * Thanks X (person that added the feature)
```



# Release to workshop
* Open the project's folder in [VS Code](https://code.visualstudio.com/)
* Publish using the [GMod SDK](https://marketplace.visualstudio.com/items?itemName=BadgerCode.gmod-sdk)
    * [TTT Damage Logs & RDM Manager 2306802961](https://steamcommunity.com/sharedfiles/filedetails/?id=2306802961)
