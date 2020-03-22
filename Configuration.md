This page details all of the config options in wizardry and how to use them. Most of the information on this page can be found in-game using the mod options menu, accessed either from the 'mod options' button in the pause menu or the 'mods' button in the main menu.

本页面将介绍 Wizadry 的所有配置选项与使用方法。本页面中的大部分内容都可以在游戏中的 mod options 菜单中找到，可以通过点击暂停菜单页面的 'mod options' 按钮或者主菜单的 'mods' 按钮进入。

Wizardry may be configured either by using the in-game mod options menu (recommended), or by editing the config file manually with a text editor before launching the game.

可以通过游戏中的 mod 菜单配置 Wizadry （推荐），或者在游戏启动之前编辑 config 文件中的文本进行配置。

## Jump to...
**等待其他页面翻译中。。。**

[[Worldgen|Configuration#worldgen]]  
[[Gameplay|Configuration#gameplay]]  
[[Commands|Configuration#commands]]  
[[Client Options|Configuration#client-options]]  
[[Resistances|Configuration#resistances]]  
[[Spells|Configuration#spells]]  

---
## Worldgen
## 世界生成设置
_Options which affect how wizardry's world generation features work._
_设定本模组的世界生成特征。_

#### Ore Dimensions
#### 水晶矿生成维度
Determines the dimensions in which [[crystal ore]] will generate. Must be a list of integer dimension IDs. The default value is `[0]`, which is just the overworld.

设定[[水晶矿石]] 的生成维度。维度 ID 必须为整数。默认值为 `[0]` ，指只在主世界生成。

#### Flower Dimensions
#### 水晶花生成维度
Determines the dimensions in which [[crystal flowers|Crystal-Flower]] will generate. Must be a list of integer dimension IDs. The default value is `[0]`, which is just the overworld.

设定[[crystal flowers|Crystal-Flower]]的生成维度。维度 ID 必须为整数。默认值为 `[0]` ，指只在主世界生成。

#### Tower Dimensions
#### 巫师塔生成维度
Determines the dimensions in which [[wizard towers|Wizard-Tower]] will generate. Must be a list of integer dimension IDs. The default value is `[0]`, which is just the overworld.

设定[[wizard towers|Wizard-Tower]]的生成维度。维度 ID 必须为整数。默认值为 `[0]` ，指只在主世界生成。

#### Tower Rarity
#### 巫师塔稀有程度
Determines the rarity with which wizard towers will generate. Must be an integer between 0 and 50, with higher numbers meaning towers are rarer. The default value is 8.

巫师塔的稀有度，代表每多少个区块内会生成一个巫师塔必须在 0 到 50 之间，数字越高生成概率就越少。默认值为 8 。

_N.B. Since structure generation is somewhat random, it is always possible for two or more wizard towers to generate near to each other._

_注：因为生成是随机的, 所以总是有可能会有两个或多个距离相近的巫师塔。_

#### Generate Loot
#### 生成战利品
Determines whether wizardry loot will be generated in vanilla loot chests. Disabling this will prevent wizardry's loot (as specified in the loot table chests/dungeon_additions.json) from being injected into vanilla loot tables.

是否在地牢箱子中生成战利品。禁用此选项将阻止 wizardry 的战利品（as specified in the loot table chests/dungeon_additions.json）添加到原版战利品表中。

_N.B. This does not affect wizardry's [[loot functions|Loot-Functions]]._.

_注：这不会影响 wizadry 的[[loot functions|Loot-Functions]]._

---
## Gameplay
## 游戏机制设定
_影响游戏机制的全局设定。_

#### Discovery Mode
#### 探索模式
Determines whether spells that a player has not yet cast will be unreadable until they are identified (either using a [[scroll of identification]] or by casting the spell). Setting this option to false effectively removes the spell discovery mechanic, though wizardry still keeps track of which spells each player has cast, so this option may be turned on and off at will without affecting existing saves. The default value is true.

当此设置为打开时，你还没施放的法术 (包括 [[scroll of identification]] 或者施放法术)不可读，直到施放后（基于这个世界）。在创造模式下无效。如果这被关闭，生存模式下将无法获得待鉴定卷轴。将此选项设置为 false 可以删除法术探索机制，即使玩家依旧可以留下法术施放记录，所以这个选项不会影响现有的法术。默认值为 true 。

#### Friendly Fire
#### 友军伤害
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
Determines whether a [[magic crystal]] is required in the crafting recipe for [[blank scrolls|Scrolls]]. This should be set to true if another mod adds a conflicting recipe. The default value is false.

#### Spell Book Drop Chance
Determines the chance out of 200 that mobs will drop spell books. Must be an integer between 0 and 200, with a value of 200 causing mobs to drop a spell book every time and a value of 0 causing spell book drops to be disabled entirely. The default value is 3.

_N.B. This does not apply to [[evil wizards|Evil Wizard]]._

#### Player Damage Scaling
Determines the global damage scaling factor applied to magic damage dealt by players. This includes indirect damage, e.g. from players' minions or constructs. Use this config option to alter the difficulty of the mod to your preference.

_N.B. Some spells such as [[arrow rain]] use vanilla entities and will not be affected by this option._

#### NPC Damage Scaling
Determines the global damage scaling factor applied to magic damage dealt by NPCs such as [[wizards]]. This includes indirect damage, e.g. from NPCs' minions or constructs. Use this config option to alter the difficulty of the mod to your preference.

_N.B. Some spells such as [[arrow rain]] use vanilla entities and will not be affected by this option._

#### Summoned Creature Targets Whitelist
Determines which mobs summoned creatures are specifically allowed to target, if this does not happen by default. Wizardry makes a best guess as to whether a mob is a suitable target for summoned creatures, but sometimes mobs from other mods work differently. Must be a list of entity IDs, with modid prefixes (for example, `wizardry:wizard`, `minecraft:shulker` or `twilightforest:skeleton_druid`). The default value is `[]` (an empty list).

#### Summoned Creature Targets Blacklist
Determines which mobs summoned creatures are not allowed to target, overriding the default and the whitelist. Wizardry makes a best guess as to whether a mob is a suitable target for summoned creatures, but sometimes it is undesirable for them to target certain mobs from other mods. Must be a list of entity IDs, with modid prefixes (for example, `wizardry:wizard`, `minecraft:shulker` or `twilightforest:skeleton_druid`). The default value is `[creeper]`.

#### Minion Revenge Targeting
Determines whether summoned creatures can revenge-target their summoner if their summoner attacks them. Set this to false if you want your minions to behave themselves at all times, or if you often find yourself accidentally hitting your minions with magic. The default value is true.

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
Determines the position of the spell HUD. Valid positions are 'Bottom left', 'Top left', 'Top right' and 'Bottom right' (without quotes). The default value is 'Top left'.

#### Show Summoned Creature Names
Determines whether summoned creatures show nameplates above their heads. If set to true, summoned creatures will show a nameplate with the name of the owner and the name of the creature, for example, 'Steve's Zombie'. The default value is true.

#### Enable Shift-Scrolling
Determines whether spells can be switched between by sneaking and scrolling with the mouse wheel. The default value is true.

_N.B. This does not affect the keybindings for spell switching; those can be disabled in the controls menu if desired by setting them to NONE._

---
## Resistances
_Options that affect how creatures interact with the different types of damage in wizardry._

---
## Spells
All of the [[spells|Spells]] in wizardry (and those in addons, if present) have their own config option allowing them to be enabled or disabled individually. If a spell is causing problems, creates an unintended exploit, or you just don't like it, then you can turn it off here!

_N.B. In order to preserve correct metadata values, the spell book and scroll (if it has one) will remain in-game and will be accessible in the creative menu. However, disabled spells may not be cast via any means, may not be bound to wands, will be excluded from any newly unlocked trades, and will not generate in chests or drop as loot. This ensures they are unobtainable in survival mode unless the spell book/scroll already exists in the world._
