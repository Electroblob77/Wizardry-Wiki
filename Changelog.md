This is a master changelog covering all released versions of wizardry. Individual versions have the relevant part of the changelog on their file pages, which are linked here.

## Key
^ Version updates  
\+ Added features  
\* Changed features  
\# Bugfixes  
\- Removed features

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