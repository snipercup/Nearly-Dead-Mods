# Propery list

This page lists properties defined in JSON. This list is useful if you want to mod the game and want to know what each property does.

## Common properties
These are properties that are shared between multiple item types

#### General
Property | Description
------------ | -------------
ID | An identifier for this item. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)
Name | The name as it appears in-game.
Description | The description of the entity as it will appear in-game.

#### Common data
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

#### Activating data
Property | Description
------------ | -------------
Method type | Todo: Figure out what this is used for

#### Throw data
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

#### Material data
Property | Description
------------ | -------------
Set charging type | This allows you to set how much this item will charge another item/furniture with. For example, a campfire will accept items that have 'charging type' set to 'flammable'.
Can disassemble | Wether or not the item can be disassembled. When enabled, it allows you to set the requirements and results of disassembly
Required tool quality | The tool qualities used to disassemble this item. The player needs to have tools that have these qualities in order to succesfully disaassemble the item.
Skill difficulty | What skills are required to disassemble the item
Disassemble data | What items and how many will result from the disassembly.

#### Item type
Property | Description
------------ | -------------
Item type | The type of item. Changing this will cause the available properties to set. For example, if you change the item type of a plastic chunk from component to weapon, you can configure damage types and amounts for it. If you change the weapon type for plank from weapon to component, it loses the weapon data that was previously configured.

#### Is liquid
Property | Description
------------ | -------------
Is liquid | Wether or not this item is liquid. If enabled, the item can no longer be held in your hands but can be stored in container that can contain liquids.


## Item type food
Property | Description
------------ | -------------
Expiration date | Days before the item can no longer safely be consumed. Use -1 to keep it from expiring
Fun | The amount your morale increases when consuming this item


## Item type weapon

#### General
Property | Description
------------ | -------------
ID | An identifier for this item. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)
Name | The name as it appears in-game.
Bone type | This is probably used when the item is displayed on the character, for example when wielding
Description | The description of the entity as it will appear in-game.

#### Action set
Property | Description
------------ | -------------
Available unique actions | TODO
Available action sets | You set the actions that you can use the tool for here. They are used in key settings (below)
Key setting | You can define what action is performed when the controls trigger an action
Wield main | This probably describes the action that is preformed when you are wielding the item as a main weapon
Wield sub | This probably describes the action that is preformed when you are wielding the item as a sub weapon (when dual wielding?)

#### Weapon data melee
Property | Description
------------ | -------------
Aim type | TODO
Melee weapon data | You set the melee weapn data like damage here
Melee damage | The amount of dmaage it deals when hitting an enemy with a melee attack
Melee attack speed | The speed at wich the attacks are performed
Melee range | The distance the weapon can reach
Break Balance | This is probably used to give a weapon a chance to stagger, push or knock an enemy down
Staggering | TODO probably a chance to stagger
Falling | TODO probably a chance to push an enemy down
Knockback | TODO probably a chance to knock an enemy back
Equip type | This property tells the game to equip the weapon as a main or as a sub weapon
Set effect | This allows you to enable the weapon to change the stat of the enemy when dealing melee damage. For example, increas or decrease the strength of the enemy
Effect type | Select the type of effect you want the weapon to have. For example, if you want to decrease the strenght of the enemy when it is hit by this weapon, select mod_stat and press add new effect and select strength and add a magnitude. (TODO can magnitude have postive and negative values?)

