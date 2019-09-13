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

### Version 4.2.3 - Hotfix  
  
\# Temporarily disabled the spells sound category to prevent issue #238, this will be reinstated later when a solution is found  
\# Fixed JEI spamming the log with errors about mana flask charging recipes having no output  
\# Fixed issue #242, where charging an item with a mana flask would wipe its NBT data  
  
### Version 4.2.2 - More tweaks and fixes  
  
\+ Added Polish translations, courtesy of Trozuu  
\+ Spell books and scrolls now display their tier, element and spell type when advanced tooltips are enabled (F3+H) - this allows you to search by element or spell type in the creative menu, hooray!  
\+ Conjure block now requires the player to be sneaking to dispel a block  
\+ Added support for WAWLA enchantment descriptions to the en_us and en_gb lang files, fixing #210  
\+ Added a 5x bonus progression modifier for casting an undiscovered spell for the first time  
\* Wands now only track the last 5 spells cast, instead of 10 - this means that cycling through all the spells in sequence on any wand incurs no repetition penalty to progression  
\* Reduced the required progression for all tiers by about 30-35%  
\* Increased the default rarity of wizardry's structures, reset them in the config menu to get the new values  
\* Combustion rune now respects player block damage and mob griefing settings, see issue #217  
\* Items can no longer be recharged with mana flasks if they are already fully charged  
\* The game will no longer launch with Forge versions older than the required version  
\# Fixed issue #68, where mana flask charging recipes did not work correctly in non-vanilla crafting grids  
\# Fixed issue #172 (also #191, #198, #199, #205, #211, #217, #220, #226, #230, #232 and #234), an ArrayIndexOutOfBoundsException crash related to wizardry's custom sound category  
\# Fixed issue #179, where the possession spell shaders were applied to all players instead of just the one using possession  
\# Fixed issue #182, where various construct spells would crash the game when cast by dispensers  
\# Fixed issue #183, yet another ArrayIndexOutOfBoundsException in wand NBT data  
\# Fixed issue #185, a crash related to summoned creature revenge-targeting  
\# Fixed issue #190, where certain forfeits were able to break or overwrite blocks they should not  
\# Fixed issue #196, a crash related to sound loops checking if they should continue  
\# Fixed issue #205, a ConcurrentModificationException crash when rendering arcane lock effects  
\# Fixed issue #216, where the game would sometimes crash when a shrine was conquered  
\# Fixed a crash when clicking an already-remembered stone circle, see issue #217  
\# Fixed spectral bow repeatedly re-equipping when used, see issue #217  
\# Fixed imbuement spells not working correctly, see issue #217  
\# Fixed issue #219, a crash on startup related to lightning hammer item attribute modifiers  
\# Fixed issue #228, a dedicated server crash related to disintegration effects  
\# Fixed issue #229, a NullPointerException crash during transportation teleporting  
\# Fixed issue #236, a crash with targeting events related to possession  
\# Fixed lighting issues with spectral blocks, they no longer emit light but always appear bright  
\# Fixed clairvoyance particles not moving correctly  
\# Fixed some typos in the lang files  
  
### Version 4.2.1 - Hotfix  
  
\+ Added a config option to specify blocks that count as trees for wizardry's structure generators - fixes issue #165  
\+ Added various translations which were missed in the 4.2.0 update  
\* The wizard tower rarity config option now resets itself to the default value (600) when it is below the minimum value (20) - this means old configs should now change automatically  
\# Fixed issue #49, where the game would crash when entities were added to the config immunity lists  
\# Fixed issue #166, a crash caused by a NullPointerException in potion events  
\# Fixed issue #171, where the game would crash with a JSON syntax error when recipes referenced from the handbook were removed - a blank recipe grid is now displayed instead when this happens  
\# Fixed issue #176, another ArrayIndexOutOfBoundsException in wand NBT  
  
