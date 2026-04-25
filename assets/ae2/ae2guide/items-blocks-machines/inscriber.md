---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 刻印機
  icon: inscriber
  position: 310
categories:
- machines
item_ids:
- ae2:inscriber
---

# 刻印機

<BlockImage id="inscriber" scale="8" />

刻印機は、[プレス](presses.md)を使って回路や[プロセッサ](processors.md)を刻印したり、さまざまなアイテムをダストへ粉砕したりするために使用されます。
AE2の電力(AE)またはFabric/Forge Energy(E/FE)のどちらも受け入れ可能です。側面設定に対応しており、異なる面からアイテムを挿入すると、
内部インベントリの異なるスロットへ挿入されます。これを扱いやすくするため、<ItemLink id="certus_quartz_wrench" />で回転できます。
また、加工結果を隣接インベントリへ送り出すよう設定することもできます。

入力バッファのサイズは調整可能です。たとえば、1つのインベントリから大量の刻印機へ供給したい場合、
小さいバッファにすると、素材がより効率よく刻印機間へ分配されます(最初の刻印機だけが64個まで埋まり、残りが空になるのを防げます)。

4種類の回路プレスは[プロセッサ](processors.md)のクラフトに使用されます

<Row>
  <ItemImage id="silicon_press" scale="4" />

  <ItemImage id="logic_processor_press" scale="4" />

  <ItemImage id="calculation_processor_press" scale="4" />

  <ItemImage id="engineering_processor_press" scale="4" />
</Row>

一方、名称プレスは金床のようにブロックへ名前を付けるために使え、<ItemLink id="pattern_access_terminal" />内で物にラベルを付けるのに便利です。

<ItemImage id="name_press" scale="4" />

## 設定

* 刻印機は、(下記のように)側面設定モードにするか、どの面からでも任意のスロットへ入力を許可し、内部フィルターで
    振り分けるモードに設定できます。非側面設定モードでは、上段と下段のスロットからアイテムを取り出すことはできません。
* 刻印機はアイテムを隣接インベントリへ送り出すよう設定できます。
* 入力バッファのサイズは調整可能です。大きい設定は手動供給する単体の刻印機向けで、
小さい設定は大規模な並列構成をより実用的にします。

## GUIと側面設定

側面設定モードでは、刻印機はどの面から挿入または取り出したかによって、入出力先を振り分けます。

![Inscriber GUI](../assets/diagrams/inscriber_gui.png) ![Inscriber Sides](../assets/diagrams/inscriber_sides.png)

A. **上段入力** 刻印機の上面からアクセスします(このスロットへは挿入・取り出しの両方が可能です)

B. **中央入力** 刻印機の左・右・前・後面から挿入します(このスロットへは挿入のみ可能で、取り出しはできません)

C. **下段入力** 刻印機の下面からアクセスします(このスロットへは挿入・取り出しの両方が可能です)

D. **出力** 刻印機の左・右・前・後面から取り出します(このスロットへは取り出しのみ可能で、挿入はできません)

## 簡易自動化

例として、側面設定と回転機能により、刻印機は次のように半自動化できます。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/inscriber_hopper_automation.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

あるいは、非側面設定モードで刻印機へ搬入・搬出するだけでも構いません。

## アップグレード

刻印機は以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="speed_card" />

## レシピ

<RecipeFor id="inscriber" />
