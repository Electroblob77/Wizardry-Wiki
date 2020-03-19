This page explains how to add [[spells]] to your spell pack. 
本页面将介绍如何将更多[[法术]]添加到你的法术列表内。

## 准备
- An addon mod ready to add spells to. You should have completed everything in the [[developing addons]] tutorial at this point.
- 一个添加法术的附属mod。你需要先完成[[developing addons]]的所有步骤。 
- Basic knowledge of the JSON file format.
- 关于 JSON 的基础知识。 
- An idea for a spell! The only limits here are your imagination and your programming skill, though the latter can always be improved with practice - and there's a whole modding community out there that can help you out if you get stuck.
- 对法术足够的想象力！ 限制你的只有你的想象力和编程能力, 尽管后者可以通过不断地训练提高 - 如果你有困难，可以到mod社区求助。

## 编写法术类

First of all, you'll need to write a new class for your spell, where you can put all of the code that makes it work. Create a new class and have it extend `Spell`. The `Spell` class can be found in the package `electroblob.wizardry.spell` and is the base class for all spells. I've taken the time to write full Javadoc comments for the methods and fields in this class, so I recommend you read them carefully!

首先，你需要编写一个新的法术类，这是给你运行代码的地方。新增一个类作为`Spell`的拓展。你可以在`electroblob.wizardry.spell`包内找到`Spell`类。 我为 Javadoc 写了一个完整的注释去说明类中的方法和字段，我推荐你去认真阅读它们。

In this class, create a new constructor with no arguments, and inside it, call the super constructor in the `Spell` class. There are **two** super constructors in `Spell`, and you need to make sure you use the one which takes an additional `modID` argument. You'll then need to pass some values into the super constructor which define basic information about your spell:

在这个类中新建一个没有参数的构造函数（constructor），并且调用在`Spell`类中的超级构造函数（super constructor）。`Spell`中有**两个**超级构造函数，你需要确保自己添加了一个`modID`附加参数。接下来你需要给超级构造函数传递一些参数，这是该函数关于法术的参数信息：

- `modID` The **mod ID** of your addon mod. This is required so that wizardry knows which mod the spell is from and where to look for your spell icon.
- `name` The unlocalised name of your spell. This should be in all lowercase with underscores_between_words.
- `action` The `EnumAction`, or animation, that the player performs when casting the spell.
- `isContinuous` True to require the use item button to be held down in order to cast the spell, false for a single click to cast the spell.

The next thing you'll need to do is override the _first_ `cast(...)` method in `Spell`. This is the method that makes your spell work, and it gets called whenever a _player_ casts the spell (see below for an explanation of how to get wizards and other entities to cast your spell). Write the code that makes your spell work in this method. Your spell could do any number of different things, so use your imagination! Pretty much anything is possible with Forge these days. You might find it useful to look through some of wizardry's own spell classes for examples.

The `cast(...)` method returns a `boolean` which tells wizardry whether the spell succeeded or not. You should return true when the spell succeeds and false if not. For example, [[Heal]] returns false when the caster has full health and true if not. Returning true means mana is consumed from the wand that cast the spell, or the scroll used to cast the spell is consumed.

> There is a class in `electroblob.wizardry.util` called `WizardryUtilities` that you might find useful - I wrote it as a place to put various methods I needed for the mod, some of which might come in handy to you as well. In particular, it contains methods for working with blocks and coordinates, entities and players.

## Creating a spell JSON file

As of wizardry 4.2, all spells have a JSON properties file located in `assets/[modid]/spells` which defines most of the information about the spell (previously this was all defined in the spell's constructor). You'll need to create a JSON file for your spell in order for it to work properly. See [[Spell Properties]] for an explanation of how this file is structured. Leave the `base_properties` object empty for now - you can add spell-specific properties later.

> Wizardry loads properties files automatically for every spell when the game loads, and will print a warning to the console if any of them are incorrect or missing.

## Registering your spell

To get your spell to appear in game, you'll need to register it in a similar way to blocks and items. Like blocks and items, each spell has a single instance. In Forge 1.10 and higher, this is done using **registry events**. To register your spell using registry events, make an event handler (or open up an existing one) and make a new method that subscribes to `RegistryEvent.Register<Spell>` (see the Forge documentation on [events](https://mcforge.readthedocs.io/en/latest/events/intro/) if you don't know how). Inside that method, create a new instance of your spell class and register it using `event.getRegistry().register(spell)`. The method should now look something like this:

