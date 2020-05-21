本页面介绍如何编译与发布你的附属 mod 。

## 准备
- 一个待编译的法术包或附属 mod 。
- 了解如何使用 gradle 去编译 mod。
- 一个 `build.gradle` 文件。

## 编译法术包

你可以像编译 mod 一样。通过在命令行中运行 `gradlew.bat build` 编译你的法术包。如果你把 deobfuscated jar 放入 `ibs` 文件夹，那么它应该能正常运行。如果不是，就会编译错误并无法构建。将以下代码添加到 `build.gradle` 文件中以修复该问题：
```
dependencies {
	compile files (
		"[filepath]"
	)
}
```
其中的 `[filepath]` 是 Wizardry 的 _deobfuscated_ 版本相对于你的项目文件夹的文件路径。

你可以将编译好的法术包像其他 mod 一样直接放进安装了 Forge 的游戏来测试它。确保你安装了 wizardry ！

## 发布法术包
那么，你已经做好了一个法术包，现在你将要把它发布到社区。牛逼！
我并未限制你的附属 mod 的发布平台，你只需要满足以下条件即可发布：


- 将我，Electroblob，**标记**为 _Electroblob's Wizardry_ 的作者，并且**给出**原 mod 的下载链接（该 mod 的 Minecraft Fourm 的主题或者 mods.curse.com 页面）。 毕竟没有人可以在不下载 wizardry 的情况下玩你的附属 mod ！
- 你不能将附属 mod 用于商用。**这包括 AdFly** 和其他网址缩短服务。**唯一**的例外是 **Curse rewards program** 。当然你**可以**通过附属 mod 的视频或直播盈利。(_我制定这个协议的原因是：我没有在 wizedry 上使用 网址缩短服务，因为我不想让用户不得不使用这些进行下载，我也不想让附属 mod 这么做。如果你想要获得许可，请不要犹豫，可以问我。_)

> 我推荐使用 CurseForge 去发布你的附属 mod ，因为它允许你把它列为 Wizardry 的附属。

我也想要你在发布附属 mod 之后告知我，你可以通过[Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry)或者 [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) 这些渠道。这不是必须的，但是如果你这么做了，我会在 Wizardry 的描述中为你的附属添加一个链接！

在 wizardry 的 Discord 中有一个 **#spell-packs** 频道，你可以将你的附属 mod 发布到此处，所以一定要来看看！
