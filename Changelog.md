This is a master changelog covering all released versions of wizardry. Individual versions have the relevant part of the changelog on their file pages on curseforge. 

## Key
^ Version updates  
\+ Added features  
\* Changed features  
\# Bugfixes  
\- Removed features  

## Jump to...
[[1.12.2 Versions|Changelog#1122-versions]]  
[[1.11.2 Versions|Changelog#1112-versions]]  
[[1.10.2 Versions|Changelog#1102-versions]]  
[[1.7.10 Versions|Changelog#1710-versions]]  

---

## 1.12.2 Versions

### Version 4.1.4  
\# Fixed issue #104, a NoClassDefFoundError on server startup  

### Version 4.1.3  
\+ Added Chinese translations, courtesy of ZHENGLOC and dragon-evol  
\# Fixed issue #56, where the console would sometimes be spammed with the message "A mod has called ItemScroll#getItemStackDisplayName from the server side. Using thedeprecated server-side translation methods as a fallback."  
\# Fixed issue #64, where the ice age spell would incorrectly place snow on top of flowing water  
\# Fixed issue #70, where the server would crash in certain cases when executing the /allies command  
\# Fixed issue #71, where the server would crash when trying to write packet data for a projectile whose caster had logged out or otherwise been lost  
\# Fixed issue #73, where the game would crash with an OutOfMemoryError when trying to generate a wizard tower if there were no blocks beneath all or part of the foundations (usually in void or sky island worlds)  
\# Fixed issue #81 courtesy of HellFirePvP, where imbuement spells combined with a resplendent prism from Astral Sorcery resulted in an exploit allowing infinite enchantment levels to be obtained  
\# Fixed issue #90 (also known as issue #80, #91, #97 and #98), an ArrayIndexOutOfBoundsException crash related to wand NBT data  
\# Fixed issue #93, where wizards under the ice shroud effect would cause a crash when fed into a mob masher from mob grinding utils  
\# Fixed issue #96, where the arcane workbench GUI did not have a dark tint over the background like the other GUIs  
\# Fixed an issue where the spell switching would behave inconsistently when the next/previous spell keys were bound to mouse buttons (may be related to issue #79)  
\# Light no longer appears to grow indefinitely when the block fails to disappear; this reduces the effects of issue #101 but does not fix it  
\# Added an optimisation which prevents unnecessary key press packets

### Version 4.1.2
\+ Added a smelting recipe for crystal ore, resolving issue #43  
\+ Crystal ore now drops 1-4 experience when mined  
\+ Legendary wizard armour now grants +2 armour toughness per piece, like diamond armour  
\+ Added a mind control targets blacklist option to the config, resolving issue #39  
\+ Added an evil wizard spawn dimensions config option and restricted their spawning to 1 per chunk, resolving issue #26 - by default, evil wizards now only spawn in the overworld  
\+ Tab-completion for spell names in commands now works without having to specify the modid  
\* Reorganised the config file and config GUI  
\* Non-evil wizards' minions will no longer attack players unless the player in question has angered the wizard  
\* Converted all non-dynamic crafting recipes to JSON  
\# Told wizards to behave themselves and stop pretending to be villagers  
\# Told petrified creatures not to be scared of the moonlight, they now break out at night as intended  
\# Fixed issue #12, an issue with GL state changes  
\# Fixed issue #18, where there were two recipes for converting crystal blocks to crystals, one of which was incorrect  
\# Fixed issue #20, where the arcane workbench did not drop its inventory items correctly when broken  
\# Fixed issue #23, where stones of transportation did not drop when unsupported  
\# Fixed issue #31, where the game would crash when entities were added to immunity lists  
\# Fixed issue #32, where the elements tag of the random_spell loot function caused a crash  
\# Fixed issue #36, where the game would crash when opening the wizard's handbook if wizardry's keybindings were set to mouse buttons  
\# Fixed issue #37, where spirit horses and wolves (though the latter was unnoticeable) incorrectly used the loot tables for regular horses and wolves  
\# Fixed issue #38, where wizards' names would show up incorrectly in certain places  
\# Fixed issue #40, where sigils (and various other entities) would behave incorrectly if they could not retrieve their caster, for instance if their caster logged out or after a server reboot  
\# Fixed issue #41, where some death messages were not translated properly  
\# Fixed a related bug in where death messages would display upon death of a minion as a result of it having a custom name tag  
\# Fixed issue #42, where throwable projectiles would hit their thrower when aimed at an entity at close range  
\# Fixed issue #44, where wizard armour would behave weirdly in various ways  
\# Fixed issue #46, a rendering issue that occurred with Conquest Reforged installed  
\# Fixed issue #47, a rendering issue that occurred with Stellar API installed  
\# Fixed issue #48, where the arcane tinkering advancement would be granted incorrectly  
\- Removed the crafting recipe config options; use the recipe JSON files to modify recipes  

### Version 4.1.1
\* Mobs attacked by summoned creatures now revenge-target the summoned creature instead of its summoner  
\# Fixed issue #13, where the game would sometimes crash when wizards cast life drain or flame ray  
\# Fixed issue #14, where the spell cooldown bar remained at the bottom of the screen when the rest of the HUD was at the top  
\# Fixed a crash in the creative tab sorter with HQM installed

### Version 4.1.0
\^ Updated to Minecraft 1.12.2  
\* Changed the mod ID from 'wizardry' to 'ebwizardry' to avoid conflict with Escapee's wizardry mod  
\* Replaced achievements with advancements; these may be restructured in the near future to fit better with the advancement system  
\* Moved crafting recipes over to JSON format; note that mana flask charging recipes are dynamic (like vanilla repair recipes) and are therefore not editable

## 1.11.2 Versions

### Version 3.1.0
\^ Updated to Minecraft 1.11.2  
\* Updated Russian translations, courtesy of VilagVil  
\* Metamorphosis now supports husks and strays, skeletons now cycle through the three different variants (sneak-cast to reverse), and the spell also works on skeleton minions (yes, you can now have wither skeleton archers shooting fire arrows for you!)  
\* Changed the transportation stone item from a 3D block model to a 2D texture, so it isn't off the bottom of the screen when holding it  
\# Many bugfixes, too numerous to list here (see the GitHub repository for a full history of changes)

## 1.10.2 Versions

### Version 2.1.2
\# Fixed sparkle particles not being animated (this was accidentally disabled when testing a new feature)  
\# Fixed inability to upgrade non-elemental wands using tomes of arcana  
\# Fixed curseforge issue #28, where keybinds would be reset on game launch  
\# Fixed curseforge issue #30, where the game would crash when casting mind control on a mob that already had the mind trick status effect

### Version 2.1.1
\# Fixed curseforge issue #27 (github issue #3), where the game would crash during loot generation with an ArrayIndexOutOfBoundsException

### Version 2.1.0 - First full 1.10.2 release
\* Did some internal refactoring in preparation for updating to Minecraft 1.11 and 1.12  
\* Finished implementing various API features and code improvements  
\* Spell modifiers in the /cast command now use NBT format, for example {damage:1.5, range:2}  
\* Changed all the keys in all the lang files to lowercase with underscores, and prepended wizardry's mod id to most of them - this should eliminate naming conflicts  
\* Wizardry's entity ids (as used in commands) are now all lowercase with underscores (for example, lightning_wraith) - this fixes the problems caused by having spaces in the names  
\* As a result of the internal changes, some items changed their ids (for example, wand_basic is now magic_wand) - the model files have been renamed accordingly, and existing saves will be remapped automatically  
\# Fixed some wizard tower generation issues (namely, door orientation and a lack of torches or chests)  
\# Fixed the rendering of shields  
\# Fixed the spectral bow animation  
\# Fixed the clairvoyance spell  
\# Fixed a bug where many spells would not play their sounds when cast using commands  
\# Fixed a bug where some spells would appear to cast twice when using a scroll  
\# Fixed a bug where modifiers in the /cast command did nothing for non-continuous spells  
\# Fixed a bug where wizardry's timed enchantments appeared on enchanted books in dungeon chests  
\# Fixed a bug where the random_spell loot function would generate incorrect warning messages  
\# Fixed a bug where the [Empty Slot] spell book would occasionally generate with the default loot tables; this should only happen when a lot of spells are disabled in the config  
\# Fixed a bug where spells that were disabled in the config could still be cast using commands  
\# Fixed issue #7 (from 1.7.10), where revenge effects could cause an infinite loop if two players used them on each other at the same time  
\# Fixed issue #12, a crash related to loot tables  
\# Fixed issue #25, where some continuous spells would keep resetting on the client side, causing them to be ineffective  
\# Fixed issue #26, a crash related to the mind control spell

### Version 1.10.2 Beta 3
\# Fixed issue #15, a server crash related to projectiles  
\# Fixed a bug where the game would crash during loot table loading, when the random_spell loot function was used with criteria which did not match any enabled spells; this now prints a warning to the console instead

### Version 1.10.2 Beta 2
\# Fixed issues #13, #16 and #17, crashes for various lightning spells when charging creepers

### Version 1.10.2 Beta 1
\^ Updated to Minecraft 1.10.2  
\^ Updated to Java 8  
\+ Added special loot table functions specific to wizardry; details will be added to the documentation  
\+ Added the block breaking animation when breaking petrified creatures (this wasn't possible in 1.7.10)  
\* Converted wizardry's loot for chests and mobs to use the loot table system; the rarities of all the items are approximately the same  
\* Wizardry loot now also spawns in igloo chests  
\* Wands can now be used in the offhand  
\* Conjuration spells now conjure their item in the main hand if the wand is in the offhand and the main hand is empty  
\* Priority for mana siphoning, imbuement spells and identification is now main hand > offhand > hotbar left-to-right  
\* As a result of the rewrite of summoned creatures, many continuous spells can now be cast by wizards  
\* Evil wizards now make witch sounds, but at a lower pitch  
\* Glide and flight now use the elytra 'whoosh' sound (flight still has the flapping sound, but glide doesn't)  
\- Removed all ID config options since they are no longer necessary in Minecraft 1.10.2

## 1.7.10 Versions

### Version 1.1.4
\+ Wands with condenser upgrades now regenerate mana when in an arcane workbench as well as in a player inventory  
\+ Added config options to change the command names  
\+ Added a config option to prevent summoned creatures from revenge-targeting their owners  
\* Cleaned up and made some changes to the code in preparation for porting to Minecraft 1.10.2  
\# Fixed a bug where elemental wizard armour would be missing its textures when using a language other than English  
\# Fixed a bug where the /help command would not display the help for wizardry commands correctly  
\# Fixed a bug where the config would not generate when an enchantment ID conflict occurred, meaning there was no value to change to fix the conflict  
\# Fixed a ticking entity crash with shields  

### Version 1.1.3
\# Fixed a crash when opening the arcane workbench on a dedicated server  
\# Fixed a bug where the client was not updated when discovering certain spells, causing the spell to appear to remain undiscovered until world reload or re-log  
\# Fixed a bug where petrified creatures were not rendering, and improved the efficiency of the rendering code as a result  

### Version 1.1.2
\* Shadow wraiths are now immune to the wither potion effect itself as well as withering spells  
\# Fixed a crash when opening a GUI on a dedicated server  
\# Fixed a crash when a firebomb hits the ground near an entity  
\# Put the missing URL back into the mcmod.info file  

### Version 1.1.1
\# Fixed a crash when opening the arcane workbench  
\# Fixed the item swing animation not playing when using scrolls  
\# Fixed a bug where continuous spells were casting when they shouldn't be after switching spells  

### Version 1.1 - The co-op update
^ Updated to use Forge build 1.7.10-10.13.4.1558  
\+ Added evil wizards who generate in their own towers and rarely spawn at night, like witches. They won't trade with you; instead they will attack you if you get too close. Oh, and they drop cool items if you kill them.  
\+ Added chests to the towers of evil wizards, filled with magical loot!  
\+ Added 30 new spells  
\+ Added wand attunement upgrades  
\+ Added more achievements  
\+ Holding shift and scrolling whilst holding a wand will now cycle through the spells  
\+ Using bonemeal on a grass block now has a chance to grow crystal flowers  
\+ Added the ally designation system: right-click a player with a wand whilst sneaking to designate them as an ally. Right-click them again to remove them from your designated allies. Also supports the vanilla scoreboard system; players on your team automatically count as your allies.  
\+ Added discovery mode: if enabled in the config (enabled by default), newly discovered spells will be unreadable until you cast them  
\+ Added scrolls of identification  
\+ Telekinesis can now be used to disarm players, and wizards can now use it on players to do just that  
\+ Added the /cast, /ally, /allies and /discoverspell commands  
\+ Whilst holding a wand, sneak-right-clicking a summoned creature now allows you to control what it attacks  
\+ Right-clicking a wizard with a spell book while in creative mode will replace one of the wizard's spells with that spell, provided they can cast it - this was mainly for development purposes, but it has been left in for you to play around with  
\+ Added a config option to prevent players from disarming each other using telekinesis  
\+ Added config options for global damage scaling of spells cast by players and by NPCs  
\+ Added a config option to enable/disable friendly fire; if disabled no spells will damage or negatively affect your allies in any way. Personally I think this is unbalanced, but it's there if you want it.  
\+ Added a config option to whitelist or blacklist mobs that summoned creatures or wizards can attack  
\+ Added a config option to turn spell discovery on or off  
\+ Added a config option to change the multiplier limit for the /cast command (use with caution!)  
\+ Added config options for making mobs immune to different types of magic  
\+ Summoned creatures' name tags now support localisations  
\+ Added localisations for the config option descriptions in the config gui  
\+ Added localisations for the key descriptions in the controls menu  
\* Allies can enter your forcefield  
\* Any spells you cast that have a lightning chaining effect will not chain to your allies  
\* Spells that seek their target will not seek your allies; however, if an ally is directly in the way they will still take damage as normal  
\* Allies won't trigger your traps  
\* Creatures you mind control will ignore your allies  
\* Summoned creatures will now attack other players, unless that player is an ally of the player that summoned them (spirit wolves are unchanged; they still behave like regular wolves)  
\* Mobs killed by a creature you summoned will now behave as if you killed them directly, dropping xp and rare drops, and granting siphon mana  
\* Summoned creatures will now attack wizards  
\* Wizards can now use many of the summoning spells  
\* Wizards can now use various other spells they couldn't use before, including mind control and wither skull  
\* Wizards will no longer cast spells which grant potion effects if they already have that potion effect  
\* Wizards can no longer cast forcefield or ring of fire when they are inside one  
\* Wizards now have wands powerful enough for the spells they spawn with  
\* Wizards and summoned creatures will now attack slimes and magma cubes  
\* Wizards will attack you if you damage their tower  
\* Wizards will no longer trade with you if you attack them or damage their tower  
\* Ice spells no longer affect ice creatures (namely snow golem, ice wraith and ice giant)  
\* Lightning spells no longer affect lightning creatures (namely lightning wraith and storm elemental)  
\* Withering spells no longer affect shadow wraiths  
\* Damage dealt by blast spells is now reduced by the blast protection enchantment  
\* Damage dealt by projectile spells is now reduced by the projectile protection enchantment  
\* Mind control is now a potion effect which lasts for a set duration, so mind controlled creatures will keep attacking mobs until it wears off  
\* Mind control no longer works on boss mobs like the enderdragon or intelligent mobs like wizards  
\* Some spells now display a chat message if a creature resists them  
\* Petrify now extinguishes targets if they are on fire  
\* Petrified creatures no longer break out at sunset; instead they have a chance to break out which increases the lower the light level (above light level 7 the chance is 0, so you can keep a mob petrified forever with torches!)  
\* Petrified creatures are now the shape of that creature with armour and held items, rather than just being blocks of stone  
\* The player must now be sneaking in order to dispel a spirit wolf by right-clicking it with a wand; this brings it in line with the spirit horse behaviour  
\* Arrow rain is now better centred on the position aimed at  
\* Nerfed black hole damage by 33%  
\* Glide is now 33% slower  
\* Adjusted the mana cost of a few spells (quite a few advanced spells are now cheaper)  
\* Moved things around in the arcane workbench GUI to allow for the new attunement upgrades, and changed the appearance slightly to make it look nicer  
\* The wand upgrades displayed in the arcane workbench GUI are now interactive, showing tooltips when hovered over with the mouse  
\* Sigils are now invisible to players except for the caster and their allies (they can still be seen by the particles if you look closely)  
\* Spectral bow now zooms in like a regular bow  
\* Overhauled the wizard tower generation code, resulting in huge efficiency improvements  
\* Wizard towers now obey the generate structures world creation option  
\* Wizard towers now change some of their materials depending on the biome  
\* Wizard towers now generate in several different shapes  
\* Wizard towers are sometimes flipped so the staircase goes clockwise, for a bit more variety, along with their usual randomised orientation  
\* Spell books are now more common in chests  
\* Wands are now less common in chests  
\* Magic crystals are now slightly more common in chests  
\* Overhauled some of the code in the base spell class, mostly related to RNG and generation. This was necessary for some of the other fixes.  
\* Overhauled the code for the spirit horse; spirit horses can now jump like regular horses  
\* Optimised the sending of spell packets  
\* Tidied up the code related to wand NBT, making it all a lot neater and less prone to errors  
\* Altered the way spell IDs are assigned internally, meaning existing spell books and scrolls won't change when the mod is updated; this now means the spell books in the creative tab are not necessarily in metadata order  
\* Crystal flowers now spawn fewer particles  
\* Firebombs and poison bombs now spawn more particles  
\* Phoenix flames are now bigger  
\* Ice giants have a new model and texture  
\* Changed the potion effect icon textures  
\* Some particle effects have new textures  
\* Tornado particles now look like the surrounding blocks (grass, sand, water, etc.), and tornadoes that pass over lava will now set mobs on fire  
\* Range upgrades have a new texture  
\* Updated a few spell icons  
\* Updated a few spell descriptions  
\* Updated The Wizard's Handbook  
\* The ids in the config menu now have their own page  
\# Fixed a bug where only spells that had been discovered could be bound to scrolls in creative mode  
\# Fixed a bug where certain entities would appear to catch fire when in lava or fire that shouldn't do so  
\# Fixed a bug where blast upgrades did not count towards the total upgrade limit for a wand  
\# Fixed a bug where the doors of wizard towers would not always generate properly  
\# Fixed a bug where wizard towers would hardly ever generate in deserts  
\# Fixed a bug where wizards sometimes spawned with spells they couldn't cast; as a result they now sometimes cast spells that are not from their element  
\# Wizards no longer run away from zombies  
\# Lightning hammers no longer get moved by flowing water  
\# Ice age now freezes lava into obsidian and cobblestone as it is supposed to  
\# Growth aura now grows grass and flowers as it is supposed to  
\# Phoenix rubber-banding seems to have fixed itself!  
\# Ignite no longer spawns particles inside the player's head  
\# Fixed a bug where firebombs and poison bombs thrown from their items did not spawn particles  
\# Fixed a bug with the sound for firestorm  
\# Tornado now uses a moving sound like meteor and lightning hammer  
\# Fixed a bug with the bounding box for ice giants; their name plate now renders in the correct position above their head  
\# Fixed issue #3, where an error report would appear in the console on world load, despite no crash or visible error occurring  
\# Fixed a bug causing the dedicated server to crash when arrow rain was cast  
\# Fixed issue #6, where the dedicated server would crash when casting the replenish hunger spell  
\# Fixed a bug where the config file used translated names, causing multiple options to be added for different languages  
\# Some other minor bugfixes  
\- Fireskin and ice shroud no longer affect attacks; this ability overlapped too much with flaming weapon and freezing weapon. The mana cost of these spells has been significantly reduced to compensate.  

### Version 1.0.4
\# Fixed lightning sigil ticking entity crash  

### Version 1.0.3
\+ Added translations into Russian, courtesy of VilagVil  
\* Re-textured the arcane workbench GUI  

### Version 1.0.2
\# Fixed entity ID conflict with EnderIO and others; the wizard spawn egg has moved to the wizardry creative tab as a result  

### Version 1.0.1
\# Fixed tile entity name conflict with RFTools  