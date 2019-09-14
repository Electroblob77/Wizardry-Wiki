_This page is about the status effect. For the spell, see [[Containment]]._

| Containment | ![](https://github.com/Electroblob77/Wizardry/blob/1.12.2/src/main/resources/assets/ebwizardry/textures/gui/potion_icon_containment.png) |
| --- | --- |
| Particles | Light blue-grey |
| Effect type | Negative |
| Max. natural level | Containment IV |
| Potion ID | `ebwizardry:containment` |
| First appeared in | Wizardry 4.2 |

## Description
Containment is a negative potion effect which traps players and mobs within a cube-shaped zone. A player or mob under the containment effect will be prevented from leaving this zone through any means, whether by walking, flying, teleporting or otherwise. Players will also see an animated magical barrier when close to the edges of the containment field.

The higher the level of containment, the smaller the containment field, with the distance from the centre determined using the formula `15 - 4 x level` (where containment I is level 0). The following table details the exact size of the containment field at each level of effect:

| Effect level | Containment field width |
| --- | --- |
| Containment I | 30 |
| Containment II | 22 |
| Containment III | 14 |
| Containment IV | 6 |

## Sources
All players, [[wizards|Wizard]] and [[evil wizards|Evil-Wizard]] within 15 blocks of an activated [[shrine]] will receive containment I every second, with a duration of 10 seconds. This effectively makes the effect permanent until the shrine is conquered or the pedestal destroyed (in creative). In addition, the containment spell inflicts containment III on its target for 20 seconds without modifiers. The effect may also be obtained via commands.

## Trivia
- The containment field is always centred on the position of the host when it first received the effect.
- Levels higher than containment IV (obtainable only using commands) cause the containment field to turn inside-out, resulting in the host being pushed rapidly back and forth.