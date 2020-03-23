
> 本教程适用于wizardry 4.2.x。如果要找的教程关于1.12环境下旧版的模组，或是1.11/1.10版本的模组，请查看历史页面。1.7.10 版本的教程请见[历史版本法术包教程](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/pages/making-spell-packs)。  

本页面将介绍如何开发 _巫术学_ 的附属 mod，尤其是如何开发 **法术包组件**。本页面将介绍如何配置好巫术学开发工作环境。 关于如何添加法术和其他内容，请参阅其他页面。  

## 相关页面  

[[编写你自己的法术]]  
[[Adding Wand Upgrades]]  
[[添加生物]]  
[[Miscellaneous Features]]  
[[编译与发布附属mod]]

---
# 开始  

## 准备  

- 了解一些关于 _Minecraft Forge_ 的基础知识：有一定的 Java 基础，并且了解如何添加方块、物品，熟悉Java中的registries机制和事件处理系统。尽管如此，我还是会尽可能将这一部分解释清楚。      

- 配置 mod 环境。我用了好几年的 eclipse ，最近换成了 IntelliJ IDEA，你也可以用其他 IDE ——我将提到的东西并不是这两个IDE的特性。请确保你使用的是适用于Wizardry的 Minecraft Forge 版本，通常应该使用对应当前 Minecraft 版本的最新 Forge 版本。    

- 一些关于添加法术的准备（mod 主类和 proxies ，还有 lang 文件）。    

## 配置工作环境  

首先你需要下载一个Wizardry mod，你可以在 curseforge 上面找到 ([这里是下载列表](https://www.curseforge.com/minecraft/mc-mods/electroblobs-wizardry/files)). 你需要确保自己下载的 **mod** 版本适用于你选择的 Minecraft 版本。我建议你使用所选版本最新的Wizardry mod，因为新版本的 API 最完善，可以使你的工作更简单。  

> 较小的更新不会对Wizardry的API产生改变，所以说，你为4.1.0版本写的附属Mod也能在4.1.1和4.2.2中正常运行，但是在4.2.0中不行，以此类推。然而，情况有时候会有所不同：如果你在附属中使用了高版本加入的特性，即使API没有重写，它也不可能在旧版本中运行。  

接下来，在你的项目文件夹（里面有 build.gradle ）中新建一个叫做 `libs` 的文件夹，将 wizardry 的 jar 文件放入。此时，如果在开发环境下启动 Minecraft ，你应该可以发现Wizardry在游戏中正常加载。  

但是，如果你以解压的方式打开Wizardry的 jar 文件，就会发现里面的所有类都无法阅读。如果要阅读它们，你还需要获取源代码。你可以通过这种方式在 Github 上下载到 .zip 格式的源代码：  

1. 打开Wizardry 在 GitHub repository 的[releases页面](https://github.com/Electroblob77/Wizardry/releases) （你也可以通过点击主页 file tree 上方的菜单栏中访问）。
2. 找到你准备开发附属的发行版。
3. 点击发行版本下方的 `.zip` 图标下载这个发行版的完整代码。

当你下载好源代码之后，将这个文件的后缀名从 `.zip` 改为 `.jar` ，并将此文件移动到随便什么地方保存（但是不要放进 `libs` 里面，不然 Forge 会认为你安装了重复的 mod ）。现在再用你的 IDE 将 jar 源代码编译好，如果你不知道怎么做，你可以去查看你使用的 IDE 的有关教程。

> If (unlike me) you know what you're doing with Gradle and Maven, you can use the CurseForge Maven as an alternative to storing wizardry jars locally. See the [curse knowledge base](https://authors.curseforge.com/knowledge-base/projects/529-api) for more details.

> 如果你知道怎么使用 Gradle 和 Maven （不像我），你可以用 CurseForge Maven 来替代本地的jar文件 。你可以在 [curse知识库](https://authors.curseforge.com/knowledge-base/projects/529-api) 里面看到更多详细信息。

## 指定Wizardry Mod为支持库

接下来，你需要将 Wizardry 设置为你的 mod 的前置，请使用以下的语法在 `@Mod`的 annotation 中写入内容：  

`dependencies="required-after:ebwizardry"`  

> 如果你想要使用的mod是用于 1.12之前的Minecraft版本的 ，请将 `ebwizardry`换成 `wizardry` 。  

这句话有两个作用:

1. 确保 Forge 在加载 wizardry 后加载再你的附属 mod 。这对 registries （还有一些其他的东西）正常运行非常重要。  
2. 如果用户没有安装 wizardry却安装了你的附属 ，在打开游戏时，Forge 会告诉用户必须要先安装 wizardry 。  

你还可以按照 [maven的版本范围语法](https://maven.apache.org/enforcer/enforcer-rules/versionRanges.html) 指定你的附属 mod 的适用版本。比如，要让附属只能和 wizardry 4.2.x 版本一起运行，就这么写：  

`dependencies="required-after:ebwizardry@[4.2.0,4.3)"`

> 在 Forge 文档的 [让你的mod结构化](https://mcforge.readthedocs.io/en/latest/gettingstarted/structuring/) 页面中有关于 `@Mod` 注释和 `mcmod.info` 文件的详细信息。  

---

现在，你已经准备好制作你自己的附属 mod 了吗？点击 [[adding spells]] 页面去了解如何添加法术。你还可以查看这个 wiki 的其他教程页面，或者直接阅读 wizardry 的代码——我已经尽可能为那些重要的和方法添加了注释，你可以通过阅读代码了解到更多信息。  


如果你对编写附属有什么问题，可以来 [Discord](https://discord.gg/MTmMzMv)，[CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) 或者 [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) 找我。我会尽量解答的！你可以给你的附属建立一个 GitHub repository，这样我能更好地帮助你们。
