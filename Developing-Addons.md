> These tutorials are for wizardry 4.2.x. For older 1.12 versions (and 1.10/1.11), check the page history. For 1.7.10 versions of wizardry, see the [legacy spell packs tutorial](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/pages/making-spell-packs).

> 本教程用于wizardry 4.2.x. 对于较旧的 1.12 （和 1.10/1.11）版本请查看历史页面。1.7.10 版本的教程请见[legacy spell packs tutorial](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/pages/making-spell-packs).

These pages explain how to program addon mods for _Electroblob's Wizardry_, particularly **spell packs**. This page covers setting up your workspace ready to work with wizardry's code. See the links to other pages for how to add spells and other content.


本页面介绍如何添加 _Electroblob's Wizardry_ 的附属 mod, 尤其是 **spell packs**。本页面将介绍如何设置你的 workspace ready to work with wizardry's code.**看不懂:(** 关于如何添加法术和其他内容，请参阅其他页面。


## Pages in this category
**看不懂:(** 

[[Adding Spells]]  
[[Adding Wand Upgrades]]  
[[Adding Entities]]  
[[Miscellaneous Features]]  
[[Compiling and Publishing]]

---
# Getting Started
# 开始

## Prerequisites
## 准备

- A reasonable knowledge of the basics of modding with _Minecraft Forge_: an understanding of simple Java, how to make blocks, items and such like, and familiarity with the registry and event handling systems. That said, I have made every effort to explain things as clearly as I can along the way.

- 了解一些关于 _Minecraft Forge_ 的基础知识: 一定的 Java 基础，例如如何添加方块、物品, and familiarity with the registry and event handling systems. 我已经尽量清楚地说明了。

- A modding environment set up. I used eclipse for several years and recently switched to IntelliJ IDEA, but you can use any IDE - I won't be referring to anything specific to either of those IDEs. Make sure you have the correct version of Minecraft Forge for the version of wizardry you intend to use. Usually this will be the latest version of Forge for the version of Minecraft you are using.

- 设置 mod 环境。我用了好几年的 eclipse ，最近换到了 IntelliJ IDEA，你也可以用其他 IDE ——我不会提及有关这两个 IDE 的任何特性。请确保你使用的是适用于 wizardry 的 Minecraft Forge 版本。通常这是你使用的 Minecraft 版本的最新 Forge 版本。

- A mod set up ready to add spells to (main mod class and proxies, plus a lang file).

- 一些关于添加法术的准备（主 mod 类和 proxies ，加上 lang 文件）。

## Setting up your workspace

First you'll need to download the version of wizardry you wish to make a spell pack for, which can be found on curseforge ([here's the full list of downloads](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/files)). Make sure you get the right **mod** version as well as the right Minecraft version. I recommend using the latest version of wizardry for the Minecraft version you want, as it will have the most API features and make your life easier.

首先你需要下载一个 wizardry ，你可以在 curseforge 上面找到 ([这里是下载列表](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/files)). 你需要确保自己下载的 **mod** 版本和 Minecraft 相同。我建议你使用最新的 wizardry 版本，因为这个版本的 API 支持最完善，可以方便修改。

> Minor updates to wizardry shouldn't break the API, meaning that an addon written for 4.1.0 will work with 4.1.1, 4.1.2, etc. but not 4.2.x. However, the reverse is not necessarily true: if you use a new feature that was added in a minor patch, your addon won't work in older versions.


> 较小的更新不会对 API 进行改动，比如 4.1.0 版本的拓展可以给 4.1.1 和 4.1.2 等版本使用，但是不能用于 4.2.x 。但是情况不一定是这样：如果使用了较小更新添加的新功能，则该拓展不能给旧版使用。

Next, make a folder called `libs` inside your project folder (the one with build.gradle in) and put the wizardry jar in there. Now if you launch Minecraft in your development environment, wizardry should be fully working in-game.

接下来，在你的项目里文件夹（里面有 build.gradle ）新建一个叫做 `libs` 的文件夹，将 wizardry 的 jar 文件放入。现在在开发环境下启动 Minecraft ，你应该可以看到 wizardry 正在游戏中运行。

However, if you look inside the wizardry jar and open up any of the classes you'll notice they're completely unreadable. To get a readable version, you'll need to attach the source code. The source code for all versions can be downloaded as a `.zip` from GitHub as follows:

单数，如果你打开 wizardry 的 jar 文件，你会发现里面的所有类都是不可读的。要获取可阅读的版本，你需要附加源代码。你可以在可以在 Github 下下载到 .zip 格式的源代码：

