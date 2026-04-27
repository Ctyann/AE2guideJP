---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME 入出力ポート
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# ME 入出力ポート

<BlockImage id="io_port" p:powered="true" scale="8" />

入出力ポートを使うと、[ストレージセル](../items-blocks-machines/storage_cells.md)と
[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)の間で、高速に内容を出し入れできます。

<ItemLink id="certus_quartz_wrench" />で回転できます。

## 設定

*   入出力ポートは、セルが空になった時、満杯になった時、または処理完了時にセルを出力スロットへ移動するよう設定できます。
*   <ItemLink id="redstone_card" />を挿入すると、各種レッドストーン条件の設定項目が追加されます
*   GUI中央には矢印があり、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)への転送方向を、セルからストレージへ送るか、
    ストレージからセルへ送るか設定できます。

## アップグレード

入出力ポートは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="speed_card" /> 1回の動作で移動する量を増やします
*   <ItemLink id="redstone_card" /> レッドストーン制御を追加し、高信号時、低信号時、またはパルスごとに1回だけ動作させられます

## レシピ

<RecipeFor id="io_port" />
