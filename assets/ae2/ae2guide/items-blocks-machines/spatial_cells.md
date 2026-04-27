---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 空間ストレージセル
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# 空間ストレージセル

<Row>
  <ItemImage id="spatial_storage_cell_2" scale="4" />

  <ItemImage id="spatial_storage_cell_16" scale="4" />

  <ItemImage id="spatial_storage_cell_128" scale="4" />
</Row>

空間ストレージセルは、[空間ストレージ](../ae2-mechanics/spatial-io.md)として物理的な空間を保存するために使用されます。
<ItemLink id="spatial_io_port" />で使用します。

[ストレージセル](../items-blocks-machines/storage_cells.md)とは異なり、空間セルは一度使用すると再フォーマットできません。

繰り返しますが、**空間セルは使用後にリセット・再フォーマット・サイズ変更を行うことはできません。** 異なるサイズを使用したい場合は新しいセルを作成してください。

## レシピ

<Row>
  <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />

  <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />

  <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
</Row>

# ハウジング

セルは空間コンポーネントとハウジングを組み合わせて作成するか、空間コンポーネントの周囲をハウジングで囲むレシピでも作成できます：

<Row>
  <Recipe id="network/cells/spatial_storage_cell_2_cubed" />

  <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
</Row>

ハウジング単体は以下のように作成します：

  <RecipeFor id="item_cell_housing" />

# 空間コンポーネント

空間コンポーネントは空間ストレージセルの中核となる部品です。各ティアごとに保存可能な空間サイズが8倍に増加します。

  <Row>
    <RecipeFor id="spatial_cell_component_2" />

    <RecipeFor id="spatial_cell_component_16" />

    <RecipeFor id="spatial_cell_component_128" />
  </Row>