```java
@SubscribeEvent
public static void register(RegistryEvent.Register<Spell> event){

    event.getRegistry().register(new YourSpell());

}
```

> The older `GameRegistry.register(...)` methods still exist in Forge, but because of how wizardry processes the registered spells, these **will not work** for spells - you must use registry events.

That's it for the required stuff! If you load up the game, you should now see a spell book and (if your spell isn't continuous) a scroll for your spell in the Spells tab of the creative mode inventory, and with any luck you'll be able to cast your spell in-game.

## Making your spell look nice

As you probably know, all spells in wizardry have an icon which appears in their spell book and on the spell HUD. You'll need to draw an icon for your spell, which should be a pictorial representation of your spell. I suggest starting with the blank icon, which can be found in `assets/wizardry/textures/spells/none.png`. Edit this with an image editing program (I use GIMP) and save your finished icon as `[your spell name].png` in `resources/[your mod ID]/assets/textures/spells`, where [your spell name] is the unlocalised name you gave your spell in its constructor.

You will need to add **localisations** for the spell to give it a nice, readable name and description. These should be put in **your lang file**, located in `assets/[your mod ID]/lang/en_US.lang`. The syntax is `spell.[unlocalised name]` for the spell name and `spell.[unlocalised name].desc` for the description.

## Making wizards cast your spell

Making [[wizards|Wizard]] cast your spell is fairly simple once you have written the code for players casting it. This time, you'll need to override the _second_ `cast(...)` method in `Spell`. You'll notice a couple of differences between this method and the player method:
- The `caster` argument is an `EntityLiving` instead of an `EntityPlayer`. This is because this method deals with non-player entities casting the spell.
- There is an additional `target` argument of type `EntityLivingBase`. This is the target that the NPC aimed at when it cast the spell.

Other than that, the method works in exactly the same way. I suggest copying the code from the other `cast(...)` method and adapting it to make it work with non-player entities - you might not have to do anything, or you might have to change it completely, depending on the spell.

You'll also need to override `Spell.canBeCastByNPCs()` to return true to allow wizards to spawn with your spell equipped.

## Standard spell superclasses

Since many spells are similar to each other, there is a set of abstract superclasses for common types of spell. These can greatly reduce the code required to make a spell work, and make sure all spells of similar types behave in a standard way.

Wizardry has the following standard spell classes built-in:

- `SpellArrow`: for spells that shoot projectiles extending `EntityMagicArrow` (see [[Adding Entities]])
- `SpellBuff`: for spells that apply one or more potion effects to their caster
- `SpellConjuration`: for spells that conjure items (normally these items implement `IConjuredItem`)
- `SpellConstruct`: for spells that summon an `EntityMagicConstruct` (see [[Adding Entities]]) at the caster's position
- `SpellConstructRanged`: for spells that summon an `EntityMagicConstruct` (see [[Adding Entities]]) at the position aimed at
- `SpellProjectile`: for spells that shoot projectiles extending `EntityMagicProjectile` (see [[Adding Entities]])
- `SpellMinion`: for spells that summon entities implementing `ISummonedCreature` (see [[Adding Entities]])
- `SpellRay`: for spells that use raytracing. This includes instant 'bolt' spells like [[poison]] and continuous 'stream' spells like [[flame ray]]

Some of these classes are _parametrised_, meaning a type parameter should be supplied when extending them. This is usually the type of entity the spell summons/shoots.

## Further information

That covers the basics of adding your own spells to wizardry, but it's likely that at some point you'll want to do something that requires more than just a spell class. Fortunately, wizardry already has some classes that can help you:

- If you want to add custom entities for your spell, there are some base classes you can use for that. See [[Adding Entities]] for more details.
- You might also want to add particle effects to your spells. Vanilla Minecraft has a fair few itself, but there are also some that are added by wizardry. To spawn these, use `Wizardry.proxy.spawnParticle(...)`, and pass the `WizardryParticleType` that you want to spawn into the method parameters.
- `WandHelper` in `electroblob.wizardry` might also come in handy if you plan to interact with wand data at all.
