> These tutorials are for wizardry 4.2.x. For older 1.12 versions (and 1.10/1.11), [check the page history](https://github.com/Electroblob77/Wizardry/wiki/Developing-Addons/_history). For 1.7.10 versions of wizardry, see the [legacy spell packs tutorial](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/pages/making-spell-packs).

These pages explain how to program addon mods for _Electroblob's Wizardry_, particularly **spell packs**. This page covers setting up your workspace ready to work with wizardry's code. See the links to other pages for how to add spells and other content.

## Pages in this category

[[Adding Spells]]  
[[Adding Wand Upgrades]]  
[[Adding Entities]]  
[[Miscellaneous Features]]  
[[Compiling and Publishing]]

---
# Getting Started

## Prerequisites

- A reasonable knowledge of the basics of modding with _Minecraft Forge_: an understanding of simple Java, how to make blocks, items and such like, and familiarity with the registry and event handling systems. That said, I have made every effort to explain things as clearly as I can along the way.
- A modding environment set up. I used eclipse for several years and recently switched to IntelliJ IDEA, but you can use any IDE - I won't be referring to anything specific to either of those IDEs. Make sure you have the correct version of Minecraft Forge for the version of wizardry you intend to use. Usually this will be the latest version of Forge for the version of Minecraft you are using.
- A mod set up ready to add spells to (main mod class and proxies, plus a lang file).

## Setting up your workspace

First you'll need to download the version of wizardry you wish to make a spell pack for, which can be found on curseforge ([here's the full list of downloads](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/files)). Make sure you get the right **mod** version as well as the right Minecraft version. I recommend using the latest version of wizardry for the Minecraft version you want, as it will have the most API features and make your life easier.

> Minor updates to wizardry shouldn't break the API, meaning that an addon written for 4.1.0 will work with 4.1.1, 4.1.2, etc. but not 4.2.x. However, the reverse is not necessarily true: if you use a new feature that was added in a minor patch, your addon won't work in older versions.

Next, make a folder called `libs` inside your project folder (the one with build.gradle in) and put the wizardry jar in there. Now if you launch Minecraft in your development environment, wizardry should be fully working in-game.

However, if you look inside the wizardry jar and open up any of the classes you'll notice they're completely unreadable. To get a readable version, you'll need to attach the source code. The source code for all versions can be downloaded as a `.zip` from GitHub as follows:

1. Go to the [releases page](https://github.com/Electroblob77/Wizardry/releases) for wizardry's GitHub repository (you can also access this from the main page by clicking releases in the menu bar just above the file tree)
2. Find the release you're developing for in the list
3. Click the little `.zip` icon below the release version number to download a zip file of the entire repository at that release

Once you've downloaded the source code, rename the file extension from `.zip` to `.jar` and move the file somewhere sensible (don't put it in `libs` or Forge will think you have duplicate mods). Now use your IDE to attach the source jar to the compiled jar - again, if you don't know how, you'll need to look up how to do this for the IDE you're using.

> If (unlike me) you know what you're doing with Gradle and Maven, you can use the CurseForge Maven as an alternative to storing wizardry jars locally. See the [curse knowledge base](https://authors.curseforge.com/knowledge-base/projects/529-api) for more details.

## Specifying wizardry as a dependency

Next you'll need to specify Wizardry as a dependency for your mod, which is done in your `@Mod` annotation using the following syntax:

`dependencies="required-after:ebwizardry"`

> If you're using a Minecraft version prior to 1.12, replace `ebwizardry` with `wizardry`.

This will do two things:
1. It ensures Forge will always load your addon after wizardry. This is important for registries (and a few other things) to work correctly.
2. If a user tries to run the game with your addon installed, but without wizardry, Forge will display a message telling them that wizardry must be installed.

You can also specify a version or range of versions your addon is for, by appending an `@` followed by the [maven version range syntax](https://maven.apache.org/enforcer/enforcer-rules/versionRanges.html). For example, the following syntax only allows an addon to run with 4.2.x versions of wizardry:

`dependencies="required-after:ebwizardry@[4.2.0,4.3)"`

> The page on [structuring your mod](https://mcforge.readthedocs.io/en/latest/gettingstarted/structuring/) in the Forge documentation contains lots of useful information about the `@Mod` annotation and the `mcmod.info` file.

---

Now you're ready to start adding content to your addon mod! Check out the page on [[adding spells]] for a tutorial on how to add spells. Alternatively, take a look at the other tutorial pages on this wiki, or have a read of wizardry's code - I endeavour to write useful Javadoc comments for all of the important classes and methods; you can learn a lot just by reading through the code itself.

If you have a question about writing an addon for wizardry, come and poke me on [Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) or the [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) and I will answer it as well as I can! Consider also setting up a GitHub repository for your addon mod, it makes it a lot easier for me to help you.