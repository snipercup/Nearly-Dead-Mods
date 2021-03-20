# Propery list

This page lists properties defined in JSON. This list is useful if you want to mod the game and want to know what each property does.

## Common data
Property | Description
------------ | -------------
ID | An identifier for this item. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)
Name | The name as it appears in-game.
Description | The description of the entity as it will appear in-game.
Size | The amount of space it takes up in the inventory
Weight | The amount of kilograms the entity weighs
Price | The amount of dollars the item will sell for
Tags | Todo: Figure out what this is used for
Container type | Select a type of container here. The container type is defined elsewhere in the JSON. This determines if it contains items, liquids or solids
Is mergable | Wether or not the two items of the same kind can merge into a stack
Base stack | What amount will spawn when a full stack is spawned


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
