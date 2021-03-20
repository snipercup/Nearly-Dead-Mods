# Propery list

This page lists properties defined in JSON. This list is useful if you want to mod the game and want to know what each property does.

## Common properties
These are properties that are shared between multiple item types

### General
Property | Description
------------ | -------------
ID | An identifier for this item. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)
Name | The name as it appears in-game.
Description | The description of the entity as it will appear in-game.

### Common data
Property | Description
------------ | -------------
Size | The amount of space it takes up in the inventory
Weight | The amount of kilograms the entity weighs
Price | The amount of dollars the item will sell for
Tags | Todo: Figure out what this is used for
Container type | Select a type of container here. The container type is defined elsewhere in the JSON. This determines if it contains items, liquids or solids
Is mergable | Wether or not the two items of the same kind can merge into a stack
Base stack | What amount will spawn when a full stack is spawned
Is tool | Wether or not this item can be used as a tool while crafting. If this is enabled, it allows you to set a tool quality to this item.
Set tool data | Configure what tool qualities this item has. This determines what recipes will be able to use this tool.

### Activating data
Property | Description
------------ | -------------
Method type | Todo: Figure out what this is used for

### Throw data
Property | Description
------------ | -------------
Can throw | If this is enabled, the player can throw this item. You can set the amount of damage etc. once it it is enabled.
Damage type | The type of damage that will be dealt when this item is thrown and hits the enemy
Damage | The amount of damage it will deal when it hits an enemy
Accuracy | How accurate the item can be thrown
Max range | Determines the maximum distance the item can be thrown
Projectile speed | The speed at wich the item travels when thrown
Use GFX | Todo: Figure out what this is used for. Probably a special effect
Set throwing GFX | Only visible when 'Use GFX' is enabled. Todo: Figure out what this is used for
Throwing SFX | The sound effect that plays when the item is thrown

### Material data
Property | Description
------------ | -------------
Set charging type | Todo: Figure out what it is used for. It is used in composite_fiber_thread
Can disassemble | Wether or not the item can be disassembled. When enabled, it allows you to set the requirements and results of disassembly
Required tool quality | The tool qualities used to disassemble this item. The player needs to have tools that have these qualities in order to succesfully disaassemble the item.
Skill difficulty | What skills are required to disassemble the item
Disassemble data | What items and how many will result from the disassembly.

### Item type
Property | Description
------------ | -------------
Item type | The type of item. Changing this will cause the available properties to set. For example, if you change the item type of a plastic chunk from component to weapon, you can configure damage types and amounts for it. If you change the weapon type for plank from weapon to component, it loses the weapon data that was previously configured.


## Item type food
Property | Description
------------ | -------------
Expiration date | Days before the item can no longer safely be consumed. Use -1 to keep it from expiring
Fun | The amount your morale increases when consuming this item


## Item type component
Property | Description
------------ | -------------
Expiration date | Days before the item can no longer safely be consumed. Use -1 to keep it from expiring
Fun | The amount your morale increases when consuming this item