### Version 4.2.0 - An update so big the changelog is in multiple parts!  
  
#### General:  
^ Updated to Forge 1.12.2 - 14.23.5.2814  
\* Sanitised the jar filename a bit (removed the spaces and the apostrophe, apparently Maven doesn't like them)  
  
#### Cosmetic:  
\+ Added many new particle effects to various spells  
\+ Added a variety of new sounds, including spell selection, spell binding in the arcane workbench, and casting of various spells  
\+ The arcane workbench GUI now has a fancy animation when the apply button is pressed  
\+ Conjured items now have an appearing/disappearing animation  
\+ Creatures with the frostbite effect now show an icy layer over their skin  
\+ Wizard robes now bend when the wearer is sneaking or sitting down  
\+ Legendary wizard armour now has its own armour texture variants (the items still look the same)  
\+ The spell HUD has a new default texture and now supports different skins defined using JSON files in resource packs, which can be selected in the config menu - the base mod now comes with 19 different skins to choose from!  
\+ The spell HUD now shows the previous and next spells and has a spell-switching animation  
\+ Sixth sense and transience (along with two of the new spells) now have fancy shaders!  
\+ The spell HUD position config option now has four more options allowing the HUD to switch from left to right depending on which hand the active wand is held in  
\+ Wands now display their progression when advanced tooltips are enabled  
\+ Added a spells sound category, use the slider in Options -> Music & Sounds to change the volume of spells separately to other sounds  
\+ Added a config option to turn off spell shaders  
\+ Added a config option to reverse the spell switching scroll direction  
\* The default spell HUD scroll direction has been reversed so it works the way you'd expect it to with the new animation  
\* The spell HUD now scales itself to get out of the way of the hotbar and offhand slot - this normally only happens with a large GUI scale or a small game window, and can be avoided by changing the HUD position, GUI scale or the player's primary hand  
\* Completely rewrote the rendering for arc/lightning ray/chain lightning, it is now fully 3D and no longer an entity, resulting in improved performance  
\* Completely rewrote the rendering for forcefields, they are now actual spheres and not made of particles, and have particle effects when things hit them  
\* Shockwave has a new animation and sound  
\* Rewrote the particle system to use the texture atlas, resulting in a major performance improvement for large numbers of particles (such as with the blizzard spell)  
\* Particles can now have simple physics, for example, flame ray spreads out when it hits a block  
\* Spirit animals now fade away when dispelled  
\* All sounds are now defined in separate sound events  
\* Continuous spell sounds are now looped nicely, with start and end sections and a much longer loop  
\* Retextured most of the blocks  
\* Retextured nearly all of the items, including all of the wands  
\* Retextured a number of spell icons  
\* Retextured a few entities  
\* Retextured all of the book GUIs and added subtly different variations for different tiers of spell book  
\* Updated the Wizardry logo  
\* Most chat readouts (excluding commands) have been changed to toast notifications above the hotbar  
\# Fixed render pass/layer issues for various translucent things  
\# Fixed a bug where status effects with custom particles (e.g. frostbite) would not update on the client when applied to non-players, causing them to appear to continue indefinitely  
\# Status effects with custom particles no longer mix their colours with other status effects  
\# Ice spikes no longer appear black when inside blocks  
\# Fixed transparency for cobwebs from the cobwebs spell  
\# Flame particles no longer appear dull and translucent for some spells (firebomb, flame ray, phoenix attacks, etc.)  
\# Fixed various spells where particles that were meant to appear did not  
\# Fixed z-fighting on the brim of wizard hats when they have the enchantment glint effect  
\# Wizard hats no longer clip through the hat layer of player skins, fixing issue #83 - the brim is slightly wider now to keep it in proportion  
\# The arcane workbench in-world animation is now smoother  
\# The spell HUD no longer displays in spectator mode  
\# Wizards no longer spawn heal particles around themselves when they first spawn  
\- Removed the mana readout in item tooltips (you can still view the exact mana in an arcane workbench - or by pressing F3 \+ H, you spoilsport...)  
  
#### Blocks:  
\+ Added runestone and runestone pedestals  
\+ Added elemental crystal block variants  
\+ Stones of transportation now display particles at the positions of any stones missing from the circle when right-clicked  
\* Magic light blocks can now be broken in creative mode  
\# Fixed issue #128, where magic light blocks would grow indefinitely on server/client desync  
\# Arcane workbenches no longer connect to fences, panes, iron bars or walls  
  
#### Items:  
\+ Added artefacts! These can only be found by exploring shrines, which will each contain a single artefact  
\+ Added elemental crystal variants, which may be used to craft novice elemental wands  
\+ Added wand progression - a new mechanic in which wands gain progression from casting spells and must reach a certain amount of progression before they can be upgraded to the next tier (tomes of arcana are still required to do the actual upgrading)  
\+ Added a config option to revert to legacy wand levelling, because I know you'll ask  
\+ Added 3 armour enchantments: Magic Protection, Frost Protection and Shock Protection - these can be applied to any armour, including wizard armour, and may be applied to or found in enchanted books  
\+ Wizard armour items now show a tooltip in the arcane workbench with how much mana they have left  
\+ Added spark bombs as an item - they work in much the same way as firebombs, poison bombs and smoke bombs and can be crafted or found in dungeon chests  
\+ Added wand melee upgrades, which allow wands to deal more melee damage  
\+ Added purifying elixir for removing curses  
\+ Added astral diamonds, which can be found as loot and are now required to buy master-tier items  
\+ There are now three different sizes of mana flask, which restore 300, 700 and 1400 mana respectively and can occasionally be found in dungeon chests or dropped by wizards, as well as being craftable as before  
\+ Added spawn eggs for all of wizardry's non-vanilla summoned creatures  
\* Magic wands are now empty when first crafted  
\* Wizard armour can now be enchanted using an enchantment table, as well as with an anvil as before (though that was not intended prior to this release!) - fixes issue #139  
\* The cost reduction provided per piece of wizard armour has been reduced to 15%, however there is now an additional 20% bonus for wearing a complete set, meaning that the cost reduction for a full set is still 80% as before  
\* When invisible, wizard armour is now ignored when calculating the mob detection penalty for wearing armour  
\* Wizard armour now doesn't render at all when invisible, rather than just using an invisible texture  
\* Siphon upgrades have been buffed to grant at least 5 mana per level for each kill (it was 3 before)  
\* All wands are now available in the creative inventory, and wizardry gear (wands, armour and artefacts) now has its own separate tab  
\* Spell books and scrolls now stack to 16 (the arcane workbench slots still only accept one spell book at a time, but you can now enchant a stack of 16 scrolls at once)  
\# Wands and conjured items can no longer be enchanted using an anvil  
  
#### Worldgen/loot:  
\+ Added obelisks  
\+ Added shrines  
\+ Added some of the new items to loot tables  
\+ Firebombs, poison bombs, smoke bombs, spark bombs and a selection of spell scrolls now have a chance to generate in jungle temple dispensers  
\+ Added the 'fancy' structure generation algorithm to determine whether there is space for the structure to spawn, meaning structures are very unlikely to spawn on cliffs, steep slopes, or other structures, and will clear any floating trees left behind after they generate - there is a config option to turn this off for potentially quicker worldgen  
\+ Added the option 'undiscovered_bias' to the random_spell loot function; this option allows a weighting towards undiscovered spells to be specified, with 0 being no weighting (as it was previously) and 1 producing guaranteed undiscovered spells  
\+ Added a config option to change the chance for a tower to contain an evil wizard and loot chest, see issue #133  
\+ Added a config option to add, change and remove structure file locations, allowing pack makers to add and remove structure variants from resource packs rather than being limited to just overriding the default ones  
\+ Added a config option to specify the loot injection locations, meaning you can now add wizardry's standard set of dungeon loot to any loot table from any mod  
\* All structures now use the structure file system, meaning you can spawn them yourself using structure blocks and change them using resource packs  
\* The tower rarity config option is now the 1/n chance per chunk that a wizard tower will generate, allowing for finer control over their rarity - multiply pre-4.2 values by 70 for an equivalent value in the new system  
\* Wizard tower materials have been tweaked a little: cobblestone and stone brick towers now have random mossy blocks and towers in mesas are now made of red sandstone  
\* Structures now ignore trees when finding a space to generate, meaning they should now spawn at the same rate in forests as everywhere else  
\* The spell books and scrolls generated in dungeon chests and wizard tower chests (as well as shrines and obelisks) now have an undiscovered bias of 0.3 by default, meaning 65% of generated spell books and scrolls will contain spells the player has not yet discovered  
\* Mob spell book drops are now defined in a loot table, and mobs can be blacklisted or whitelisted for this in the config  
\* Mobs no longer drop master spell books, apart from evil wizards spawned from structures  
\* All loot is now less common in dungeon chests, to account for the new structures  
\* Tomes of arcana are now much less common  
\* Various other loot rarity tweaks  
\# Eliminated most cascading worldgen lag (a small amount still remains; this is due to the size of the bigger stuctures)  
\# All structures now respect the generated structures world option  
\# The rewrite should fix issue #100  
\- Removed novice elemental wands from loot tables in favour of elemental crystals  
\- Removed the generateLoot config option in favour of finer control over loot injection locations, see above  
  
#### Spells:  
\+ Added 50 new spells!  
\+ Spells can now be cast by placing a spell scroll in a dispenser and powering the dispenser - some spells behave slightly differently to when they are cast by players, and a few spells such as transportation cannot be cast by dispensers  
\+ Continuous spells can now be cast using scrolls, and will last for a set duration of 6 seconds in survival mode. They also work in dispensers!  
\+ Continuous spells may now have cooldowns, though by default none of them do  
\+ Arcane jammer now prevents evokers from casting spells  
\+ Added a config option to prevent player block damage, this should stop griefing on servers - the one exception to this is the new Mine spell since that's all it does, but it should still respect block protection mods (if not, you'll have to disable the spell, sorry)  
\+ Added a pocket furnace item blacklist to the config  
\+ Added sword and bow item whitelists to the config  
\* Wizards (and other non-player spell casters) now obey range restrictions for all spells, so no more being electrocuted from 20 blocks away!  
\* Wizards now have the decency to tell you which spell you are buying before you buy it - however, it will only count as discovered after you buy it  
\* All construct spells including sigils now have anti-overlap, meaning that multiple constructs of the same type cannot be placed such that they intersect - this removes an exploit where constructs (especially sigils) could be stacked up at a single location to deal massive amounts of damage  
\* All summoned creatures now increase their attack damage based on the potency the spell was cast with  
\* Summoned creatures can now always attack non-players that are attacking their caster (noticeable with, for example, angry wolves)  
\* Some spells such as blizzard no longer require the caster to be aiming at the ground in order to cast them, they can now be cast in mid-air just like black hole, fixing issue #132  
\* Summoning a spirit horse or wolf when the player already has one now causes the old one to disappear, instead of not allowing the new one to be summoned - this fixes issue #74  
\* Wizards can now cast even more of the spells  
\* Some projectile spells have had their base ranges reduced to make range upgrades more useful  
\* Forcefield's repulsion code has been completely rewritten; it is now impossible for anything to get through that isn't supposed to - this fixes issue #117  
\* Forcefield now supports blast modifiers, which increase the forcefield size  
\* Forcefield now protects against explosions - you can now stand inside your forcefield and watch creepers blow up in your face without taking a single bit of damage!  
\* Blocks can now be placed and broken and entities can now be interacted with inside forcefields; however, you cannot interact with anything outside a forcefield from inside it, and vice versa  
\* Sigil spells are now affected by potency modifiers  
\* Blast upgrades now affect various spells that weren't affected by them before  
\* Firestorm has been renamed to fire breath, and a new firestorm spell more befitting of the name has been added (any references to the old firestorm spell in existing worlds will change to fire breath)  
\* Fireball and greater fireball have had their fireballs replaced with custom ones because the vanilla ones are useless - you can optionally replace all fireballs in the game with these if you prefer them  
\* Phase step now allows teleportation through floors and ceilings, and also works as a short-distance teleport that does not require the caster to be looking at a block, unlike blink  
\* Summoned silverfish now have a limit to the number of 'generations' that can happen, preventing them from multiplying indefinitely - this fixes issue #143  
\* Flame ray and fire breath now support duration modifiers, in the same way as ignite  
\* Life drain's healing power has been nerfed slightly, but now scales with potency modifiers  
\* Wall of frost now freezes mobs solid if they are caught in its blast  
\* Wall of frost now uses frosted ice instead of ice statue blocks, eliminating the large number of tile entities, resulting in improved performance  
\* Wall of frost now supports duration modifiers, which will increase the time before the ice breaks  
\* Lightning hammer now deals damage to entities on a direct hit  
\* Phoenixes now spawn in mid-air instead of on the ground  
\* Banish's teleportation radius is now affected by blast modifiers instead of range modifiers. The range of the actual spell shot is still affected by range modifiers.  
\* Light is now affected by range modifiers  
\* Greater fireball and growth aura are now affected by blast modifiers  
\* Glide and flight are now affected by potency modifiers, which in both cases increase flight speed  
\* Intimidate is now affected by potency modifiers, which increase the distance mobs will run away  
\* Whirlwind is now affected by potency modifiers, which increase the repulsion speed  
\* Ice spikes can now be summoned on walls and ceilings  
\* Ice charge now spawns ice shards with greater velocity  
\* Diamondflesh now gives resistance IV instead of resistance V  
\* The code now allows wizards to cast most master spells, but only wizards spawned from shrines will actually do so naturally - but you can make any wizard cast master spells by right-clicking them with a master spell book in creative mode (at your own risk!)  
\* All spells now respect the mobGriefing gamerule  
\# All spells no longer hit entities that are in the process of dying  
\# Transience now prevents all damage except being out of the world, as was originally intended - you can now jump off a cliff and land unharmed under its effects  
\# Spirit wolves now spawn with a full 40 health instead of 8 (the value for untamed wolves, which was incorrectly used in previous versions)  
\# Decoy now has a greater chance to trick mobs the higher the potency, as it should (it was less before... my bad!)  
\# Pocket furnace no longer smelts weapons, tools or armour, fixing issue #115  
\# Fixed issue #30, where Potion Core (or any other mod that modifies vanilla invulnerability timers) would cause continuous spells to deal damage in very quick succession in certain cases - the config-based workaround should no longer be necessary  
\# Fixed issue #69, where discover spells would (sometimes?) reset client-side on player death  
\# Fixed issue #137, where summoned iron golems would behave like village ones instead of player-built ones  
\# Fixed issue #150, where lightning hammer caused a crash with LordCraft installed  
  
