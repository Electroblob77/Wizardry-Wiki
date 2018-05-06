This page details all of the config options in wizardry and how to use them. Most of the information on this page can be found in-game using the mod options menu, accessed either from the 'mod options' button in the pause menu or the 'mods' button in the main menu.

Wizardry may be configured either by using the in-game mod options menu (recommended), or by editing the config file manually with a text editor before launching the game.

---
## Worldgen
_Options which affect how wizardry's world generation features work._

#### Ore Dimensions

#### Flower Dimensions

#### Tower Dimensions

#### Tower Rarity
Determines the rarity with which [[wizard towers|Wizard-Tower]] will generate. Must be an integer between 0 and 50, with higher numbers meaning towers are rarer. The default value is 8.

_N.B. Since structure generation is somewhat random, it is always possible for two or more wizard towers to generate near to each other_

#### Generate Loot
Determines whether wizardry loot will be generated in vanilla loot chests. Disabling this will prevent wizardry's loot (as specified in the loot table chests/dungeon_additions.json) from being injected into vanilla loot tables.

_N.B. This does not affect wizardry's [[loot functions|Loot-Functions]]._

---
## Gameplay
_Options which affect wizardry's general gameplay._

#### Discovery Mode

#### Friendly Fire

#### Telekinetic Disarmament

#### Teleport Through Unbreakable Blocks

#### Firebomb is Craftable

#### Poison Bomb is Craftable

#### Smoke Bomb is Craftable

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