---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ファサード
  icon: facade
  icon_components:
    "ae2:facade_item": "minecraft:stone"
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:facade
---

# ファサード

ファサードを使うと、拠点をよりすっきりと見せられます。両方のサイズのケーブルを覆うことができ、
さまざまな種類のブロックで作成できます。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/facades_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

ケーブルの全方向を覆えますが、[サブパーツ](../ae2-mechanics/cable-subparts.md)やケーブル接続は
外へ突き出たままになります。

<GameScene zoom="6"  interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

拠点の見た目を良くしたり、各面で異なるテクスチャを持つブロックを作ったりするために、うまく活用しましょう。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_3.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## ファサードの非表示

どちらかの手に<a href="network_tool.md">ネットワークツール</a>を持っている間、ファサードは非表示になります。

非表示になったファサードは、先に取り外さなくてもその背後のブロックを操作できます。

## レシピ

4つの<ItemLink id="cable_anchor" />の中央に、見た目を使いたいブロックを配置します。

![Facade Recipe](../assets/diagrams/facade_recipe.png)