#### Weapon data ranged
Property | Description
------------ | -------------
Is ranged weapon | If this is disabled the weapon is a melee weapon. If this is enabled it can be used as a ranged weapon. You need to enable it to see the properties described below
Ammo capacity | The maximum amount of ammunition it can contain
Reload one by one | Wether or not the weapon is reloaded one bullet at a time
Ammo type | The type of ammo it uses
Ranged damage type | Allows you to set the damage type dealt when hitting an enemy with a ranged attack
Shooting type | The type of shooting the weapon performs (TODO: Describe types)
Shooting mechanism | TODO
Targeting skill ID | The skill used to succesfully target an enemy
Ranged damage | The amount of ranged damage dealt
Ranged attack speed | The speed at wich the weapon performs ranged attacks
Max range | The maximum range of the weapon
Ranged accuracy | The accuracy of ranged attacks
Projectile speed modifier | This is probably used for bows and allows you to make the same arrow go faster depending on the bow used. (TODO can be negative?)
Can fire single | Wether the weapon supports single shot mode
Can fire auto | Wether or not the weapon supports auto fire mode
Can fire burst | Wether or not the weapon supports burst fire mode
Burst count | The amount of bullets fired when the weapon is set to burst mode. You need to enable 'can fire burst' to see this property.
Recoil | The amount of recoil when firing the weapon
Use magazine | Wether a magazine is supported in this weapon

#### Item weapon type
TODO what effect does this have in-game?

#### Mod type
TODO Probably what types of weapon mods are supported


#### Set sprite
Property | Description
------------ | -------------
Preview | Shows a preview of the sprite when it is wielded
Select status | Changes the preview depending on the selected status. Previous and next buttons changes the status.
Add sprite | Sets the sprite for the status that is selected in the 'select status' property. If you add multiple sprites, it will allow you to have parts behind the hand and parts in front of the hand, depending on the layer (see below)
Remove sprite | Will remove the sprite for the selected status
Select sprite | Select one of the sprites for the selected status. Use previous and next buttons to cycle trough the sprites
Select layer | Select the layer at which the sprite is shown in-game. TODO we probably need a good overview of the layters that can be selected here.
Sprite input | This field does not have a name but is below 'select layer'. It allows you to select a sprite from the assets.
Sprite name | Set the name for the sprite as it will appear in the drop-down at 'select sprite'
Priority | TODO
Synchronize color preset | TODO
Position | How much the sprite is shown off-center. For a weapon, you want it to appear on the hand
X | The horizontal position. 0 means center. A negative value moves it to the left. A positive value moves it to the right.
Y | The vertical position. 0 means center. A negative value moves it up. A positive value moves it down.
Use frame animation | Allows you to set extra frames for an animation in-game
Manual frame | TODO
Add frame | Allows you to select a sprite that will act as a frame for this animation



#### GFX data
Allows you to set special effects when using this weapon.

Property | Description
------------ | -------------
Call action type | Shows the name of the call ID you added previously at 'Add new call ID' (see below)
Action clip | You can set a custom name here (if an input field is not available, click 'add gfx' first)
GFX ID | The ID of the special effect
Distance | TODO maybe the distance it travels?
GFX Scale | X: The horizontal scale. Y: The vertical scale
Hit GFX | The special effect shown when the enemy is hit
Add GFX | Adds a new special effect to the call action type you are currently working in
Duplicate GFX | Duplicates the special effect to a new line
Remove GFX | Removes the special effect line
Add new call ID | Lets you set a new call ID TODO no idea if these ID's are defined somewhere or you can make something up.


## Container data
These fields are visible when 'Container type' is set to a value, for example 'charging_storage' or 'Bottle'. The fields below are listed for each type.

#### Pack
Property | Description
------------ | -------------
Container capacity size | Todo: Figure out what this is used for
Contain item ID | Todo: Figure out what this is used for
Empty bottle ID | Todo: Figure out what this is used for
Use own GFX | Todo: Figure out what this is used for

#### Bottle
Property | Description
------------ | -------------
Container capacity size | Todo: Figure out what this is used for.
Contain liquid ID | The liquid it contains when it is spawned. For example: 'canned cola' has this set to 'cola'
Empty bottle ID | The item that is returned when bottle is empty. For example: 'canned cola' has this set to 'opened_aluminium_can'
Use own GFX | Todo: Figure out what this is used for

