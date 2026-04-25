---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: モニター
  icon: storage_monitor
  position: 210
categories:
- devices
item_ids:
- ae2:storage_monitor
- ae2:conversion_monitor
---

# モニター

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/monitors.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

モニターを使うと、GUIを開かずに単一のアイテムまたは流体の表示と操作ができます。

モニターは、取り付けられている[ケーブル](cables.md)の色を引き継ぎます。

モニターが床または天井に設置されている場合、<ItemLink id="certus_quartz_wrench" />で回転できます。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

# ストレージモニター

アイテムまたは流体とその数量を表示します。農場の近くなどに設置すると便利です。

[チャンネル](../ae2-mechanics/channels.md)を*必要としません*。

キー操作:

*   アイテムを持って右クリック、または流体コンテナでダブル右クリックすると、そのアイテム/流体をモニターに設定します。
*   素手で右クリックすると、モニター設定をクリアします。
*   素手でShift+右クリックすると、モニターをロックします。

## レシピ

<RecipeFor id="storage_monitor" />

# 変換モニター

変換モニターはストレージモニターに似ていますが、設定されたアイテムの挿入や取り出しも可能です。

設定されたアイテムが[自動クラフト](../ae2-mechanics/autocrafting.md)可能で、かつストレージ内に存在しない場合、
アイテムを取り出そうとすると、代わりにクラフト数量を指定するUIが開きます。

[チャンネル](../ae2-mechanics/channels.md)を*必要とします*。

追加のキー操作:

*   左クリックで設定されたアイテムを1スタック取り出します。ストレージに存在しない場合はそのアイテムのクラフトを要求します。
*   任意のアイテムを持って右クリックすると、そのアイテムを挿入します。
*   素手で右クリックすると、インベントリ内の設定済みアイテムをすべて挿入します。

## レシピ

<RecipeFor id="conversion_monitor" />
