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
Set liquid data | Select the ID of the liquid that applies to this item


## Item type food

#### General
Property | Description
------------ | -------------
Expiration date | Days before the item can no longer safely be consumed. Use -1 to keep it from expiring
Fun | The amount your morale increases when consuming this item
Consume icon | The UI icon that represents the consume action in-game
Consume text | The text that will appear when the consume action is selected in-game
Consuming time | The time in minutes it take to consume this item
Have by-product | When enabled, allows you to set the item that will spawn when this item is consumed. Probably used for wrappers/peels.
Item ID | Select the ID of the item that will appear as by-product. Only visible if 'Have by-product' is enabled.
Item count | The amount of items that will appear as a by-product. Only visible if 'Have by-product' is enabled.


#### Consume effect
Allows you to set the effect of consuming this item like hunger and thirst but also allows mutation.

Property | Description
------------ | -------------
Condition ID | The ID of the condition to be affected
Magnitude | How much effect this food item has on the selected condition
Add consume effect | Allows you to add a new consume effect.


#### Flavor
This is probably used to affect mood, or maybe this comes into play when the character has a preference for sertain flavors?

Property | Description
------------ | -------------
Flavor data | Select the flavors that apply to this food item.


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
When producing items, you can set the condition value of stamina, HP, etc. to be consumed. 




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



#### Set rendering
Property | Description
------------ | -------------
Rendering type | TODO
Is passable | This probably means you can move trough the furniture. Maybe in case of a door frame?
Pass light | Wether light passes trough this furniture
Pass bullet | wether or not bullets will pass trough this furniture
has light | Enabling this will make this furniture emit light in-game. You need to enable this in order to see the options below
Light intensity | The inensity of the light TODO what values to use
Light range (pixel) | The range of the light in pixels
Light color | The color of the light



#### Set sprite
Property | Description
------------ | -------------
Durability ratio | Allows you to set levels of durability before the sprite changes. This is useful to make furniture appear damaged. You need to set sprites for each level of durablity (see below)
Capacity ratio | This probably allows you to set capacity levels for the damage levels of this furniture TODO: Do these levels correspond to the durability ratio's?
Sprite properties | Allows you to set the northward, southward, eastward and westward sprites for this furniture for each durablilty ratio.
copy from | Copies the sprites from one of the other directions. This is useful for furniture that has limited orientations, like a round table
Base | Configure the sprite that will show when the furniture is at full durability
Durability sprites | Set the sprite for each level of durability you configured in 'Durability ratio'. 
Has animation | If enabled, it allows you to set the frames that will make up the animation for this furniture. To see the properties below, you need to enable this first
Set animation | If there are no frames, click add new frame. You can set a sprite per frame and the time the frame will be visible for. You can add as many frames as you want TODO: Will only the base durability be animated? What about the other damage ratios?





#### Set collider
Property | Description
------------ | -------------
Pivot | A preview of the collision box for each of the north, east, south and west directions. You can control this with the pivot x (see below)
pivot x | Allows you to align the furniture with the collision box. A smaller number will move the sprite to the left. A bigger number moves the sprite to the right



#### Set local position
This is probably used for furniture that the player can mount or sit on, like a bed. This allows you to configure the position of the player sprite on the furniture when mounted/sat on

Property | Description
------------ | -------------
New local position | Select the local position you want to add and click 'Add local position'
Add local position | Adds the local position for the position selected in 'new local positoin'
Direction | For each direction, the position and rotation can be configured (see below)
X | The horizontal offset of the player sprite in relation to the sprite of the furniture. Making this bigger will move the player sprite to the right
Y | The vertical offset of the player sprite in relation to the sprite of the furniture. Making this bigger will move the player sprite downward






#### Set sound effect
Property | Description
------------ | -------------
Hit sound | Select the sound effect that plays when the furniture is hit
Destruction sound | select the sound effect that plays when the furniture is destroyed


## Creature



