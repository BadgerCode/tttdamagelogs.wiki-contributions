You can modify the code for TTT weapons and entities to provide more information for the damage logs.<br>
This is done by calling the hook `TTTEquipmentUse`.

# Example
```lua
-- In your weapon's code

function SWEP:PrimaryAttack()
    local playerUsingEquipment = self:GetOwner()
    local equipment = self
    local description = "C4 placed"
    hook.Call("TTTEquipmentUse", nil, playerUsingEquipment, equipment, description)
end
```