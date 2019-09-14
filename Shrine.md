| Shrine | ![](https://github.com/Electroblob77/Wizardry/blob/1.12.2/src/main/resources/assets/ebwizardry/textures/integration/antiqueatlas/shrine.png) |
| --- | --- |
| Spawns | Overworld surface |
| Contains | 1 Runestone pedestal, 1 Chest |
| Spawned mobs | 3 Evil wizards |
| First appeared in | Wizardry 4.2 |

Shrines are structures which generate at the surface throughout the overworld, or whichever dimensions are specified by the [[shrine dimensions config option|Configuration#shrine-dimensions]]. Shrines consist of a ring of [[runestone]] pillars of varying heights, surrounding a central [[runestone pedestal]]. An arcane-locked chest containing valuable magical loot sits on top of the pedestal.

[[images/screenshots/shrine.png]]
_An earth shrine in an extreme hills biome_

## Generation
Shrines generate on the surface of the overworld, or whichever dimensions are specified in the config. Their default spawn frequency makes them quite rare, considerably rarer than [[wizard towers|Wizard-Tower]], though this can be changed in the config. Shrines generate in all biomes. With the exception of the pedestal and chest, shrines are built exclusively of [[runestone]]. There are eight different shrine layouts, each with a different arrangement of pillars - however, the central pedestal with loot chest is always the same.

Each shrine is aligned to one of the seven arcane [[elements]], which can easily be seen from the colour of the runestone from which it is built. This element also determines the element of the wizards that are spawned. Shrines cannot be aligned to the magic 'element'.

The loot chest found in a shrine is guaranteed to always contain one [[artefact|artefacts]], with higher-tier artefacts being rarer. Artefacts are found nowhere else. Alongside this, the chest can contain a variety of magical items, including magic crystals and elemental crystals, spell books and scrolls, and wand and armour upgrades, as well as other loot such as books, paper and emeralds.

## Mechanics
When initially generated, shrines are unactivated, and the chest in the centre is arcane-locked with no owner, preventing it from being opened or destroyed in survival mode. The shrine is activated when a player moves within 5 blocks of the central pedestal (which roughly corresponds to within the ring of pillars), signified by a sound and red particle effect. This immediately causes 3 [[evil wizards|Evil-Wizard]] to spawn which match the shrine's element, and a [[containment|Containment (Status Effect)]] effect to be applied to all players, wizards and evil wizards within 15 blocks of the central pedestal. This effect is refreshed every second as long as the shrine is active, much like that from a beacon, preventing the player and the spawned wizards from escaping.

Once a shrine is active, it may only be deactivated by killing all three evil wizards that were spawned. Upon doing so, a second sound and particle effect signify that the shrine has been conquered, and the arcane lock on the chest is removed, allowing the player to access the loot inside. Once conquered, the containment effect no longer refreshes, and will wear off after 10 seconds, allowing any players inside to escape.

In creative mode, the shrine can also be deactivated by breaking the central runestone pedestal block. This block is unbreakable in survival.

## Trivia
- When fast worldgen is enabled, shrines can sometimes generate in lakes, resulting in them being partially or even fully submerged.