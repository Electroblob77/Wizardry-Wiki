_Since: Wizardry 4.2_

Every [[spell|spells]] in wizardry has a JSON file specifying various properties of the spell. These files are located in `assets/ebwizardry/spells` in the mod jar, and are loaded on startup. Spells from other mods are located under `assets/[modid]/spells` in their respective mod jars.

The spell properties files can be viewed in the wizardry GitHub repository [here](https://github.com/Electroblob77/Wizardry/tree/1.12.2/src/main/resources/assets/ebwizardry/spells).

## Structure

Spell properties files all contain the following tags:

- **enabled**: A list of _contexts_ in which the spell is enabled. There are currently 9 contexts:
  - **book**: True to enable the [[spell book]] for this spell, false to disable it. If disabled, the spell book will be unobtainable (in survival) and will not bind to [[wands]].
  - **scroll**: True to enable the [[scroll|scrolls]] for this spell, false to disable it. If disabled, the scroll will be unobtainable (in survival) and will not work when right-clicked.
  - **wands**: True to allow wands to cast this spell, false to prevent it. If disabled, the spell will not bind to wands and wands it is already bound to will not be able to cast it.
  - **npcs**: True to allow NPCs to cast this spell, false to prevent it. If disabled, [[wizards|wizard]] and other spellcasting mobs/NPCs will not spawn with this spell equipped, and those that already have it will not be able to cast it. It will also be excluded from the [[wizard_spell loot function|Loot Functions#wizard_spell]], so evil wizards will not drop it.
  - **dispensers**: True to allow dispensers to cast this spell, false to prevent it. If disabled, the spell's scroll will drop out of the dispenser as an item rather than being consumed and casting the spell.
  - **commands**: True to allow this spell to be cast using commands, false to prevent it. If disabled, the `/cast` command will always fail for this spell.
  - **treasure**: True to include this spell in loot chests, false to exclude it. If disabled, the spell will be excluded from the [[random_spell loot function|Loot Functions#random_spell]] when used in chest loot tables.
  - **trades**: True to allow this spell to be sold by wizards, false to prevent it. If disabled, newly-spawned wizards will not offer the spell's book in any of their trades, and existing wizards will not offer it in newly unlocked trades.
  - **looting**: True to include this spell's book in rare mob drops, false to exclude it. If disabled, the spell will be excluded from the [[random_spell loot function|Loot Functions#random_spell]] when used in entity loot tables.
- **tier**: Determines the spell's [[tier|tiers]]. Valid tiers are `"novice"`, `"apprentice"`, `"advanced"` and `"master"`.
- **element**: Determines the spell's [[element|elements]]. Valid elements are `"magic"`, `"fire"`, `"ice"`, `"lightning"`, `"necromancy"`, `"earth"`, `"sorcery"` and `"healing"`.
- **type**: Determines the spell's [[type|spell types]]. Valid types are `"attack"`, `"defence"`, `"utility"`, `"minion"`, `"buff"`, `"construct"`, `"projectile"` and `"alteration"`.
- **cost**: Determines the mana cost of the spell.
- **chargeup**: Currently unused.
- **cooldown**: Determines the cooldown time of the spell, in ticks (20 ticks = 1 second).
- **base_properties**: A list of _spell-specific_ properties. Different spells will have different properties depending on what they do, and a few will have none at all. Property names are normally fairly self-explanatory.
  - **[property name]**: Determines the numeric value of a particular property.
  - ...

As an example, here is the spell properties file for [[magic missile]]:

```json
{
	"enabled": {
		"book": true,
		"scroll": true,
		"wands": true,
		"npcs": true,
		"dispensers": true,
		"commands": true,
		"treasure": true,
		"trades": true,
		"looting": true
	},
	"tier": "novice",
	"element": "magic",
	"type": "projectile",
	"cost": 5,
	"chargeup": 0,
	"cooldown": 5,
	"base_properties": {
		"damage": 3,
		"range": 18
	}
}
```

Here, the `"damage"` tag specifies the damage dealt when a magic missile hits a player or mob, and the `"range"` tag determines how far it will fly before vanishing.

> The spell-specific properties listed in a spell's JSON file are the only ones available for that spell. Removing any of them will crash the game with a `JSONSyntaxException`, and adding others will do nothing. For example, adding a `"blast_radius"` tag to a spell that doesn't already have it will not make it cause explosions, as this would have to be implemented in-code first.

## Modifying spell properties

_Since: Wizardry 4.2.4_

Spell properties files can be modified to tweak how spells behave - this can be useful for balancing modpacks, making minigames, or just adjusting the gameplay to your liking.

Spell properties are loaded from 3 locations, which can be thought of like 'layers', similar to the resource pack stacking system. In order of priority, these are:

1. `saves/[world save]/data/spells` - Contains world-specific spell properties, which override the other two locations. Within this folder, spells are organised into subfolders by mod id, so all the spells in the base mod will be in a folder `ebwizardry`. These files are loaded on world load, so in singleplayer or LAN they can be reloaded by quitting to the main menu and reopening the world.
2. `config/ebwizardry/spells` - Contains global custom spell properties, which override the built-in ones. Within this folder, spells are organised into subfolders by mod id, so all the spells in the base mod will be in a folder `ebwizardry`. These files are loaded on startup, so the game must be restarted for changes to take effect.
3. `mods/[wizardry/addon jar]/assets/[mod id]/spells` - Contains the built-in default spell properties. If you're developing an addon, this is where your spell properties files live. These files are loaded on startup, so the game must be restarted for changes to take effect.

By default, neither the world-specific (1) or config (2) spell JSON folders exist - they must be created manually. Custom spell properties files can then be put into the folder to modify them. These files must be complete as described above, or the game will crash with a `JSONSyntaxException` (it is not currently possible to specify only some of the properties and have the built-in properties file determine the rest). The default spell properties files can be extracted from the wizardry or addon jar, or you can view and download the ones from the base mod [here](https://github.com/Electroblob77/Wizardry/tree/1.12.2/src/main/resources/assets/ebwizardry/spells).