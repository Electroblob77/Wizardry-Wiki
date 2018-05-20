| Fear | [[images/icons/fear.png]] |
| --- | --- |
| Particles | Red |
| Effect type | Negative |
| Max. natural level | Fear I |
| Potion ID | `ebwizardry:fear` |
| First appeared in | Wizardry 1.1 |

## Description
Fear is a negative status effect that causes mobs to run away from a particular creature. Creatures under the effects of fear I will try to stay at least 16 blocks away from the creature that inflicted it upon them. This creature is stored by its UUID in the mob's NBT data (under the "fearedEntity" tag).

## Sources
The intimidate spell inflicts fear I on nearby entities for 30 seconds without modifiers. The only other source of the effect is via commands.

## Trivia
- The amplifier has no effect for fear, much like blindness or nausea in vanilla _Minecraft_.
- Fear has no effect on players.
- Since the feared creature is stored in NBT, simply giving a mob the fear status effect will have no effect unless its NBT contains the correct tag.