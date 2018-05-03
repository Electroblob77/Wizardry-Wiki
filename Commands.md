_Since: Wizardry 1.1_

Wizardry has four inbuilt commands: /cast, /discoverspell, /ally and /allies. This page explains what they do and how to use them.

> Note that angle brackets <> denote required arguments, whereas square brackets [] denote optional arguments. All commands support tab-completion where applicable. Spell names used in commands are unlocalised, meaning they are in English, all in lowercase and spell names with more than one word have underscores _ between words.

## /cast

**Syntax: /cast \<spell\> [player] [modifiers]**

Casts the specified spell. If a player is specified, casts the spell as if it were being cast by that player, otherwise casts the spell as the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names. If the spell is a continuous spell (i.e. one where the use item button must be held when casting with a wand), the spell will continue to be cast until the command is repeated (though the optional arguments need not be specified again).

Spell modifiers can also be specified for the spell using NBT format, for example `{damage:1.5, range:2}`. Valid modifiers are `damage`, `range`, `duration` and `blast`, though add-on mods may add their own. Modifiers can have decimal values like 1.4, or 0.58932. By default, these can be anywhere between 0 and 20 inclusive, though the upper limit can be changed via the config. NBT spell modifiers may be specified without needing to specify a player, so for example, the command /cast magic_missile {damage:1.5} will work, despite no player being specified. Be aware that excessive multipliers (especially blast) can cause considerable lag if used with certain spells.

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