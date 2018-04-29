_Since: Wizardry 1.1_

Wizardry has four inbuilt commands: /cast, /discoverspell, /ally and /allies. This page explains what they do and how to use them.

_Note that angle brackets <> denote required arguments, whereas square brackets [] denote optional arguments. All commands support tab-completion where applicable. Spell names used in commands are unlocalised, meaning they are in English, all in lowercase and spell names with more than one word have underscores _ between words._

## /cast

**Syntax: /cast <spell> [player] [damage multiplier] [range multiplier] [duration multiplier] [blast multiplier]**

Casts the specified spell. If a player is specified, casts the spell as if it were being cast by that player, otherwise casts the spell as the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names. If the spell is a continuous spell (i.e. one where the use item button must be held when casting with a wand), the spell will continue to be cast until the command is repeated (though the optional arguments need not be specified again).

Numerical multipliers (with 1 being default) can also be specified for the spell, and can be decimals like 1.4. By default, these can be anywhere between 0 and 20 inclusive, though the upper limit can be changed via the config. If the first argument after the spell is not a currently logged in player, it is treated as a number, so for example, the command /cast magic_missile 1.5 is valid, despite no player being specified. Be aware that excessive multipliers (especially blast) can cause considerable lag if used with certain spells.

Requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN).

## /discoverspell

**Syntax: /discoverspell <spell> [player]**

Adds the specified spell to the given player's discovered spells, or removes it if they have already discovered it. If no player is specified, defaults to the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names. Type 'all' (without quotes) in place of a spell name to discover all spells, or 'clear' to remove all discovered spells.

Requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN).

## /ally

**Syntax: /ally <player> [player]**

Adds the first player to the second player's list of allies, or removes them if they are already an ally (see Ally Designation System for details on allies). If the second player is unspecified, it defaults to the player who typed the command. If this command is executed by a command block, _both_ player arguments are required and accept @p, @a, etc. as well as specific player names.

All players can use this command on themselves, but changing another player's allies requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN).

## /allies

**Syntax: /allies [player]**

Displays a list of the given player's allies, including those not currently logged in (see Ally Designation System for details on allies). If the player is unspecified, it defaults to the player who typed the command. If this command is executed by a command block, the player argument is _required_ and accepts @p, @a, etc. as well as specific player names.

All players can use this command on themselves, but viewing another player's allies requires operator permissions (multiplayer) or cheats enabled (singleplayer/LAN).