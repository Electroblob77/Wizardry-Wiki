_Since: Wizardry 1.10.2 Beta 1_

Wizardry has two custom loot functions: random_spell and wizard_spell. This page explains how to use them in your own loot table customisations.

Wizardry 有两种自定义战利品函数：random_spell 和 wizard_spell 。本页面将介绍如何在自己的战利品表内使用它们。

It is assumed that readers of this page are familiar with the format of Minecraft loot tables. You can read more about them [here](https://minecraft.gamepedia.com/Loot_table).

本教程先假设玩家熟悉 Minecraft 战利品表的格式。你可以先通过[这里](https://minecraft-zh.gamepedia.com/战利品表)更多信息。（译者注：原文中链接为英文 Wiki 。这里直接替换为中文 Minecraft Wiki 的链接了。如果访问速度过慢可以访问[镜像链接](https://wiki.biligame.com/mc/战利品表)

All names are written in lowercase with underscores _ between words.

所有名称都为小写，单词间的空格用下划线（“_”）代替。

## random_spell

Loot function that allows spell books and scrolls to select a random spell based on the standard weighting. Automatically discounts continuous spells when the item in question is a scroll. Can be used as-is with no parameters, but several optional parameters are available for those wishing to customise further:

战利品函数允许将法术书和卷轴的法术根据标准的权重进行选择。

* **spells**: A list of spells to choose from. Defaults to all enabled spells.
* **ignore_weighting**: true to ignore the standard weighting and just pick a completely random spell. Defaults to false.
* **tiers**: A list of tiers to choose from. Defaults to all tiers. Valid tiers are: basic, apprentice, advanced and master (novice is called basic in the code, they're the same thing).
* **elements**: A list of elements to choose from. Defaults to all elements. Valid elements are: fire, ice, lightning, necromancy, earth, sorcery and healing.
* **undiscovered_bias**: A number between 0 and 1 which specifies a weighting to apply towards spells that have not been discovered yet. Defaults to 0. A value of 0 results in no weighting (all applicable spells are equally likely), and a value of 1 results in a guaranteed undiscovered spell. This parameter only has an effect when a player has opened a loot container or killed a mob.

If an add-on mod adds new tiers or elements, these will also work. Spells from other mods are automatically included as well.

For reference, the standard weighting is as follows: Basic (Novice) 60%, Apprentice 25%, Advanced 10%, Master 5%. If the selection is restricted to specific tiers, their relative weightings are used; for example, if only apprentice and master tiers are included the weighting becomes: Apprentice 83.3%, Master 16.7%.

Example Json syntax for a single entry in a loot pool:
```
{
    "type": "item",
    "name": "wizardry:spell_book",
    "weight": 20,
    "functions": [
        {
            "function": "wizardry:random_spell",
            "tiers": [
                "advanced",
                "master"
            ],
            "elements": [
                "fire",
                "ice",
                "sorcery"
            ]
        }
    ]
}
```
This example entry will generate a spell book with a random spell each time, chosen using the standard weighting from only the advanced and master tiers and only the elements fire, ice and sorcery.

## wizard_spell

Loot function that allows spell books to select a random spell from the spells used by the mob that dropped them. This is intended for use in mob loot tables and will have no effect if used in other types of loot table. The mob whose loot table contains this function must be a mob that can cast spells, or the loot function will not work. This loot function has no additional parameters.

Example Json syntax for a single entry in a loot pool:
```
{
    "type": "item",
    "name": "wizardry:spell_book",
    "weight": 1,
    "functions": [
         {
             "function": "wizardry:wizard_spell"
         }
    ]
}
```
This example was taken from the loot table for evil wizards and will generate a random spell book with one of the spells the wizard was using. Note that the generated spell book will never be for the magic missile spell.
