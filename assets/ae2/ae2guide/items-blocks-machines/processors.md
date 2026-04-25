---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: プロセッサ
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# プロセッサ

<Row>
  <ItemImage id="logic_processor" scale="4" />

  <ItemImage id="calculation_processor" scale="4" />

  <ItemImage id="engineering_processor" scale="4" />
</Row>

プロセッサは、AE2の[デバイス](../ae2-mechanics/devices.md)やマシンで使われる主要な素材のひとつです。また、最初に直面する大きな自動化課題のひとつでもあります。プロセッサには3種類あり、それぞれ金、<ItemLink id="certus_quartz_crystal" />、ダイヤモンドを使って作られます。これらは[プレス](presses.md)を使い、<ItemLink id="inscriber" />で複数段階の工程を経て作成します(通常は複数のインスクライバーとフィルター付き配管で自動化されます)。

## 製造手順

<Column gap="5">
  1.  必要な素材を集める、または作成します: シリコン、レッドストーン、金、<ItemLink id="certus_quartz_crystal" />、ダイヤモンド。

  <RecipeFor id="silicon" />

  <br />

  2.  前提となる印刷済み回路部品をプレスします

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3.  最終組み立て

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>
