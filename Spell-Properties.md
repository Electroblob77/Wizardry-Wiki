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

## Modifying spell properties

Spell properties files can be modified to tweak how spells behave - this can be useful for balancing modpacks, making minigames, or just adjusting the gameplay to your liking.

For now, the only way to do this is to modify the mod jar directly. To do this, use an archive program such as 7zip to extract the JSON files for the spells you want to edit from the mod jar (or alternatively rename the mod jar to a `.zip` and unzip using your file explorer). The JSON files can then be modified to change various properties of the spell. When you're done editing, overwrite the original files in the mod jar (or zip the mod jar again and rename to a `.jar`) and run _Minecraft_, and you should see the altered properties in-game!

> In future, you'll be able to edit these files without modifying the mod jar.