| Runestone Pedestal | [[images/misc/runestone_pedestals.png]] |
|---|---|
| Craftable | Yes |
| Stackable | Yes, 64 |
| Creative Tab | Wizardry |
| Harvest Tool | Pickaxe, any* |
| Blast Resistance | 10 |
| Drops | Itself |
| Tile entity | Only when part of a shrine |
| Block ID | `ebwizardry:runestone_pedestal` |
| First appeared in | Wizardry 4.2 |

*_Runestone pedestals which are part of an unconquered shrine cannot be destroyed in survival mode

Runestone pedestals are blocks with similar properties to stone, which are available in 7 elemental varieties and have a glowing pattern on their side faces. They serve as decorative blocks and building materials, and hold the tile entity responsible for [[shrine]] mechanics.

## Obtaining
Runestone pedestals can be crafted from 5 stone and 4 magic crystals of the corresponding [[element]], or it can be collected from naturally-generated shrines once conquered. It is also available in the wizardry tab of the creative mode inventory and via the /give command.

[[images/recipes/runestone_pedestal.png]]  
_The crafting recipe for fire runestone pedestals - other elements require their respective elemental crystals_

## Appearance
Runestone pedestal blocks appear to be made of coloured stone with roughly chiselled edges. The four side faces have a T-shaped pattern, which glows in the dark - though the block itself does not emit any actual light. The colours of the stone and pattern reflect the runestone pedestal's element.

## Usage
Runestone pedestals have no uses in survival mode besides construction and decoration. However, using commands it is possible to place a runestone pedestal which will behave as if it were part of a naturally-generated shrine, allowing shrines to be built artificially.

## Technical
_For an explanation of shrine mechanics themselves, see [[Shrine#Mechanics]]_.

When generated as part of a shrine, a runestone pedestal has its `natural` property set to `true`. This makes it unbreakable in survival mode and gives it a tile entity, which controls the shrine's mechanics. When the shrine is conquered, the pedestal is immediately replaced with a `natural=false` variant, which is breakable and has no tile entity. Runestone placed using the item is always the `natural=false` variant. However, using the `/setblock` command, it is possible to place a pedestal with its `natural` property set to `true`, which will behave as if it was generated naturally.