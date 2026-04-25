---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: MEドライブ
  icon: drive
  position: 210
categories:
- devices
item_ids:
- ae2:drive
---

# MEドライブ

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/drive.snbt" />
</GameScene>

ドライブは、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)で使用するために[ストレージセル](storage_cells.md)を接続する[デバイス](../ae2-mechanics/devices.md)です。10個のスロットがあり、それぞれにセルを挿入できます。

必要に応じて、ホッパーやae2バスなどのアイテムロジスティクスを使用して、セルをインベントリからプッシュおよびプルすることができます。

<ItemLink id="certus_quartz_wrench" />を使用して回転させることができます。

## セルステータスLED

ドライブ内のセルには、ステータスを示すLEDがあります：

| 色     | ステータス                                                                 |
| :----- | :------------------------------------------------------------------------- |
| 緑     | 空                                                                         |
| 青     | 一部の内容が含まれている                                                   |
| オレンジ | [タイプ](../ae2-mechanics/bytes-and-types.md)が満杯で、新しいタイプを追加できない |
| 赤     | [バイト](../ae2-mechanics/bytes-and-types.md)が満杯で、これ以上アイテムを挿入できない |
| 黒     | 電力がない、またはドライブに[チャンネル](../ae2-mechanics/channels.md)がない |

## 優先度

GUIの右上にあるレンチをクリックして優先度を設定できます。
ネットワークにアイテムが入力されると、最初に最も優先度の高いストレージを目的地として選択します。同じ優先度のストレージやセルが2つある場合、すでにアイテムを含んでいるストレージが他のストレージよりも優先されます。[パーティション化](cell_workbench.md)されたセルは、他のストレージと同じ優先度グループにある場合、すでにアイテムを含んでいると見なされます。ストレージからアイテムを取り出す場合は、最も優先度の低いストレージから取り出されます。この優先度システムにより、アイテムがネットワークストレージに挿入および削除される際に、優先度の高いストレージが満たされ、優先度の低いストレージが空になります。

## レシピ

<RecipeFor id="drive" />
