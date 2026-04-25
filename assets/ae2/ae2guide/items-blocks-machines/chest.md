---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: MEチェスト
  icon: chest
  position: 210
categories:
- devices
item_ids:
- ae2:chest
---

# MEチェスト

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/chest.snbt" />
</GameScene>

MEチェストは、<ItemLink id="terminal" />、<ItemLink id="drive" />、<ItemLink id="energy_acceptor" />を備えたミニネットワークのように機能します。小さなストレージネットワークとして使用できますが、1つの[ストレージセル](../items-blocks-machines/storage_cells.md)しか収容できないため、その用途は限られています。

代わりに、内部に取り付けられたストレージセルと特にやり取りするために便利です。その統合端末は取り付けられたドライブ内のアイテムのみを表示およびアクセスできますが、一般的なネットワーク上の[デバイス](../ae2-mechanics/devices.md)は、MEチェストを含む任意の[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)内のアイテムにアクセスできます。

2つの異なるGUIがあり、アイテム輸送のために側面が設定されています。上部端末を操作すると統合端末が開きます。この面を通じて取り付けられたストレージセルにアイテムを挿入できますが、取り出すことはできません。他の面を操作すると、ストレージセルのスロットと優先設定のGUIが開きます。セルは、セルスロットのある面を通じてのみアイテムロジスティクスによって挿入および取り外すことができます。

<ItemLink id="certus_quartz_wrench" />で回転させることができます。

小さなAEエネルギーバッファを備えているため、[エネルギーセル](../items-blocks-machines/energy_cells.md)のないネットワーク上では、一度に多くのアイテムを挿入または抽出すると停電する可能性があります。

端末は<ItemLink id="color_applicator" />で色を付けることができます。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/chest_color.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 設定

MEチェストには、<ItemLink id="terminal" />や<ItemLink id="crafting_terminal" />と同じ設定がすべてあります。ただし、<ItemLink id="view_cell" />はサポートしていません。

## セルステータスLED

チェスト内のセルには、そのステータスを示すLEDがあります:

| 色    | ステータス                                                                           |
| :----- | :------------------------------------------------------------------------------- |
| 緑    | 空です                                                                            |
| 青    | 一部の内容があります                                                                |
| オレンジ | [タイプ](../ae2-mechanics/bytes-and-types.md)が満杯で、新しいタイプを追加できません     |
| 赤    | [バイト](../ae2-mechanics/bytes-and-types.md)が満杯で、これ以上アイテムを挿入できません |
| 黒    | 電力がない、またはドライブに[チャンネル](../ae2-mechanics/channels.md)がありません     |

## 優先順位

セルスロットGUIの右上のレンチをクリックして優先順位を設定できます。
ネットワークに入るアイテムは、最初の宛先として最も高い優先順位のストレージから開始します。2つのストレージまたはセルが同じ優先順位を持つ場合、1つがすでにアイテムを含んでいる場合は、他のストレージよりもそのストレージを優先します。同じ優先順位グループ内の他のストレージと比較して、[パーティション化](cell_workbench.md)されたセルはすでにアイテムを含んでいると見なされます。ストレージからアイテムを削除する場合は、最も低い優先順位のストレージから削除されます。この優先順位システムにより、アイテムがネットワークストレージに挿入および削除されると、高い優先順位のストレージが満たされ、低い優先順位のストレージが空になります。

## レシピ

<RecipeFor id="chest" />
