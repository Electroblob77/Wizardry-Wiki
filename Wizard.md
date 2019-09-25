_Not to be confused with [[evil wizards|Evil-Wizard]]._

| Wizard | [[images/icons/wizard.png]] |
|--------|-------|
| Health | 30 ([[images/icons/heart.png]] x 15)|
| Attack Damage | Varies |
| Size | Height 1.95, Width 0.6 |
| Spawns | Only in wizard towers |
| Drops | None |
| Experience | None |
| Entity ID | `ebwizardry:wizard` |
| First appeared in | Wizardry 1.0 |

Wizards are friendly NPCs who can cast spells. They can be found only in [[wizard towers|Wizard-Tower]], which generate naturally throughout the world. Wizards are an important part of wizardry's gameplay due to their trading mechanic, which is a reliable way to obtain [[spell books|Spell-Book]] and other magical items.

![](https://media.forgecdn.net/attachments/202/398/2017-01-16_20.png)
_An ice mage chilling in his tower_

## Spawning
Wizards naturally spawn only in wizard towers, which generate throughout the overworld (or whichever dimensions are specified in the config - see [[Configuration|Configuration]] for details). They can also be spawned using a wizard spawn egg, available in the creative mode inventory, or using the /summon command.

## Attributes and Equipment
Wizards have a 50% chance to spawn as specialists in one of the seven [[elements|Elements]] (about a 7% chance for each element), and a 50% chance of having no element. Wizards with an element wear the corresponding elemental armour and carry an elemental wand of that element, whereas wizards without an element wear regular wizard armour and carry a non-elemental wand. A wizard's element affects the types of spells they cast and the trades they offer, though it does not currently give a potency bonus to their attacks. Wizards with an element also have special names such as 'Pyromancer' and 'Earth Mage'.

Wizards spawn with a random tier of wand, but it is always powerful enough for the spells they cast. All wizards spawn with [[magic missile|Magic-Missile]] and three other spells chosen at random, with a high weighting on their element if they have one. In addition, all wizards know [[heal|Heal]] and use it independently from the rest of their spells, except healers, who know [[greater heal|Greater-Heal]] instead. They never drop their equipment, regardless of looting enchantments. Wizards also spawn with one of six randomly chosen skins, which have different hair and eye colours.

## Behaviour
Wizards are normally friendly towards players and passive animals, but are hostile towards mobs and will attack them on sight using magic. Wizards will show interest in nearby players and watch them when they are within a certain range. Right-clicking on a wizard will display a trade GUI, similar to that of NPC villagers, allowing the player to trade with the wizard - see [[Trading|Wizard#trading]] for more details.

If a player angers a wizard, either by hurting them or by breaking a block in their tower, the wizard will become hostile towards that player and start attacking them. This behaviour is similar to that of zombie pigmen, and like zombie pigmen, nearby wizards will also become hostile towards the player in question. If any of the wizards succeeds in killing the player, the wizards will no longer be hostile towards that player. Wizards will not trade with a player that has angered them. However, if a hostile mob attacks the wizard while the wizard is angry at a player, the wizard will stop attacking the player and attack the mob instead.

When in combat, wizards will select different spells at random to use against their opponent, incurring that spell's cooldown each time. These are usually attack spells, but can also be defensive or utility spells such as blink or forcefield. When on less than full health, wizards will heal themselves periodically. When severely injured, they will heal themselves more often.

## Trading
Wizards start out with four trades: three randomly chosen trades, and one trade which allows any spell book to be traded for 5 magic crystals (all wizards have this trade). Each time a player trades with a wizard, there is an 80% chance for the wizard to unlock a new trade, signified by them emitting pink potion particles for a few seconds. A maximum of 8 additional trades can be unlocked. The more trades a wizard has, the greater the chance that new trades will sell more valuable items, such as higher-tier spells and wands. For the statistically inclined, the exact chances are listed in the following table:

| Trades completed   | Basic | Apprentice | Advanced | Master |
|--------------------|-------|------------|----------|--------|
| 0 (starting trades)| 50%   | 25%        | 18%      | 8%     |
| 1                  | 46%   | 25%        | 20%      | 9%     |
| 2                  | 42%   | 24%        | 22%      | 12%    |
| 3                  | 38%   | 24%        | 24%      | 14%    |
| 4                  | 34%   | 22%        | 26%      | 17%    |
| 5                  | 30%   | 21%        | 28%      | 21%    |
| 6                  | 26%   | 19%        | 30%      | 24%    |
| 7                  | 22%   | 17%        | 32%      | 28%    |
| 8                  | 18%   | 15%        | 34%      | 33%    |

_Chance for each tier of item when unlocking a new trade. Number of trades completed excludes the initial four trades. Wizard armour items are treated as apprentice tier, and wand upgrades are treated as advanced tier._

When generating a trade for a wand, spell book or wizard armour, there is an 80% chance that its element will match that of the wizard, unless the wizard has no element.

## Trivia
- Wizards currently use the same sounds as NPC villagers
- Not all spells can be cast by wizards; see [[Spells|Spells]] for more information
- Zombies (and their variants) will seek out and attack wizards the same way as they do for NPC villagers, making them the only mob that actively attacks wizards without being provoked
- Wizards will fight each other if they accidentally hurt one another; combined with the zombie pigmen-style group mechanics this makes for some interesting fights between two groups of wizards
- Right-clicking a wizard with a spell book in creative mode will randomly change one of the wizard's spells for that spell - this was a debug feature, but it's fun to play around with so it was left in