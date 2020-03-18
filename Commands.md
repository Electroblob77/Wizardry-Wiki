_Since: Wizardry 1.1_  
_适用版本：巫术学1.1以上_  

Wizardry has four inbuilt commands: /cast, /discoverspell, /ally and /allies. This page explains what they do and how to use them.  
巫术学有四个内置的命令：/cast,/discoverspell,/ally 和/allies。这个页面将会告诉你它们各自的作用和使用方法。  

> Note that angle brackets <> denote required arguments, whereas square brackets [] denote optional arguments. All commands support tab-completion where applicable. Spell names used in commands are unlocalised, meaning they are in English, all in lowercase and spell names with more than one word have underscores _ between words.  
> 请注意：尖括号（<>）说明这是必要的参数，而方括号（[]）说明这是可选的参数。所有的命令都支持Tab补全。在命令中，法术的名称没有被本地化，所以说它们都是英文的，并且全部都是小写字母，如果法术的名称不止有一个单词，那么在单词之间会用下划线(\_)隔开。  


## /cast  

**Syntax: /cast \<spell\> [player] [duration] [modifiers]**  
**语法：/cast \<法术名称\>[玩家][持续时间][附加参数]**  

_or_ **/cast \<spell\> \<x\> \<y\> \<z\> \<direction\> [duration] [modifiers]**  
_或者_ **/cast \<法术名称\> \<x\> \<y\> \<z\> \<方向\>[持续时间][附加参数]**  

Casts the specified spell. If a player is specified, casts the spell as if it were being cast by that player. If a position and direction is specified, casts the spell as if it were being fired from a dispenser at that position, facing that direction. If neither is specified, casts the spell as the player who typed the command.  
发动某一种法术。如果一位玩家已经被指定，系统将认为这个法术由这位玩家发动。如果指定了位置和方向，则认为这个法术由

If this command is executed by a command block, the player or location argument is _required_ and accepts @p, @a, etc. as well as specific player names. The duration argument is only parsed if the spell is a continuous spell (i.e. one where the use item button must be held when casting with a wand), in which case it is required.

Spell modifiers can also be specified for the spell using NBT format, for example `{damage:1.5, range:2}`. Valid modifiers are `damage`, `range`, `duration` and `blast`, though add-on mods may add their own. Modifiers can have decimal values like 1.4, or 0.58932. By default, these can be anywhere between 0 and 20 inclusive, though the upper limit can be changed via the config. NBT spell modifiers may be specified without needing to specify a player, so for example, the command /cast magic_missile {damage:1.5} will work, despite no player being specified. Be aware that excessive modifiers (especially blast) can cause considerable lag if used with certain spells.

_Requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN)._

## /discoverspell

**Syntax: /discoverspell \<spell\> [player]**

Adds the specified spell to the given player's discovered spells, or removes it if they have already discovered it. If no player is specified, defaults to the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names. Type 'all' (without quotes) in place of a spell name to discover all spells, or 'clear' to remove all discovered spells.

_Requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN)._

## /ally

**Syntax: /ally \<player\> [player]**

Adds the first player to the second player's list of allies, or removes them if they are already an ally (see [[Ally Designation System|Ally-Designation-System]] for details on allies). If the second player is unspecified, it defaults to the player who typed the command. If this command is executed by a command block, _both_ player arguments are required and accept @p, @a, etc. as well as specific player names.

_All players can use this command on themselves, but changing another player's allies requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN)._

## /allies

**Syntax: /allies [player]**

Displays a list of the given player's allies, including those not currently logged in (see [[Ally Designation System|Ally-Designation-System]] for details on allies). If the player is unspecified, it defaults to the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names.

_All players can use this command on themselves, but viewing another player's allies requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN)._
