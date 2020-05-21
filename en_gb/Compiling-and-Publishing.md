This page explains how to compile and publish a spell pack or other addon mod.

## Prerequisites
- A spell pack or addon mod ready to compile.
- Knowledge of how to compile a mod using gradle.
- A `build.gradle` file.

## Compiling a spell pack

You can compile your spell pack in the same way as any other mod, by running `gradlew.bat build` in the command window. If you put the deobfuscated jar in the `libs` folder, this should all work just fine. However, if not, the build will fail with compile errors. To fix this, add the following lines to your `build.gradle` file:
```
dependencies {
	compile files (
		"[filepath]"
	)
}
```
where `[filepath]` is the file path of the _deobfuscated_ version of Wizardry, relative to your project folder.

You can test out your compiled spell pack by dropping it into a Forge installation the same way you would install any other mod. Be sure to have wizardry installed as well!

## Publishing a spell pack

So, you've made a spell pack, and now you want to release it for the community to enjoy. Hooray!

I do not place any restrictions on how or where you distribute your addon mod, provided that you **credit me**, Electroblob, as the author of _Electroblob's Wizardry_, and **give a link** to the original mod (i.e. the curseforge page, this repository, or the Minecraft Forum thread). After all, nobody can play your addon without downloading wizardry as well!

I also kindly ask that you don't put your addon behind AdFly or other URL shorteners, because they're a pain and I don't want wizardry's players to have to go through that. I'd recommend using CurseForge to distribute your addon mod, because it allows you to specify that it's an addon to Wizardry, and they have an awesome rewards program to repay you for your hard work!

I also ask that you notify me if you release an addon mod, either on [Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) or the [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod). It's not required, but if you do I will add a link to your addon in Wizardry's description!

There's also a **#spell-packs** channel on the wizardry Discord server where you can come and tell people all about your spell pack, so be sure to check that out!