#### The Wizard's Handbook:  
\+ Added a movable bookmark to The Wizard's Handbook  
\+ Added more images to The Wizard's Handbook  
\+ The Wizard's Handbook now adds pages as and when you discover the relevant item, location or thing, so that new players don't have a huge wall of text to start off with (and to encourage you people to actually read the thing, goddamnit!)  
\+ Added a (client-side) config option to switch this behaviour off for the wizardry veterans out there  
\+ Added a config option controlling whether wizardry's books pause the game when opened in singleplayer, fixing issue #126  
\* The Wizard's Handbook is now defined in a JSON file, allowing for much more flexibility in its structure and formatting - it now supports:  
	> Inline and animated crafting recipes, which are loaded dynamically from defined recipe JSON files  
	> Inline images with captions  
	> Customisable text colours  
	> Inline hyperlinks to sections of the book and external websites  
	> Customisable contents lists, complete with automatically-generated hyperlinks  
	> Advancement triggers for book sections  
\* Updated and reorganised the information in The Wizard's Handbook  
\# As a result of the changes, text now wraps properly regardless of the font, language or book contents, fixing issue #58  
\# Fixed issue #145, where the handbook background was coloured if the GL colour was not set to white by whatever was drawn before it  
  
#### Mod Integration / Compatibility:  
\+ Added Baubles integration for the new artefacts - if Baubles is installed, they are active when worn in the appropriate Baubles slot, otherwise they are active when on the hotbar (and are limited to the same number as the Baubles slots would allow)  
\+ Added JEI integration for arcane workbench 'recipes' - JEI will now show you how to charge items, bind spells, upgrade wands and enchant scrolls  
\+ Added Antique Atlas integration for wizard towers and the two new structures, shrines and obelisks - each has its own dedicated marker type, and by default global markers will be added as the structures are generated  
\+ Added mod integration options to the config file  
\# Added the damage safety checker, fixing issues #72 and #89 - this system allows wizardry to detect an imminent crash before it happens and divert the damage to prevent it  
\# Fixed issue #125, a crash with the Applied Energistics 2 terminal  
\# Fixed issues #66 and #153, an exploit where wands and armour could be refilled with mana using item repair methods from other mods  
  
