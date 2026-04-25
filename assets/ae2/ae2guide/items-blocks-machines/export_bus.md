---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: MEエクスポートバス
  icon: export_bus
  position: 220
categories:
- devices
item_ids:
- ae2:export_bus
---

# エクスポートバス

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/export_bus.snbt" />
</GameScene>

エクスポートバスは[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)からアイテムや流体(およびアドオンによって追加されたその他のもの)を取り出し、
接触しているインベントリへ送り込みます。

ラグ軽減のため、エクスポートバスが最近何も搬出していない場合、ある種の
「スリープモード」に入り低速で動作します。そして何かの搬出に成功すると復帰し、最大速度(毎秒4回動作)まで加速します。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

## フィルター

デフォルトでは、このバスは何も搬出しません。フィルタースロットに入れたアイテムがホワイトリストとして機能し、
その特定のアイテムのみ搬出できるようになります。

実際にそのアイテムを所持していなくても、JEI/REIからアイテムや流体をスロットへドラッグできます。

バケツや流体タンクのような流体コンテナを持って右クリックすると、バケツやタンク自体ではなく、その中の流体をフィルターとして設定できます。

## アップグレード

インポートバスは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="capacity_card" /> フィルタースロット数を増やし、フィルターされたものをどの順番で搬出するかの設定を追加します。
*   <ItemLink id="speed_card" /> 1回の動作で移動する量を増やします
*   <ItemLink id="fuzzy_card" /> 耐久値でのフィルターや、アイテムNBTの無視を可能にします
*   <ItemLink id="crafting_card" /> バスが必要とするアイテムを得るために、[自動クラフト](../ae2-mechanics/autocrafting.md)
    システムへクラフト要求を送信できるようにします。可能ならストレージからアイテムを取り出すか、あるいは常に
    新しいアイテムのクラフトを要求するかを設定できます。
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
