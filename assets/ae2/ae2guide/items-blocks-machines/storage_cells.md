---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ストレージセル
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# ストレージセル

<Column>
  <Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

  <Row>
    <ItemImage id="fluid_storage_cell_1k" scale="4" />

    <ItemImage id="fluid_storage_cell_4k" scale="4" />

    <ItemImage id="fluid_storage_cell_16k" scale="4" />

    <ItemImage id="fluid_storage_cell_64k" scale="4" />

    <ItemImage id="fluid_storage_cell_256k" scale="4" />
  </Row>
</Column>

ストレージセルは、Applied Energisticsにおける主要なストレージ手段のひとつです。<ItemLink id="drive" />や<ItemLink id="chest" />に挿入して使用します。

容量（バイトおよびタイプ）については[Bytes and Types](../ae2-mechanics/bytes-and-types.md)を参照してください。

セルの中身が空であれば、手に持った状態でシフト＋右クリックすることで、ストレージコンポーネントをハウジングから取り外すことができます。

<Row>
    <Recipe id="upgrade/item_storage_cell_1k_to_4k" />

    ストレージセルは、より高位のストレージコンポーネントとクラフトすることで上位ティアへアップグレードできます。内容物は保持され、元の低位コンポーネントは返却されます。
</Row>

## タイプ数による容量変化

[タイプの初期コスト](../ae2-mechanics/bytes-and-types.md)の仕様により、1種類のみを保持しているセルは、63種類すべてを使用しているセルの約2倍の容量を持ちます。

| セル                                     | 1種類使用時の総容量 | 63種類使用時の総容量 |
| ---------------------------------------- | ------------------: | -------------------: |
| <ItemLink id="item_storage_cell_1k" />   |               8,128 |                4,160 |
| <ItemLink id="item_storage_cell_4k" />   |              32,512 |               16,640 |
| <ItemLink id="item_storage_cell_16k" />  |             130,048 |               66,560 |
| <ItemLink id="item_storage_cell_64k" />  |             520,192 |              266,240 |
| <ItemLink id="item_storage_cell_256k" /> |           2,080,768 |            1,064,960 |

## パーティショニング

セルは、ストレージバスと同様に特定のアイテムのみを受け入れるようフィルタリングできます。これは<ItemLink id="cell_workbench" />で設定します。

アイテムは実際に所持していなくても、JEI/REIからスロットへドラッグして設定可能です。

## アップグレード

ストレージセルは以下の[アップグレード](upgrade_cards.md)に対応しており、<ItemLink id="cell_workbench" />を通じて挿入できます：

* <ItemLink id="fuzzy_card" />（フルイドセルでは使用不可）：ダメージ値やNBTを無視したフィルタリングを可能にする
* <ItemLink id="inverter_card" />：ホワイトリストをブラックリストに反転
* <ItemLink id="equal_distribution_card" />：タイプごとに均等なバイト容量を割り当て、特定の種類がセルを占有しないようにする
* <ItemLink id="void_card" />：セルが満杯（またはイコールディストリビューション使用時はそのタイプ枠が満杯）の場合にアイテムを消去する。ファームの詰まり防止に有用だが、パーティション設定には注意
* ポータブルセルは<ItemLink id="energy_card" />を使用してバッテリー容量を増加可能

## カラーリング

ポータブルアイテムセルおよびフルイドセルは、革装備と同様に染料で着色できます。

# ハウジング

セルはストレージコンポーネントとハウジングを組み合わせるか、コンポーネントの周囲をハウジングで囲むことで作成できます：

<Row>
  <Recipe id="network/cells/item_storage_cell_1k" />

  <Recipe id="network/cells/item_storage_cell_1k_storage" />
</Row>

ハウジング単体は以下のレシピで作成されます：

<Row>
  <RecipeFor id="item_cell_housing" />

  <RecipeFor id="fluid_cell_housing" />
</Row>

# ストレージコンポーネント

ストレージコンポーネントはすべてのAE2セルの基礎であり、セルの容量を決定します。各ティアで容量は4倍になり、1つ上のティアを3個使用して作成されます。

<Column>
  <Row>
    <RecipeFor id="cell_component_1k" />

    <RecipeFor id="cell_component_4k" />

    <RecipeFor id="cell_component_16k" />
  </Row>

  <Row>
    <RecipeFor id="cell_component_64k" />

    <RecipeFor id="cell_component_256k" />
  </Row>
</Column>

# アイテムストレージセル

アイテムストレージセルは最大63種類の異なるアイテムを保持でき、すべての標準容量で利用可能です。

<Column>
  <Row>
    <Recipe id="network/cells/item_storage_cell_1k_storage" />

    <Recipe id="network/cells/item_storage_cell_4k_storage" />

    <Recipe id="network/cells/item_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/item_storage_cell_64k_storage" />

    <Recipe id="network/cells/item_storage_cell_256k_storage" />
  </Row>
</Column>

## ポータブルアイテムストレージ

これらは手の中の小さな<ItemLink id="chest" />、あるいはバックパックのようなものとして機能します。<ItemLink id="charger" />で充電可能です。

通常のストレージセルとは異なり、容量が増えるほどタイプ容量は減少し、総バイト容量も半分になります。

すべてのセルが受け取れるアップグレードカードに加えて、内部バッテリーを強化する<ItemLink id="energy_card" />も使用できます。

<Column>
  <Row>
    <RecipeFor id="portable_item_cell_1k" />

    <RecipeFor id="portable_item_cell_4k" />

    <RecipeFor id="portable_item_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_item_cell_64k" />

    <RecipeFor id="portable_item_cell_256k" />
  </Row>
</Column>

# フルイドストレージセル

フルイドストレージセルは最大5種類の異なる液体を保持でき、すべての標準容量で利用可能です。

<Column>
  <Row>
    <Recipe id="network/cells/fluid_storage_cell_1k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_4k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/fluid_storage_cell_64k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_256k_storage" />
  </Row>
</Column>

## ポータブルフルイドストレージ

これらは手の中の小さな<ItemLink id="chest" />、あるいはバックパックのようなものとして機能します。<ItemLink id="charger" />で充電可能です。

通常のストレージセルとは異なり、容量が増えるほどタイプ容量は減少し、総バイト容量も半分になります。

すべてのセルが受け取れるアップグレードカードに加えて、内部バッテリーを強化する<ItemLink id="energy_card" />も使用できます。

<Column>
  <Row>
    <RecipeFor id="portable_fluid_cell_1k" />

    <RecipeFor id="portable_fluid_cell_4k" />

    <RecipeFor id="portable_fluid_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_fluid_cell_64k" />

    <RecipeFor id="portable_fluid_cell_256k" />
  </Row>
</Column>

# クリエイティブストレージセル

<Row>
  <ItemImage id="creative_storage_cell" scale="2" />
</Row>

クリエイティブセルは**無限ストレージを提供するものではありません**。代わりに、[パーティション](cell_workbench.md)で指定したアイテムまたは液体について、無限の供給源および消費先として機能します。