#### Technical/Commands:  
\+ Added support for positional spell casting using commands, meaning players and command blocks can cast spells at any location as if there was a dispenser there  
\+ Spells now each have their own JSON file located under assets/ebwizardry/spells, which defines the spell's base attributes and where it can appear and be used - this means they can now be tweaked using resource packs  
	> On a server, you'll need to modify the jar in the same way you would for recipes or advancements - but 	the changes will be sent to clients automatically  
\+ Added proper advancement triggers, meaning you can make custom advancements for certain actions in wizardry including spell casting, spell discovery and arcane workbench use  
\* Continuous spells cast via commands now last for a certain duration which may be specified in the command, or left as the default 5 seconds, similar to the /effect command  
\* Assigning spells to wizards via right-clicking in creative now displays a chat readout  
\* Increased the config limit for player/NPC damage scaling from 20 to 255  
\* Wizardry's commands now respect the sendCommandFeedback gamerule (with the exception of /allies, since that's all it does)  
\# Eliminated several ArrayIndexOutOfBoundsExceptions caused by wand NBT in commands  
  
#### Miscellaneous:  
\+ Ice wraiths now occasionally spawn at night in tundra, ice spikes and ice mountains biomes  
\+ Lightning wraiths now occasionally spawn in any biome during thunderstorms  
\+ Added config options to control mob spawning  
\+ Added a config option for changing the items required to buy items from wizards, useful if, for example, your modpack has a currency item such as coins  
\+ Added Korean translations, thanks to rewi_wire and shejery  
\+ Added French translations, thanks to Hahdrim  
\+ Added Brazilian Portugese translations, thanks to lorrampi  
\* The ally designation system now takes tamed creatures into account, including those from other mods (assuming they use the vanilla system): creatures tamed by you or an ally will not be targeted by your spells, even when you are not logged in  
\* Due to internal changes (namely that they now implement IEntityOwnable), other mods should now recognise that your summoned creatures and constructs belong to you - actual effects will vary between mods  
\* The friendly fire config option now has four settings: All (allow all friendly fire), Only players (prevent friendly fire on creatures summoned/tamed by you or an ally, but allow it on allied players), Only minions/pets (prevent friendly fire on players, but allow it on creatures summoned/tamed by you or an ally), and None (prevent all friendly fire)  
\* The minion revenge targeting config option now works on everything the ADS works on, so your pets, your friends and their pets will now be completely safe if it is disabled  
\* Wizard trades are a bit less expensive now, and diamonds have been removed from the potential items bought  
\* Reorganised wizardry's advancements, added some new ones and removed some old ones  
\* Updated Russian translations, thanks to kellixon  
\* Reorganised and improved the config file and GUI  
\* Polar bears are now immune to frost damage  
\# Binding the next/previous spell keys to mouse buttons finally works properly - gaming mouse users, rejoice!  
\# Fixed issue #116, where the server would freeze when it received an invalid arcane workbench packet (this now prints a warning instead)  
\# Squashed a load of other little bugs  
  
