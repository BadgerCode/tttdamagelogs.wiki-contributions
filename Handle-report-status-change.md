When an admin changes the status of a report, a custom event (hook) will be emitted.<br>
This hook may be useful if you wish to log report status changes to Discord.

![preview of setting report status](https://i.imgur.com/dY9ST1B.png)

# Details
Hook name: `RDMManagerStatusUpdated`

## Parameters
| Name | Example | Description |
| -- | -- | -- |
| ply | Player [1][Badger] | The player **entity** of the admin that changed the report status |
| reportId | 1 | The report number. Use this to identify one report from another. Report numbers start again from 1 on map change. |
| newStatus | 2 | The new status of the report.<br>1: Waiting<br>2: In progress<br>3: Completed |
| isReportFromPreviousMap | true | Is this report from the previous map. true = this report is from the previous map |


# Example
```lua
-- Replace "myaddon" in the two lines below with some unique name for your addon
hook.Remove("RDMManagerStatusUpdated", "myaddon_RDMManagerStatusUpdated")
hook.Add("RDMManagerStatusUpdated", "myaddon_RDMManagerStatusUpdated", function(ply, reportId, newStatus, isReportFromPreviousMap)
    local reportStatus = "unknown"
    if(status == 1) then reportStatus = "waiting"
    elseif(status == 2) then reportStatus = "in progress"
    elseif(status == 3) then reportStatus = "completed"

    local map = isReportFromPreviousMap ? "previous map" : "current map"

    print(string.format("The admin %s has changed the status of report %d (%s) to %s",
        ply:Nick(),
        reportId,
        map,
        reportStatus
    ))
```

## Output
```
The admin Badger has changed the status of report 1 (current map) to waiting
The admin Badger has changed the status of report 1 (current map) to in progress
The admin Badger has changed the status of report 1 (previous map) to waiting
```