1. Go to the [releases page](https://github.com/Electroblob77/Wizardry/releases) for wizardry's GitHub repository (you can also access this from the main page by clicking releases in the menu bar just above the file tree)
2. Find the release you're developing for in the list
3. Click the little `.zip` icon below the release version number to download a zip file of the entire repository at that release 

1. 打开 wizardry 的 GitHub repository [releases page](https://github.com/Electroblob77/Wizardry/releases) （你也可以通过点击主页 file tree 上方的菜单栏中访问）。
2. 找到你正在开发的发行版。
3. 点击发行版本下方的 `.zip` 图标下载这个发行版的完整 repository 。

Once you've downloaded the source code, rename the file extension from `.zip` to `.jar` and move the file somewhere sensible (don't put it in `libs` or Forge will think you have duplicate mods). Now use your IDE to attach the source jar to the compiled jar - again, if you don't know how, you'll need to look up how to do this for the IDE you're using.

当你下载源代码之后，将这个文件的后缀名从 `.zip` 改为 `.jar` ，并将此文件移动到你喜欢的地方存好（不要放进 `libs` 里面，不然 Forge 会认为你安装了重复的 mod ）。现在再次用你的 IDE 将 jar 源代码添加到编译好的 jar 文件中，如果你不知道怎么做，你可以去查看你自己的 IDE 的有关教程。

> If (unlike me) you know what you're doing with Gradle and Maven, you can use the CurseForge Maven as an alternative to storing wizardry jars locally. See the [curse knowledge base](https://authors.curseforge.com/knowledge-base/projects/529-api) for more details.

> 如果你知道怎么使用 Gradle 和 Maven （不像我）。你可以用 CurseForge Maven 替代本地的 wizardry jars 。你可以在 [curse knowledge base](https://authors.curseforge.com/knowledge-base/projects/529-api) 里面看到更多详细信息。

## Specifying wizardry as a dependency

Next you'll need to specify Wizardry as a dependency for your mod, which is done in your `@Mod` annotation using the following syntax:

接下来，你需要将 Wizardry 设置为你的 mod 的前置，下面的是完成后的 `@Mod` 中的 annotation 语法：

`dependencies="required-after:ebwizardry"`

> If you're using a Minecraft version prior to 1.12, replace `ebwizardry` with `wizardry`.
> 如果你想要使用 1.12 以前的 wizardry 版本，请将 `ebwizardry`换成 `wizardry` 。

这将执行两项操作:
1. It ensures Forge will always load your addon after wizardry. This is important for registries (and a few other things) to work correctly.
2. If a user tries to run the game with your addon installed, but without wizardry, Forge will display a message telling them that wizardry must be installed.

1. 确保 Forge 始终在加载 wizardry 后加载你的附属 mod 。这对 registries （和一些其他的事情）正常运行非常重要。
2. 如果用户没有安装 wizardry ，在其尝试在安装你的附属 mod 后打开游戏时，Forge 会告诉用户必须要先安装 wizardry 。

You can also specify a version or range of versions your addon is for, by appending an `@` followed by the [maven version range syntax](https://maven.apache.org/enforcer/enforcer-rules/versionRanges.html). For example, the following syntax only allows an addon to run with 4.2.x versions of wizardry:

你还可以按照 [maven version range syntax](https://maven.apache.org/enforcer/enforcer-rules/versionRanges.html) 指定你的附属 mod 的适用版本。比如，要让附属只能和 wizardry 4.2.x 版本一起运行：

`dependencies="required-after:ebwizardry@[4.2.0,4.3)"`

> The page on [structuring your mod](https://mcforge.readthedocs.io/en/latest/gettingstarted/structuring/) in the Forge documentation contains lots of useful information about the `@Mod` annotation and the `mcmod.info` file.

> 在 Forge 文档中的 [structuring your mod](https://mcforge.readthedocs.io/en/latest/gettingstarted/structuring/) 页面内含有关于 `@Mod` 注释和 `mcmod.info` 文件的详细信息。

---

Now you're ready to start adding content to your addon mod! Check out the page on [[adding spells]] for a tutorial on how to add spells. Alternatively, take a look at the other tutorial pages on this wiki, or have a read of wizardry's code - I endeavour to write useful Javadoc comments for all of the important classes and methods; you can learn a lot just by reading through the code itself.

现在，你已经准备去制作你的附属 mod 了吗？点击 [[adding spells]] 页面去了解如何添加法术。你还可以查看这个 wiki 的其他教程页面，或者直接阅读 wizardry 的代码——我为 Javadoc 中的重要类和 method 添加了很多注释，你可以通过阅读代码了解到更多信息。

If you have a question about writing an addon for wizardry, come and poke me on [Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) or the [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) and I will answer it as well as I can! Consider also setting up a GitHub repository for your addon mod, it makes it a lot easier for me to help you.

如果你对编写附属有什么问题，可以来 [Discord](https://discord.gg/MTmMzMv)，[CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) 或者 [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) 。我会尽量解答的！我还考虑为你的附属 mod 去开一个 GitHub repository，这样能更好地帮助你们。