#### Internal/Development:  
\+ Improved API support for adding new elements  
\+ Improved API support for adding new tiers, you'll probably need to do some of the legwork yourself though  
\+ Added the ISpellCastingItem interface, allowing custom spellcasting items to be defined without needing to extend ItemWand  
\+ Added the IManaStoringItem interface, allowing custom implementations of mana storage (such as NBT)  
\+ Added a spell data system to WizardData which allows data of any type to be stored in it. This is done by specifying a key which is an IVariable<T>, where T is the type of data you want to store. The system also allows automatic saving to NBT through supplied converter functions, see IStoredVariable. There are a number of static methods for generating keys for primitives and other common data types in StoredVariable. The system is completely optional, so you may well not even need to use it.  
\* Reorganised some of the packages  
\* Moved a lot of methods around in an effort to improve code navigability and separation of concerns. There shouldn't be too many external changes, but some helper methods may be somewhere different to before (notably: raytracing, NBT helpers and the ally designation system).  
\* Significantly refactored the structure and hierarchy of the spell classes, introducing a set of standardised superclasses for similar types of spells. These changes should be backwards-compatible except for a few minor tweaks/name changes, though these are insignificant compared to the changes required as part of the spell JSON system - HOWEVER, it is highly recommended that spell classes are converted over to extend the appropriate superclass wherever possible. This will likely result in deletion of a lot of copied code.  
\* Introduced spell properties, which are the code representation of the base_properties object in the new spell JSON files. You'll need to make JSON files for all your spells and plug in their tier, element, cost, etc. (I have a code snippet that generates the standard stuff for you, give me a shout). The more involved part is taking the hardcoded constants ('properties') out of your spells and moving them over to the JSON file so that users can change them. Your spells will still work without doing this, so which things you choose to give users control over is up to you. See my spell classes for examples.  
\* Decoupled spell metadata from the numbers used in packets. This fixes a problem where removing a spell from a world (perhaps by uninstalling a spell pack) would result in the game crashing when trying to sync spell glyph data. Spells now have a network ID which must be used for packets, see Spell#networkID() and Spell#byNetworkID(int). For clarity, the Spell#id() and Spell#get(int) methods have been renamed to metadata() and byMetadata() respectively. N.B. Spell metadata is likely to be phased out in future updates in preparation for 1.13 and the flattening, network IDs are the first step towards that.  
\* Rewrote the particle system, pretty much from the ground up. Wizardry particles must now be spawned using the particle builder - see electroblob.wizardry.util.ParticleBuilder for more details. It's pretty self-explanatory though, this isn't a difficult change to make. You can even add your own particles to this system!  
\* Improvements and changes to spell casting events and modifiers to accommodate dispenser casting, including proper support for cooldown modifiers and integration of cost into the modifiers system - fixing issue #140  
\* Allies are now stored as UUIDs, as are owners of summoned creatures and constructs, which now also implement IEntityOwnable. The ally system has been tweaked accordingly and there are a few extra helper methods for it, see electroblob.wizardry.util.AllyDesignationSystem for details. This change fixes issue #113 and possibly #21.  

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