#### Magazine
Property | Description
------------ | -------------
Container capacity size | Todo: Figure out what this is used for.
Ammo type | Select the ammo type this container will be able to hold.
Bullet count | The maximum amount of ammunition this container can hold.
Use own GFX | Todo: Figure out what this is used for

#### Charging_storage
Property | Description
------------ | -------------
Charging type | The type of material this container is charged with. For example, a battery would be charged with electric_power
Default amount | The amount of charges this item is spawned with
Max amount | The maximum amount of charges this item can hold
Delta per hour | Todo: Figure out what this is used for

#### Add_to_Baee_Inventory
Property | Description
------------ | -------------
Capacity | Todo: Figure out what this is used for

#### None
The default value. Use this to indicate that the item is not a container

## Recipes

#### General
Property | Description
------------ | -------------
ID | An identifier for this recipe. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)
Name | The name as it appears in-game.

#### Common data
Property | Description
------------ | -------------
Description | The description of the entity as it will appear in-game.
Time | The time used to make this (seconds?)
partial_time | TODO
Autolearn | If anabled, you can set the conditions for when the recipe is learned. If disabled, the player needs to learn this recipe from a book or something else.
Autolearn skill type | The type of skill used to determine when the recipe is learned
Skill level | The level of the skill that is required to learn the recipe
Recipe main category | This sets under which main tab in the crafting menu the recipe will appear
Recipe sub category | This sets under which sub tab in the crafting menu the recipe will appear
Animation call ID | TODO

#### Recipe result
Property | Description
------------ | -------------
Result item ID | The item that results from the recipe when crafting. May contain more then one item
Result item count | The amount of items that will result from this recipe. You can set this for each item that is returned.

#### Required tool quality
This allows you to set the quality of the tools needed to craft the recipe. 

#### Skill difficulty
Property | Description
------------ | -------------
Skill ID | The skill that is required to craft this recipe. It's possible to add more then one skill to increase difficulty.
Level | The level of skill required to craft this recipe.

#### Recipe component
Here you can set the items used while crafting this recipe

##### Consume component
These items will be consumed when making this recipe

Property | Description
------------ | -------------
Component ID | The ID of the item that is required to craft this recipe. Multiple components may be configured
Amount | The amount of the item required to craft this recipe

##### Don't consume component
These items will not be consumed when making this recipe. For example, a pan

Property | Description
------------ | -------------
Component ID | The ID of the item that is required to craft this recipe. Multiple components may be configured
Amount | The amount of the item required to craft this recipe

##### Material component
The material used in this recipe. 

Property | Description
------------ | -------------
Material ID | The ID of the material that is required to craft this recipe. Multiple materials may be configured
Amount | The amount of the material required to craft this recipe


#### Consuming condition
TODO. I think this allows you to set the required level of stamina, health etc. for making this recipe. 




## Furniture
Furniture can be recognized by having the type set to object. Type is visible in the JSON. In the modding tool you can see (Object) next to the ID in the JSON entry list of the file you selected.

#### General
Property | Description
------------ | -------------
Object name | The name as it appears in-game.
ID | An identifier for this object. Don't use spaces. Has to be unique for the type of entity (for example, no two tools can be identified as 'hammer' at the same time, but you can have one 'hammer' tool and one 'hammer' recipe)

#### Parcour data
Property | Description
------------ | -------------
Can parcour | Wether or not the player can vault over this object
Select UI icon | Allows you to set an icon for the UI that resembles the parcour action when you are standing close to the furniture
Parcour text | This is probably shown when the action is selected or executed
Animation call ID | Probably a reference to an animation
Speed multiflier | Changes the movementspeed of the character performing the parcour. 0.5 is half speed


