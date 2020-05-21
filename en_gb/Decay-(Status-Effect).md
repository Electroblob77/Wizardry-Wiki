_This page is about the status effect. For the spell, see [[Decay]]._

| Decay | ![](https://github.com/Electroblob77/Wizardry/blob/1.12.2/src/main/resources/assets/ebwizardry/textures/gui/potion_icon_decay.png) |
| --- | --- |
| Particles | Dark purple |
| Effect type | Negative |
| Max. natural level | Decay I |
| Potion ID | `ebwizardry:decay` |
| First appeared in | Wizardry 1.0 |

## Description
Decay is a negative status effect which has several dangerous effects. Players or mobs under the effects of decay will take ongoing damage (similar to the wither effect), have reduced movement speed, and place patches of decay wherever they walk. Decay I reduces movement speed by 20%, and each subsequent level (though not naturally occurring) will reduce movement speed by a further 20%.

## Sources
Any creature which steps on a patch of decay will be inflicted with the decay status effect for 20 seconds. The only other source of the effect is via commands. Decay patches themselves are placed by the decay spell and by other creatures with the decay effect.

## Trivia
- To avoid an infinite loop of self-infection, creatures are not inflicted with the decay effect when stepping on patches of decay they spread themselves.
- Amplifiers higher than decay I can only be obtained using commands, and only change the amount of slowness applied; the damage rate remains the same.