#### General
Property | Description
------------ | -------------
Name | The name of the creature
ID | Something to identify this creature. Don't use spaces
Select bone type | This will determine what animations will work with this creature. 'Bone' refers to the bones in the animation skeleton on top of which the sprites will be projected. This has nothing to do with what's inside the character's flesh.
Is playable | Turning this on probably allows you to select this as a race in the character creation menu
Faction | This button has no actual label, but it's shown below 'is playable' and it probably refers to faction.



#### Preview image and trace
Property | Description
------------ | -------------
Preview image | No idea what function this has other then to get a picture of what this creature looks like. You can enter an image from the assets tree. It's not required.
Trace | Put an image here that represent the tracks this creature leaves behind (frootprints)
Trace selected | Put an image here that represent the tracks while they are selected
Trace highlighted | Put an image here that represent the tracks while they are highlighted
Hit GFX | The special effect that appears when the creature takes a hit. If you click it, it is removed from the hit GFX list (you can have multiple)
Hit splatter liquid | The liquid that appears when the creature is hit. This is probably the stuff that will splatter onto the ground.
Add hit GFX | You can add an additional hit GFX with this button. Not sure if they show up simultaniously in-game or if they are shuffled.





#### Animator
Property | Description
------------ | -------------
Animation controller | This ties in with what you selected at 'Bone type'. An animation controller animates the bones. The sprites will be projected on top of the bones. Make sure that the animation controller is the same as the 'Bone type'. 



#### Mutation
This section not only changes the appearance of the creature, but also the stats, although indirectly. You select 'mutations'. For a human, a 'mutation' might be a human arm, or a bionic arm. Each variant has it's own properties like health and appearence. Don't think you're mutating your creature with these mutations, your creature IS the mutations.

Property | Description
------------ | -------------
Select status | This only changes the preview image, nothing else
Add mutation | You can add mutations to your creature with these buttons. Some of these mutations not only change the properties, but also the appearance. Currently, you can't see the creature's properties directly. You need to look at the mutations you put on your creature and look at the stats there.
Mutation list | The mutations show up in this vertical list. You can click them to remove them.
Base body mutation | Here you will tell the game what your body is made of. You already defined your body structure in 'bone type', so you can only select the parts of that type here. These mutations are defined somewhere else in the JSON and have their own stats.
Set mutation group | You can select mutation groups for your creature here. On the left side are the mutations that will apply to your character. These groups probably contain multiple variants of the same mutation and the game selects one of them. So for example, human_mouth may contain multiple sprites for a human mouth.
Collider radius | This sets the radius for the collider. The collider is the blue circle on the preview. It tells the game where the creatrure will collide with other objects in-game.
Collider pos | This sets the position for the collider. Decreasing X moves the collider left. Increasing X will move the collider right. Decreasing Y moves the collider up. Increasing Y will move the collider down. The collider is the blue circle on the preview. It tells the game where the creatrure will collide with other objects in-game.
Shade height | Sets how high the shadow is projected under the creature
Shade size | Sets how big the shadow is below the creature



#### Item table
This determines what you can loot from your creature, although you can select only item groups, not items. You can select item groups from the list on the right. Once you click a group, it moves to the left. Use the 'filter word' to filter the list on the right. Your creature will now carry items from that group. Look at the item group section for more about item groups.


#### Base stat
Property | Description
------------ | -------------
Default race value | This is probably the max/default health value. TODO figure out why you can add more then one. Does this have something to do with the character creation menu?
Race value | This is probably some additinal health value you can set and add a sub-race? it also notes that this can change, so it can probably increase or decrease based on certain effects. The default race value propbably can't change if only the sub race value can change.
Stamina spending while running (hour) | The amuont of stamina spent per hour while running
Sight range | How far you can see. Probably in number of tiles
Sight angle | How wide your field of view is, in degrees. Don't enter more then 360
Attack range | The unarmed melee attack range? TODO figure this out
Move speed | The speed at which you walk. Probably tiles per second
Moving type | Wether the creature can walk, run or both
Rotation speed | The speed at which you turn around. Is this degrees/second? TODO figure this out
Set stat | Enter a number per stat for this creature. Not sure how this is affected by mutations
Set skills | The default skill level for this creature.



## Mutation



