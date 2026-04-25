---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ネットワークツール
  icon: network_tool
  position: 410
categories:
- tools
item_ids:
- ae2:network_tool
---

# ネットワークツール

<ItemImage id="network_tool" scale="4" />

ネットワークツールは、ネットワーク診断情報の表示や[アップグレードカード](upgrade_cards.md)の保存もできる改造版の[レンチ](wrench.md)です。
レンチの「素早く分解する」「ケーブルから[サブパーツ](../ae2-mechanics/cable-subparts.md)を取り外す」といった機能は維持していますが、
物を回転させることはできません。

[アップグレードカード](upgrade_cards.md)を保存するための9スロットを備えており、このツールがインベントリ内のどこかにあれば、
どのAE2デバイスUIでもそれらを使用できます。

ネットワークの任意の部分を右クリックすると、<ItemLink id="controller" />を右クリックした時と同様の診断情報ウィンドウが表示されます。
このウィンドウには以下が表示されます

*   ネットワークで使用中のチャンネル数
*   エネルギー表示をAEまたはE/FEで切り替えるグローバル設定
*   ネットワークに蓄えられた[エネルギー](../ae2-mechanics/energy.md)量と、ネットワークの最大エネルギー容量
*   ネットワークへ流入しているエネルギー量と、ネットワークが消費しているエネルギー量
*   ネットワーク上のすべての[デバイス](../ae2-mechanics/devices.md)および構成要素の一覧

このウィンドウは、[サブネットワーク](../ae2-mechanics/subnetworks.md)を扱っている時に、
異なる2本のケーブルやデバイスが同じネットワークに属しているか確認するのにも役立ちます。

## ファサードの非表示

<a href="facades.md">ファサード</a>は、どちらかの手にネットワークツールを持っている間は非表示になります。

ファサードを外さなくても、非表示中のファサード越しに背後のブロックを操作できます。

## レシピ

<RecipeFor id="network_tool" />
