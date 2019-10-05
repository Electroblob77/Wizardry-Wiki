This page contains a collection of code snippets for automatically generating certain files which are too numerous to write manually. In each case, they work best when pasted into the `init()` method in your main mod file. To use them, create the folder `generated` inside the `run` folder in your project directory, then launch the game as far as the main menu and the files will be generated inside the folder you just created.

## Spell properties JSON file generator

This snippet will generate [[spell properties]] files for every registered spell that isn't part of the base mod. Note that this only generates an empty `"base_properties"` object; you will need to add any spell-specific properties yourself.

```java
Gson gson = new GsonBuilder().setPrettyPrinting().create();

for(Spell spell : Spell.getSpells(Spell.allSpells)){

        if(spell.getRegistryName().getNamespace().equals(Wizardry.MODID)) continue;

	try {

		FileWriter writer = new FileWriter("generated\\" + spell.getRegistryName().getPath() + ".json");

		JsonObject json = new JsonObject();

		JsonObject enabled = new JsonObject();

		enabled.addProperty("books", true);
		enabled.addProperty("scrolls", true);
		enabled.addProperty("wands", true);
		enabled.addProperty("npcs", true);
		enabled.addProperty("dispensers", true);
		enabled.addProperty("commands", true);
		enabled.addProperty("treasure", true);
		enabled.addProperty("trades", true);
		enabled.addProperty("looting", true);

		json.add("enabled", enabled);

		json.addProperty("tier", spell.getTier().getUnlocalisedName());
		json.addProperty("element", spell.getElement().getName());
		json.addProperty("type", spell.getType().getUnlocalisedName());

		json.addProperty("cost", spell.getCost());
		json.addProperty("chargeup", 0);
		json.addProperty("cooldown", spell.getCooldown());

		json.add("base_properties", new JsonObject());

		gson.toJson(json, writer);

		writer.close();

	}catch(IOException e){
		e.printStackTrace();
	}
}
```

## Spell wiki page generator

Yes, I even made a generator for that!

```java
int i = 1;
String firstAppeared = "1.0";

for(Spell spell : Spell.getSpells(Spell.allSpells)){

	try{

		FileWriter writer = new FileWriter("generated\\" + spell.getDisplayName().replace(' ', '-') + ".md");

		writer.write("| " + spell.getDisplayName() + " |![](https://github.com/Electroblob77/Wizardry/blob/1.12.2/src/main/resources/assets/ebwizardry/textures/spells/" + spell.getUnlocalisedName() + ".png)|\n" +
				"|---|---|\n" +
				"| Tier | " + spell.getTier().getDisplayName() + " |\n" +
				"| Element | " + spell.getElement().getDisplayName() + " |\n" +
				"| Type | " + spell.getType().getDisplayName() + " |\n" +
				"| Mana Cost | " + spell.getCost() + " |\n" +
				"| Continuous | " + (spell.isContinuous ? "Yes" : "No") + " |\n" +
				"| Cast by wizards | " + (spell.canBeCastByNPCs() ? "Yes" : "No") + " |\n" +
				"| Cast by dispensers | " + (spell.canBeCastByDispensers() ? "Yes" : "No") + " |\n" +
				"| ID | `" + spell.getRegistryName() + "` |\n" +
				"| Metadata | " + i++ + " |\n" +
				"| First appeared in | Wizardry " + firstAppeared + " |\n" +
				"## Description\n" +
				"_" + spell.getDescription() + "_");

		writer.close();

	}catch(IOException e){
		e.printStackTrace();
	}
}
```