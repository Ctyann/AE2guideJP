---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: MEインポートバス
  icon: import_bus
  position: 220
categories:
- devices
item_ids:
- ae2:import_bus
---

# MEインポートバス

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/import_bus.snbt" />
</GameScene>

MEインポートバスは接触しているインベントリからアイテムや流体(およびアドオンによって追加されたその他のもの)を取り出し、
[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ送り込みます。

ラグ軽減のため、MEインポートバスが最近何も搬入していない場合、ある種の
「スリープモード」に入り低速で動作します。そして何かの搬入に成功すると復帰し、最大速度(毎秒4回動作)まで加速します。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

## フィルター

デフォルトでは、このバスはアクセス可能なものを何でも搬入します。フィルタースロットに入れたアイテムがホワイトリストとして機能し、
その特定のアイテムのみ搬入できるようになります。

実際にそのアイテムを所持していなくても、JEI/REIからアイテムや流体をスロットへドラッグできます。

バケツや流体タンクのような流体コンテナを持って右クリックすると、バケツやタンク自体ではなく、その中の流体をフィルターとして設定できます。

## アップグレード

MEインポートバスは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="capacity_card" /> フィルタースロット数を増やします
*   <ItemLink id="speed_card" /> 1回の動作で移動する量を増やします
*   <ItemLink id="fuzzy_card" /> 耐久値でのフィルターや、アイテムNBTの無視を可能にします
*   <ItemLink id="inverter_card" /> フィルターをホワイトリストからブラックリストへ切り替えます
*   <ItemLink id="redstone_card" /> レッドストーン制御を追加し、高信号時、低信号時、またはパルスごとに1回だけ動作させられます

## 速度

| 加速カード | 1回の動作で移動するアイテム数 |
|:-----------|:------------------------------|
| 0          | 1                             |
| 1          | 8                             |
| 2          | 32                            |
| 3          | 64                            |
| 4          | 96                            |

## レシピ

<RecipeFor id="import_bus" />