#### Other
Property | Description
------------ | -------------
Capacity size | The capacity of this furniture. If you set this number to more then 0 you get additional options (see below) TODO what does this number reprisent? Liters? Big metal cabinet has 120 for reference
Search icon | Allows you to set the icon that appears when you are close enough to search it. This field is only visible if 'capacity size' is greater then 0.
Search text | The text that appears when you perform the search action. This field is only visible if 'capacity size' is greater then 0.
Max durability | This number represents the damage the furniture can sustain before being destroyed. Big metal cabinet has 1000 for reference.
Armor type | The type of armor this furniture has. This derermines the resistence to certain types of damage.
Show armor points | Shows the actual resistence values of the selected armor type
Size | How many tiles of space this furniture takes up. A chair takes up 1 by 1 but a big metal cabinet takes up 2 by 1
Set interaction | Allows you to set how the player can interact with this furniture. Not required for search or parcour actions.
Interaction object | Shows the action that has been selected for this object. You can add a new action by pressing 'Add new action'
Default interaction | The interaction that the game defaults to when multiple actions are possible. For example, the default action for bed is sleep, but you can also select disassemble.
Has tool function | If enabled, you can set the tool qualities for this furniture. 
Wreckage ID | The ID of the object that appears when you demolish the furniture in-game
Demolishing GFX | The special effect when the furniture is demolished



#### Dissassemble data
Property | Description
------------ | -------------
Can disassemble | Wether or not the furniture can be disassembled. Enabling this shows the options below
Disassembling data | Shows various options for disassembling the furniture
Select icon | The UI icon that represents the disassembly action for this furniture
Disassemble text | The text that appears in the UI in-game
Result item | Allows you to set a list of the items and the amounts that result from disassembling the furniture. A random amount of items will appear based on the min and max values.
Required skill level | The skills required to disassemble the furniture TODO figure out what max skill level means
Required tool level | The tool quality levels required to disassemble this furniture. TODO figure out what max quality level means
Time (min) | The time in minutes required to disassemble this furniture



#### Destruction remain items
Property | Description
------------ | -------------
Remaining item | A list of items that will remain when the furniture is destroyed. A random amount will be selected somewhere between the min and max values specified.


#### Resource storage
Property | Description
------------ | -------------
Charging type id | The ID of the type of charges it can hold
Default storage | The amount of charges it spawns with
Max storage | The maximum amount of charges it can hold
Delta per hour | TODO figure out what this means
Can import manually | This probably means you can feed charges by hand
Can export manually | This probably means you can remove charges by hand



#### Activating effect
This allows you to transform the furniture into something else. This is useful for deploying/folding or arming furniture. You first need to set the target type and then press change effect type

Property | Description
------------ | -------------
Change effect type | Allows you to set the properties of the selected target type
Transform object | The furniture this object transforms into.
Activating icon | The UI icon that represents the activation action in-game
Activating text | The text that appears when the activating action is selected
Target type | The type of activation you want to apply to this furniture. Each type offers different options. Press 'change effect type' each time you make a selection.

*For object_transform only*
Property | Description
------------ | -------------
Required resources | Sets the required resources for the transform action
Spending resource ID | Sets the ID of the resource that has to be spent in order to transform the furniture
Spend amount | How much of the resource is required to perform the transform action
Sound effect | The sound effect that plays when the transform is occurring

*For object_transform_automatic only*
Property | Description
------------ | -------------
Can activate manually | If enabled, the transform can be triggered manually. If disabled, only the configured trigger will activate the transormation (see below)
Trigger charging type ID | What type of charge will be used to determine if it triggers
Trigger type | Select between full_charging_type and lack_of_charging_type. Selecting the first one will trigger the furniture transform when it's fully charged. Selecting the second one will trigger the transform when all charges are consumed.

*For object_transform_with_function only*
Property | Description
------------ | -------------
Giving item | This probably allows you to set an item that the player will recieve when the object is transformed
Required skill level | The skill level required for the transformation to be activated
Required tool level | The tool qualities that need to be in your posession in order to activate the transformation
