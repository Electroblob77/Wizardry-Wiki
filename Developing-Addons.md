> These tutorials are for versions of wizardry running on Minecraft 1.12.2. The information here should also work with 1.10 and 1.11 versions of wizardry, though there may be minor differences. For 1.7.10 versions of wizardry, see the [legacy spell packs tutorial](https://minecraft.curseforge.com/projects/electroblobs-wizardry/pages/making-spell-packs).

These pages explain how to program addon mods for _Electroblob's Wizardry_, particularly **spell packs**. This page covers setting up your workspace ready to work with wizardry's code. See the links to other pages for how to add spells and other content.

## Pages in this category

[[Adding Spells]]  
[[Adding Wand Upgrades]]  
[[Adding Entities]]  
[[Miscellaneous Features]]  
[[Compiling and Publishing]]

---

## Prerequisites

- A reasonable knowledge of the basics of modding with _Minecraft Forge_: an understanding of simple Java, how to make blocks, items and such like, and familiarity with the registry and event handling systems. That said, I have made every effort to explain things as clearly as I can along the way.
- A modding environment set up. I use eclipse, but you can use any IDE - I won't be referring to anything specific to eclipse. Make sure you have the correct version of Minecraft Forge for the version of wizardry you intend to use. Usually this will be the latest version of Forge for the version of Minecraft you are using.
- A mod set up ready to add spells to (main mod class and proxies, plus a lang file).

## Setting up your workspace

First you'll need to grab the **development** (deobfuscated) version of wizardry for the mod version you wish to make a spell pack for. These can be found under additional downloads on the relevant CurseForge file page, and you need the one that ends with 'deobf'. Make sure you get the right **mod** version as well as the right Minecraft version. I recommend using the latest version of wizardry for the Minecraft version you want, as it will have the most API features and make your life easier. _Note that not all versions of wizardry have development versions, because changes between minor versions do not usually affect the API._

Put this file... anywhere you like, actually, so long as you know where it is - but the best way is to make a folder called 'libs' inside your project folder (the one with build.gradle in) and put it there. You'll then need to _add it to your build path_ in your IDE - if you don't know how to do this, have a look at your IDE's website and it should explain it. Once this is done, you should have a read-only copy of my code which can be accessed in the same way as the Minecraft and Forge code itself, and if you launch Minecraft in your development environment wizardry should be fully working in-game.

However, if you open up any of the classes you'll notice they're completely unreadable. To get a readable version, you'll need to attach the source code. The source code can be found in the same place as the deobfuscated version, except this time you need the file that ends with 'sources'. Download this file and put it anywhere you like (I like to put it in the libs folder with the deobfuscated jar, but you don't have to). Now use your IDE to attach the source to the deobfuscated jar - again, if you don't know how, you'll need to look up how to do this for the IDE you're using.

> Unlike the compiled versions of wizardry, the source and deobf versions are for personal use and mod development only and may not be distributed. Please see the permissions section on wizardry's CurseForge page for more information.

## Specifying wizardry as a dependency

Next you'll need to specify Wizardry as a dependency for your mod, which is done in your `@Mod` annotation using the following syntax:

`dependencies="required-after:ebwizardry"`

> If you're using a Minecraft version prior to 1.12, use `dependencies="required-after:wizardry"` instead.

It is good practice to specify that your mod is an addon for Wizardry in your `mcmod.info` file. To do this, add the following lines:
```
"requiredMods": [ "wizardry" ],
"dependencies": [ "wizardry" ],
"useDependencyInformation": "true",
```
Now, if wizardry is not installed with your spell pack, Forge will display a message to users telling them that wizardry must be installed, and they won't be able to launch Minecraft without it. It also ensures that your mod gets loaded after wizardry, which is important to ensure things work as they should.

> The page on [structuring your mod](https://mcforge.readthedocs.io/en/latest/gettingstarted/structuring/) in the Forge documentation contains lots of useful information about the `@Mod` annotation and the `mcmod.info` file.

---

Now you're ready to start adding content to your addon mod! Check out the page on [[adding spells]] for a tutorial on how to add spells. Alternatively, take a look at the other tutorial pages on this wiki, or have a read of wizardry's code - I endeavour to write useful Javadoc comments for all of the important classes and methods; you can learn a lot just by reading through the code itself.

If you have a question about writing an addon for wizardry, come and poke me on Discord, CurseForge or the Minecraft Forum and I will answer it as well as I can! Consider also setting up a GitHub repository for your addon mod, it makes it a lot easier for me to help you.