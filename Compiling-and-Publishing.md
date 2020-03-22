This page explains how to compile and publish a spell pack or other addon mod.

本页面介绍如何编译与发布你的附属 mod 。

## Prerequisites
## 准备
- A spell pack or addon mod ready to compile.
- 一个待编译的法术包或附属 mod 。
- Knowledge of how to compile a mod using gradle.
- 了解如何使用 gradle 去编译 mod。
- A `build.gradle` file.
- 一个 `build.gradle` 文件。

## Compiling a spell pack
## 编译法术包

You can compile your spell pack in the same way as any other mod, by running `gradlew.bat build` in the command window. If you put the deobfuscated jar in the `libs` folder, this should all work just fine. However, if not, the build will fail with compile errors. To fix this, add the following lines to your `build.gradle` file:

你可以像编译 mod 一样。通过在命令行中运行 `gradlew.bat build` 编译你的法术包。如果你把 deobfuscated jar 放入 `ibs` 文件夹，那么它应该能正常运行。如果不是，就会编译错误并无法构建。将以下 lines  **应该是“行”但是我不敢确定**添加到 `build.gradle` 文件中以修复该问题：
```
dependencies {
	compile files (
		"[filepath]"
	)
}
```
where `[filepath]` is the file path of the _deobfuscated_ version of Wizardry, relative to your project folder.
其中的 `[filepath]` 是 Wizardry 的 _deobfuscated_ 版本相对于你的项目文件夹的文件路径。

You can test out your compiled spell pack by dropping it into a Forge installation the same way you would install any other mod. Be sure to have wizardry installed as well!

你可以将编译好的法术包像其他 mod 一样直接放进安装了 Forge 的游戏**（这里Forge installation我理解成这样了不知道对不对）**来测试它。确保你安装了 wizadry ！

## Publishing a spell pack
## 发布法术包

So, you've made a spell pack, and now you want to release it for the community to enjoy. Hooray!

那么，你已经做好了一个法术包，现在你将要把它发布到社区。万岁！

I do not place any restrictions on how or where you distribute your addon mod, provided the following conditions are met:

我并未限制你的附属 mod 的发布平台，你只需要满足以下条件即可发布：

- You **credit me**, Electroblob, as the author of _Electroblob's Wizardry_, and **give a link** to the original mod (i.e. this page, the Minecraft Forum thread or the mods.curse.com page). After all, nobody can play your addon without downloading wizardry as well!
- 将我，Electroblob，**标记为** _Electroblob's Wizardry_ 的作者，并且**给出**原 mod 的下载链接（该 mod 的 Minecraft Fourm 的主题或者 mods.curse.com 页面）。 毕竟没有人可以在不下载 wizadry 的情况下玩你的附属 mod ！
- You do not make money off of your addon mod in any way. **This includes AdFly** and other URL shorteners. The **only** exception to this rule is the **Curse rewards program**. Making money from videos featuring your addon mod **is** allowed. (_The reason for this rule is as follows: I haven't put wizardry behind a URL shortener because I don't want my users to go through that just to download the mod, and as such I don't want users of addons to have to go through it either. If you want to discuss permissions, please don't hesitate to ask me._)
- 你不能将附属 mod 用于商用。**这包括 AdFly** 和其他网址缩短服务。**唯一**的例外是 **Curse rewards program** 。当然你**可以**通过附属 mod 的视频或直播盈利。(_我制定这个协议的原因是：我没有在 wizedry 上使用 网址缩短服务，因为我不想让用户不得不使用这些进行下载，我也不想让附属 mod 这么做。如果你想要获得许可，请不要犹豫，可以问我。_)
> I recommend using CurseForge to distribute your addon mod, because it allows you to specify that it's an addon to Wizardry.
> 我推荐使用 CurseForge 去发布你的附属 mod ，因为它允许你把它列为 Wizadry 的附属。

I also ask that you notify me if you release an addon mod, either on [Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry) or the [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod). It's not required, but if you do I will add a link to your addon in Wizardry's description!
我也想要你在发布附属 mod 之后告知我，你可以通过[Discord](https://discord.gg/MTmMzMv), [CurseForge](https://minecraft.curseforge.com/projects/electroblobs-wizardry)或者 [Minecraft Forum thread](http://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2818029-electroblobs-wizardry-the-expandable-rpg-magic-mod) 这些渠道。这不是必须的，但是如果你这么做了，我会在 Wizadry 的描述中为你的附属添加一个链接！

There's also a **#spell-packs** channel on the wizardry Discord server where you can come and tell people all about your spell pack, so be sure to check that out!
在 wizadry 的 Discord 中有一个 **#spell-packs** 频道，你可以将你的附属 mod 发布到此处，所以一定要来看看！
