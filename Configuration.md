This page details all of the config options in wizardry and how to use them. Most of the information on this page can be found in-game using the mod options menu, accessed either from the 'mod options' button in the pause menu or the 'mods' button in the main menu.

Wizardry may be configured either by using the in-game mod options menu (recommended), or by editing the config file manually with a text editor before launching the game.

## Jump to...
[[Worldgen|Configuration#Worldgen]]  
[[Gameplay|Configuration#Gameplay]]  
[[Commands|Configuration#Commands]]  
[[Client Options|Configuration#Client-Options]]  
[[Resistances|Configuration#Resistances]]  
[[Spells|Configuration#Spells]]  

---
## Worldgen
_Options which affect how wizardry's world generation features work._

#### Ore Dimensions
Determines the dimensions in which [[crystal ore]] will generate. Must be a list of integer dimension IDs. The default value is [0], which is just the overworld.

#### Flower Dimensions
Determines the dimensions in which [[crystal flowers|Crystal-Flower]] will generate. Must be a list of integer dimension IDs. The default value is [0], which is just the overworld.

#### Tower Dimensions
Determines the dimensions in which [[wizard towers|Wizard-Tower]] will generate. Must be a list of integer dimension IDs. The default value is [0], which is just the overworld.

#### Tower Rarity
Determines the rarity with which wizard towers will generate. Must be an integer between 0 and 50, with higher numbers meaning towers are rarer. The default value is 8.

_N.B. Since structure generation is somewhat random, it is always possible for two or more wizard towers to generate near to each other._

#### Generate Loot
Determines whether wizardry loot will be generated in vanilla loot chests. Disabling this will prevent wizardry's loot (as specified in the loot table chests/dungeon_additions.json) from being injected into vanilla loot tables.

_N.B. This does not affect wizardry's [[loot functions|Loot-Functions]]._

---
## Gameplay
_Options which affect wizardry's general gameplay._

#### Discovery Mode
Determines whether spells that a player has not yet cast will be unreadable until they are identified (either using a [[scroll of identification]] or by casting the spell). Setting this option to false effectively removes the spell discovery mechanic, though wizardry still keeps track of which spells each player has cast, so this option may be turned on and off at will without affecting existing saves. The default value is true.

#### Friendly Fire
Determines whether spells cast by a player can damage or otherwise negatively affect that player's allies. If set to false, a player's allies will be completely immune to all magic damage from them, both direct ([[ignite]], [[wither]], etc.) and indirect (summoned creatures, traps, [[chain lightning]], etc.) - this is in addition to the normal effects of designating a player as an ally. See [[Ally Designation System]] for more details on allies. The default value is true.

#### Telekinetic Disarmament
Determines whether players can use [[telekinesis]] to disarm other players. It is recommended that this is set to false on non-whitelisted servers to prevent players from stealing each other's items. The default value is true.

#### Teleport Through Unbreakable Blocks
Determines whether players can teleport through unbreakable blocks (e.g. bedrock, barrier blocks) using the [[phase step]] spell. This is set to false by default so that the phase step spell cannot be used to teleport into the void, cheat in mazes, and such like.

#### Firebomb is Craftable
Determines whether [[firebombs|Firebomb-(Item)]] have a [[crafting recipe|Crafting-Recipes]]. The default value is true.

#### Poison Bomb is Craftable
Determines whether [[poison bombs|Poison-Bomb-(Item)]] have a crafting recipe. The default value is true.

#### Smoke Bomb is Craftable
Determines whether [[smoke bombs|Smoke-Bomb-(Item)]] have a crafting recipe. The default value is true.

#### Use Alternate Scroll Recipe

#### Spell Book Drop Chance

#### Player Damage Scaling

#### NPC Damage Scaling

#### Summoned Creature Targets Whitelist

#### Summoned Creature Targets Blacklist

#### Minion Revenge Targeting
Determines whether summoned creatures can revenge-target their summoner if their summoner attacks them. The default value is true.

---
## Commands
_Options which affect how wizardry's [[commands|Commands]] work._

#### Cast Command Multiplier Limit

#### /cast Command Name

#### /discoverspell Command Name

#### /ally Command Name

#### /allies Command Name

---
## Client Options
_Options that are specific to each player; these have no effect in the config file on a server._

#### Spell HUD Position
Specifies the position of the spell HUD. Valid positions are 'Bottom left', 'Top left', 'Top right' and 'Bottom right' (without quotes).

#### Show Summoned Creature Names

#### Enable Shift-Scrolling

---
## Resistances
_Options that affect how creatures interact with the different types of damage in wizardry._

---
## Spells
All of the [[spells|Spells]] in wizardry (and those in addons, if present) have their own config option allowing them to be enabled or disabled individually. If a spell is causing problems, creates an unintended exploit, or you just don't like it, then you can turn it off here!

_N.B. In order to preserve correct metadata values, the spell book and scroll (if it has one) will remain in-game and will be accessible in the creative menu. However, disabled spells may not be cast via any means, may not be bound to wands, will be excluded from any newly unlocked trades, and will not generate in chests or drop as loot. This ensures they are unobtainable in survival mode unless the spell book/scroll already exists in the world._