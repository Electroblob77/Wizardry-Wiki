This page explains how to add custom entities to your spells (or elsewhere) using wizardry's built-in classes.

> Note that you don't have to use wizardry's built-in classes, but if you do, they will take care of a lot of the inner workings for you, like syncing and saving variables, keeping track of entities' casters, display stuff and so on. It will also make it easier for you if an update to wizardry changes anything (which is pretty likely).

## Custom projectiles
Wizardry has two classes used for custom projectiles: `EntityMagicProjectile` and `EntityMagicArrow`, both of which can be found in the package `electroblob.wizardry.entity.projectile`. The key difference between these two classes is that `EntityMagicArrow` rotates to face in the direction of travel as it flies (like an arrow), whereas `EntityMagicProjectile` doesn't (like a snowball). Other than that, the two classes are fairly similar.

## Custom summoned creatures (minions)
The relevant classes for summoned creatures can be found in the package `electroblob.wizardry.entity.living`. Wizardry's summoned creatures can be split into two categories:
- Creatures that exist in vanilla Minecraft, such as skeletons and blazes. The classes for these entities extend their vanilla counterparts and implement the interface `ISummonedCreature`. Creatures that exist in other mods also fit into this category.
- Creatures that don't exist in vanilla Minecraft, like ice wraiths and storm elementals. The classes for these entities extend `EntitySummonedCreature`, which implements `ISummonedCreature` itself, so you don't have to.

## Custom constructs

## Custom spell casters
You can even add your own spell casting entities!