#### General
Property | Description
------------ | -------------
Mutation Name | The name of the mutation
ID | Something to identify this mutation. Don't use spaces
Description | An optional description for this mutation. Not sure if it shows up in-game
Required race value | Probably the number of mutations of a certain race you need to have in order to gain this mutation? Like, you would get fur and claws befor you would get a snout and tail. You can add a list of required races and their values
Exclusive group | This probably enables you to make sure the mutation can only be gained if the creature gets a mutation from the selected group
Mutation priority | This probably has to do with rendering. TODO is a high priority needed to render on top? Or a low priority?
Rendering exclusive group | TODO: Figure this out



#### Mutation effect
Property | Description
------------ | -------------
Mod condition stat | Select a stat that the mutation will affect, like health or stamina
Max | The amount of max health is added to the creature that gets this mutation. TODO can this value be negative?
Delta per hour (120 per day) | TODO: Figure this out
Effect type | Allows you to select an effect that this mutation has your creature. It may be an effect on a stat, skill, moreale and more
Add new effect | Adds the effect you selected at 'effect type'. You can add multiple effects.



#### Disassembling data
This is probably used when you butcher a corpse. You need to set the disassemble (butcher) data for each mutation.

Property | Description
------------ | -------------
Disassemble type | Sets the type of disassembly can be performed on this mutation (probably the corpse of the creature that carries this mutation). Choose Batch, batch_individual or individual
Disassembling data  | Make a list of items that result from disassembling the creature that carries this mutation
Result item | Select the ID of the item that will be returned when the creature is butchered
Min/max | The minimum and maximum amount of the selected item that will be returned when buchering. The game will select a random amount between these values.
Add disassembled item | Adds a new item to the list for you to configure
Required skill level | Allows you to set a list of skills required to perform disassembly on this mutation
Required tool level | Allows you to set a list of required tool levels to butcher this mutation



#### Parent category
Property | Description
------------ | -------------
Category | I think you select the bone_type here but maybe there is a category that this mutation should belong to?
Body part | Select the body part that this mutation applies to. You can only select parts of the 'category' you selected above
Can wear | Wether or not you can put clothes on this body part after aquiring this mutation
Can wield | Wether or not you can wield weapons after this body part aquired this mutation
Can walk | Wether or not this mutation allows walking
Body type | TODO No idea what effect this has in-game



#### Base color preset ID
This has something to do with appearance TODO figure this out



#### Mutation Sprite
A sprite is not required for a mutation. What you will see with different creatures is that the body parts are defined as mutation without sprite, and the skin is defined as a mutation with many sprites making up the entire body. Not sure what the logic behind this is but it probably has to do something with animation.

Property | Description
------------ | -------------
Preview | The preview of all the sprites that you have applied to this mutation (if any).
Sprite/pivot toggle | Allows you to see/hide the sprites you have selected for this mutation (if any)
Female/male front/back | Allows you to switch between the female and male front/back view. You need to define sprites for each view if you plan to add any sprites at all
Add sprite | Adds a new sprite to the list at 'select sprite'
Remove sprite | Removes the selected sprite from the 'select sprite' list
Select sprite | Allows you to select the sprite you want to modify or delete
Previous/next | Cycle trough the list of sprites
Sprite selection | Allows you to select a sprite from the assets. If you have an external sprite somewhere on your harddrive, you need to add it to the assets first
Select layer | The layer on which the sprite will appear. This allows you to layer sprites on top of eachother so the arm behind the body actually appears behind the body
Sprite name | An arbitrary sprite name. You are not required to change this, it is merely for your own convenience
Priority | Probably has something to do with the situation where there are multple sprites on the same layer? Allows you to set what sprite gets priority
Synchronize color preset | TODO what relation does this has with 'Base color preset ID'? 
Position | The position of the selected sprite on the preview (and in-game). You should probably enable the pivot guides next to the preview to help position things.
Apply this setting to other stance | If you are working on the back view, this will probably copy the settings over to the front view and vica verse. 
Apply both side settings to other gender | If you are working on the male sprites, this will probably copy over the front and back sprites for this gender over to the female gender and vice verse.
