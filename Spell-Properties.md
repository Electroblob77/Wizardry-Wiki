_Since: Wizardry 4.2_

巫术学的每一个[[法术|法术]]的各种属性都由一个 JSON 文件指定。这个文件在此 mod 的 jar 文件的`assets/ebwizardry/spells`目录下，并且在其启动时加载。其他拓展 mod 中的法术属性保存在它们自己的 jar 文件的`assets/[modid]/spells`目录下。

你可以在巫术学的 Github repository 中找到法术的属性文件：[此处](https://github.com/Electroblob77/Wizardry/tree/1.12.2/src/main/resources/assets/ebwizardry/spells)。

## 构成

  
法术属性文件包含以下标签：

 - **enabled（启用）**: 这是法术启用的 _contexts_ 列表。一般有 9 个contexts:
  - **book（法术书）**: 将值设置为 true 以启用此法术的[[法术书]]，将值设置为 false 以禁用。如果将其禁用，那么玩家将不能获得该法术的法术书（在生存模式下），同时也不能将其绑定到[[魔杖]]。
  - **scroll（卷轴）**: 将值设置为 true 以启用此法术的[[卷轴|卷轴]]，将值设置为 false 以禁用。如果将其禁用，那么玩家将不能获得该法术的卷轴（在生存模式下），同时也不能右键使用它。
  - **wands（魔杖）**: 将值设置为 true 以允许魔杖发动该法术，将值设置为 false 以禁用。如果将其禁用，那么该法术将不能绑定到魔杖，同时魔杖也不能发动该法术。
  - **npcs**:将值设置为 true 以允许 NPC 发动该法术，将值设置为 false 以禁用。如果将其禁用，那么[[巫师|巫师]]和其他能够施法的生物/在生成时将不会装备该法术，同时已经装备该法术的生物/NPC将不能发动该法术。 它还将被排除在[[wizard_spell的战利品表|wizard_spell的战利品表]]以外, 所以击杀邪恶巫师不会掉落它。
  - **dispensers（发射器）**: 将值设置为 true 以允许发射器发动该法术，将值设置为 false 以禁用。如果将其禁用，那么该法术的卷轴将会被发射器像物品一样扔出去而不是发动该法术。
  - **commands（命令）**: 将值设置为 true 以允许使用命令发动该法术，将值设置为 false 以禁用。如果将其禁用，那么在使用`/cast`命令发动该法术时会失败。
  - **treasure（宝藏）**: 将值设置为 true 以将此法术包含在战利品箱内，将值设置为 false 以禁用。如果将其禁用，那么在箱子的战利品表使用[[random_spell loot function|Loot Functions#random_spell]]时，这个法术将会被排除在外。
  - **trades（交易）**: 将值设置为 trupropertye 以将此法术包含在巫师的交易项内，将值设置为 false 以禁用。如果将其禁用，新生成的巫师将不会在交易项内提供该法术的法术书，同时现有巫师新解锁的交易项中也将不会包含它。
  - **looting（战利品）**:将值设置为 true 以将此法术的法术书包含在生物的稀有掉落物中内，将值设置为 false 以禁用。如果将其禁用，那么在实体的战利品表使用[[random_spell loot function|Loot Functions#random_spell]]时，这个法术将会被排除在外。
- **tier（等级）**: 确定法术的 [[等级|等级]]. 有效的等级为 `"novice"` （基础）, `"apprentice"` （学徒）, `"advanced"` （进阶）和 `"master"` （大师）。 
- **element（属性）**: 确定法术的[[元素|元素]].有效的属性为`"magic"` （无属性）, `"fire"` （火焰）, `"ice"` （冰霜）, `"lightning"` （雷电）, `"necromancy"` （死灵）, `"earth"` （大地）, `"sorcery"` （秘法）和 `"healing"` （治疗）。
- **type（类型）**: 确定法术的[[类型|类型]].。 `"attack"` （攻击）, `"defence"` （防御）, `"utility"` （功能）, `"minion"` （召唤）, `"buff"` （加成）, `"construct"` （造物）, `"projectile"` （投掷物）和 `"alteration"` （改造）。
- **cost（消耗）**: 确定法术的魔力值消耗。
- **chargeup**: 目前未使用。
- **cooldown（冷却）**: 确定法术的冷却时间, 用刻（tick）来表示 (20 刻 = 1 秒) 。
- **base_properties**: _法术特殊属性_ 列表。 不同的法术将会有不同的属性，这取决于它们的用途，有的法术没有。法术属性的名称通常都会很清楚地介绍该法术。
  - **[property name]（属性名称）**: 确定特殊属性的数值。
  - ...

例如，下面是[[magic missile]]的法术属性文件：

```json
{
	"enabled": {
		"book": true,
		"scroll": true,
		"wands": true,
		"npcs": true,
		"dispensers": true,
		"commands": true,
		"treasure": true,
		"trades": true,
		"looting": true
	},
	"tier": "novice",
	"element": "magic",
	"type": "projectile",
	"cost": 5,
	"chargeup": 0,
	"cooldown": 5,
	"base_properties": {
		"damage": 3,
		"range": 18
	}
}
```

这里的 `"damage"` 标签确定了击中玩家或生物时造成的伤害, `"range"` 标签确定了它的最大飞行距离。

>  每一个法术的属性都由它们自己独立的 JSON  文件指定。删除 `JSONSyntaxException` 中的任何一个属性会使游戏崩溃，增加多余的属性不会有任何效果。例如，在法术中添加 `"blast_radius"` 标签不会让该法术拥有爆炸属性，因为它要在代码中实现。

## 修改法术属性

修改法术属性会改变法术的行为——你可以用它制作整合包，小游戏，或者按你的喜好修改游戏。

目前唯一的改变法术属性的方法是修改 mod 的 jar 文件。你需要用一个解压缩软件（比如 7zip ）去提取 mod 的 jar 中的 JSON 文本（或者将 jar 文件的后缀名改为 .zip 并使用系统自带的解压缩软件进行解压）。然后你就可以通过修改该文件以改变法术的各种属性，当修改完成时，用这个 JSON 文件覆盖 mod 的 jar 中原来的文件（或者再次将解压后的 zip 文件压缩并将后缀名改为 .jar ），启动你的 _Minecraft_ ，你可以看到在游戏中你修改的法术属性！

> 在将来，你将不需要通过修改 mod 的 jar 文件的方式去修改法术属性。
