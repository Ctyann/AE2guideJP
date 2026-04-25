---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ワイヤレスターミナル
  icon: wireless_crafting_terminal
  position: 410
categories:
- tools
item_ids:
- ae2:wireless_terminal
- ae2:wireless_crafting_terminal
---

# ワイヤレスターミナル

<Row>
  <ItemImage id="wireless_terminal" scale="4" />

  <ItemImage id="wireless_crafting_terminal" scale="4" />
</Row>

ワイヤレスターミナルは、通常の有線[ターミナル](terminals.md)の携帯版です。UIは完全に同一ですが、<ItemLink id="view_cell" />のスロットの代わりに[アップグレードカード](upgrade_cards.md)用のスロットが追加されています。

ネットワークに接続するには、対象ネットワークに接続された<ItemLink id="wireless_access_point" />の右上スロット（ワイヤレスターミナルのアイコンと矢印が表示されているスロット）にターミナルを挿入してペアリングします。

動作には<ItemLink id="wireless_access_point" />の通信範囲内にいる必要があります。

電力は<ItemLink id="charger" />で充電できます。

# ワイヤレスターミナル

<ItemImage id="wireless_terminal" scale="4" />

基本となるワイヤレスターミナルです。携帯可能になったターミナルとして、<ItemLink id="wireless_access_point" />の範囲内であればどこからでも、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)の閲覧やアクセス、[自動クラフト](../ae2-mechanics/autocrafting.md)の要求が可能になります。

## UI

[ターミナル](terminals.md)を参照してください。

## アップグレード

ワイヤレスターミナルは以下の[アップグレード](upgrade_cards.md)に対応しています：

*   <ItemLink id="energy_card" />：バッテリー容量を増加

## レシピ

<RecipeFor id="wireless_terminal" />

# ワイヤレスクラフトターミナル

<ItemImage id="wireless_crafting_terminal" scale="4" />

ワイヤレスクラフトターミナルは通常のワイヤレスターミナルと同様の機能を持ちますが、ネットワークストレージから自動補充されるクラフトグリッドが追加されています。出力をシフトクリックする際は注意してください。

## UI

[ターミナル](terminals.md)を参照してください。

## アップグレード

ワイヤレスクラフトターミナルは以下の[アップグレード](upgrade_cards.md)に対応しています：

*   <ItemLink id="energy_card" />：バッテリー容量を増加

## レシピ

<RecipeFor id="wireless_crafting_terminal" />
