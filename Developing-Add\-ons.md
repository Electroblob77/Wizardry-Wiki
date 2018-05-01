> The information on this page is outdated and will be updated and reorganised soon. Please be patient!

This page explains how to use wizardry's inbuilt API to add your own spells.

### Prerequisites:

- A reasonable knowledge of the basics of modding with Minecraft Forge.
- A modding environment set up. I use eclipse, but you can use any IDE - I won't be referring to anything specific to eclipse. Make sure you use the correct version of Minecraft Forge for the version of wizardry you intend to use.
- A mod set up ready to add spells to (main mod class and proxies, plus a lang file).
Some of the information on this page is taken from coolAlias' tutorial on modding with APIs. It's more in-depth, but also contains a lot of information you won't need for making a spell pack. If you're interested, it's worth a read!

First you'll need to grab the **development** (deobfuscated) version of wizardry for the mod version you wish to make a spell pack for. These can be found under additional downloads on the relevant CurseForge file page, and you need the one that ends with 'deobf' [latest deobf version]. It's important to get the right **mod** version as well as the right Minecraft version. I recommend using the latest version of wizardry for the Minecraft version you want, as it will have the most API features and make your life easier. _Note that not all versions of wizardry have a development version, because changes between minor versions do not usually affect the API._

Put this file... anywhere you like, actually, so long as you know where it is - but the best way is to make a folder called 'libs' inside your project folder (the one with build.gradle in) and put it there. You'll then need to _add it to your build path_ in your IDE - if you don't know how to do this, have a look at your IDE's website and it should explain it. Once this is done, you should have a read-only copy of my code which can be accessed in the same way as the vanilla and forge code itself, and if you launch Minecraft in your development environment Wizardry should be fully working in-game.

However, if you open up any of the classes you'll notice they're completely unreadable. To get a readable version, you'll need to attach the source code. The source code can be found in the same place as the deobfuscated version, except this time you need the file that ends with 'sources' [latest source version]. Download this file and put it anywhere you like (I like to put it in the libs folder with the deobfuscated jar, but you don't have to). Now use your IDE to attach the source to the deobfuscated jar - again, if you don't know how, you'll need to look up how to do this for the IDE you're using.

_A note about permissions: You may **not** distribute the deobfuscated or source versions of Wizardry **in any way**. They are strictly for **mod development purposes only**, and do not come under the same licence as the mod itself. It is not necessary to include any of Wizardry's code or assets in a spell pack; if you have, you're doing it wrong!_

Next you'll need to specify Wizardry as a dependency for your mod, which is done in your @Mod annotation using the following syntax:

`dependencies="required-after:wizardry"`

There are three steps to making your own spell:

1. Create a new class and extend Spell. Spell can be found in the package electroblob.wizardry.spell and is the base class for all spells. I've taken the time to write proper javadoc comments for the methods and fields in this class, so read them carefully. You'll need to pass some values into the super constructor which define basic information about your spell, such as tier, element and mana cost. Most importantly, you'll need to pass in the **mod ID** of your add-on mod, or the spell icons won't work. Speaking of spell icons, you'll need to draw one of those too. I suggest starting with the blank icon, which can be found in `assets/wizardry/textures/spells/none.png`. Edit this with an image editing program and save your finished icon as a PNG image in `resources/[your mod ID]/assets/textures/spells`.
1. Write the code that makes your spell work in the `cast()` method. Use your imagination! Pretty much anything is possible with forge these days. There is a class in `electroblob.wizardry` called `WizardryUtilities` that you might find useful - I wrote it as a place to put various methods I needed for the mod, a lot of which might come in handy to you as well. It's worth a read anyway since it contains some information on best practices for making your spell fit seamlessly with the original mod.
1. Register your spell with wizardry in your `preInit()` method, using `Spell.register(spell)`. _This stage is absolutely vital!_ It tells wizardry that your spell exists, and wizardry will then add a spell book and scroll for you automatically.
That's it! You should now be able to cast your spell in the game.

You will need to add **localisations** for the spell to give it a nice, readable name and description. These should be put in **your lang file**, and the syntax is `spell.[unlocalised name]` for the spell name and `spell.[unlocalised name].desc` for the description.

If you want to add custom entities for your spell, there are some base classes you can use for that. `EntityMagicConstruct` is for stationary area-of-effect type entities, `EntitySummonedCreature` is for minions, `EntityMagicArrow` is for arrow-like projectiles and `EntityMagicProjectile` is for snowball-like projectiles. These are all fairly well-documented, and you can look at their subclasses for examples of how to use them. If you open up their corresponding spell classes, you can take a look at how best to spawn them, and you can see which renderers they use by looking in `ClientProxy` in `electroblob.wizardry.client`. You don't have to use these base classes, but they do make life easier.

You might also want to add particle effects to your spells. Vanilla Minecraft has a fair few itself, but there are also some that are added by wizardry. To spawn these, use `Wizardry.proxy.spawnParticle()`, and pass the `EnumParticleType` that you want to spawn into the method parameters.

`WandHelper` in `electroblob.wizardry` might also come in handy if you plan to interact with wand data at all.

It is good practice to specify that your mod is an add-on for Wizardry in your `mcmod.info` file. To do this, simply add the following lines:
```
"requiredMods": [ "wizardry" ],
"dependencies": [ "wizardry" ],
"useDependencyInformation": "true",
```
Now, if Wizardry is not installed with your spell pack, Forge will display a message to users telling them that Wizardry must be installed, and they won't be able to launch Minecraft without it. It also ensures that your mod gets loaded after Wizardry, which is important to ensure things work as they should.

You can compile your spell pack in the same way as any other mod, by running `gradlew.bat build` in the command window. If you put the deobfuscated jar in the `libs` folder, this should all work just fine. However, if not, the build will fail with compile errors. To fix this, add the following lines to your `build.gradle` file:
```
dependencies {
	compile files (
		"[filepath]"
	)
}
```
where `[filepath]` is the file path of the deobfuscated version of Wizardry, relative to your project folder.

### Publishing a Spell Pack

So, you've made a spell pack, and now you want to release it for the community to enjoy. That's great!

I do not place any restrictions on how or where you distribute your add-on mod, provided the following conditions are met:

You **credit me**, Electroblob, as the author of Wizardry, and **give a link** to the original mod (i.e. this page, the Minecraft Forum thread or the mods.curse.com page). After all, nobody can play your add-on without downloading Wizardry as well!
You do not make money off of your add-on mod in any way. **This includes AdFly** and other URL shorteners. The **only** exception to this rule is the **Curse rewards program**. Making money from videos featuring your add-on mod **is** allowed. (_The reason for this rule is as follows: I haven't put wizardry behind a URL shortener because I don't want my users to go through that just to download the mod, and as such I don't want users of add-ons to have to go through it either. If you want to discuss permissions, please don't hesitate to ask me._)
I would recommend using CurseForge to distribute your add-on mod, because it allows you to specify that it's an add-on to Wizardry.

I also ask that you notify me if you release an add-on mod, either by PM or in a comment on CurseForge or the Minecraft Forum thread. It's not required, but if you do I will add a link to your add-on in Wizardry's description!

If you have a question about writing a spell pack, please ask me and I will answer it as well as I can!