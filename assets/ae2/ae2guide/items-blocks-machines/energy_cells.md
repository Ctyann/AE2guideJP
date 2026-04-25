---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: エネルギーセル
  icon: energy_cell
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_cell
- ae2:dense_energy_cell
- ae2:creative_energy_cell
---

# エネルギーセル

<Row gap="20">
  <BlockImage id="energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="8" />
</Row>

エネルギーセルは、ネットワークに[エネルギー](../ae2-mechanics/energy.md)の蓄積を追加します。ある程度のエネルギーバッファは、大量のアイテムが挿入または抽出される際のエネルギー消費のスパイクを平滑化するのに役立ちます。また、大量のエネルギーを瞬時に消費する[空間ストレージ](../ae2-mechanics/spatial-io.md)のような状況に対応するために、より多くのエネルギーを蓄えることができます。

## 充填バー

<Row>
<BlockImage id="energy_cell" scale="4" p:fullness="0" />
<BlockImage id="energy_cell" scale="4" p:fullness="1" />
<BlockImage id="energy_cell" scale="4" p:fullness="2" />
<BlockImage id="energy_cell" scale="4" p:fullness="3" />
<BlockImage id="energy_cell" scale="4" p:fullness="4" />
</Row>

セルの側面にあるバーは、エネルギーの充填量を示しています。

*   0: 25%未満の充電時
*   1: 25%から50%の間の充電時
*   2: 50%から75%の間の充電時
*   3: 75%から99%の間の充電時
*   4: 99%以上の充電時

## セルの種類

*   <ItemLink id="energy_cell" />は200k AEを蓄えることができ、通常のネットワーク使用の電力サージを簡単に処理できるため、ほとんどの用途で1つあれば十分です。
*   <ItemLink id="dense_energy_cell" />は1.6M AEを蓄えることができ、蓄えた電力でネットワークを稼働させたり、大規模な[空間ストレージ](../ae2-mechanics/spatial-io.md)セットアップの大量の瞬時エネルギー消費に対応するために使用されます。
*   <ItemLink id="creative_energy_cell" />はクリエイティブアイテムで、無限のエネルギーを提供します。

## レシピ

<Row>
  <RecipeFor id="energy_cell" />

  <RecipeFor id="dense_energy_cell" />
</Row>
