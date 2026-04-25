---
navigation:
  parent: example-setups/example-setups-index.md
  title: セミオート・ケルタス鉱石 ファーム
  icon: certus_quartz_crystal
  position: 115
---

# セミオート・ケルタスファーム

残念ながら、[シンプルなケルタスファーム](simple-certus-farm.md)は完全自動化するために<ItemLink id="flawless_budding_quartz" />が必要です。
そのためには[Spatial IO](../ae2-mechanics/spatial-io.md)を使うか、[隕石](../ae2-mechanics/meteorites.md)の場所にファームを構築する必要があります。

しかしAE2はブロックの設置と破壊が可能なため、ファーム側で*バドゥング・ケルタスを自動で交換する*仕組みを作ることができます。
（ただし定期的に<ItemLink id="flawed_budding_quartz" />を入力バレルへ補充し、消費済みのバドゥング・ケルタスから<ItemLink id="quartz_block" />を取り出す必要があります）

完全自動化については[高度なケルタスファーム](advanced-certus-farm.md)を参照してください。

このファームは[シンプルなケルタスファーム](simple-certus-farm.md)よりも少し複雑で、実際には3つの異なる仕組みを組み合わせたものです。

速度の目安については[ケルタス成長](../ae2-mechanics/certus-growth.md)を参照してください。

**この構成は複雑で、他のブロックの裏に隠れている要素があります。必ず視点を動かして全体を確認してください。**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/semiauto_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) クラスターブレーカー：GUIなし。ただし幸運（Fortune）を付与可能
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1" max="2.3 3 2">
        (2) ストレージバス #1：ケルタス水晶にフィルタ設定
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    クラスター破壊サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) ブロックブレーカー：GUIなし。シルクタッチ必須
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1" max="2.3 2 2">
        (4) ストレージバス #2：ケルタスブロックにフィルタ設定
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    ケルタスブロック破壊サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) フォーメーションプレーン：デフォルト設定
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0 1" max="2.3 1 2">
        (6) インポートバス：デフォルト設定
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    バドゥングブロック設置サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="0.7 2 1" max="1 3 2">
        (7) ストレージバス #3：ケルタス水晶にフィルタ設定。メインストレージより高優先度
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

    <DiamondAnnotation pos="1.5 0.5 1.5" color="#00ff00">
        手動でバドゥング・ケルタスを投入
        <BlockImage id="flawed_budding_quartz" scale="2" />
    </DiamondAnnotation>

    <DiamondAnnotation pos="1.5 1.5 1.5" color="#00ff00">
        ケルタスブロックを手動回収
        <BlockImage id="quartz_block" scale="2" />
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## 構成設定

### クラスターブレーカー：

* 最初の<ItemLink id="annihilation_plane" />（1）はGUIなしで設定不可。ただし幸運を付与可能
* 最初の<ItemLink id="storage_bus" />（2）は<ItemLink id="certus_quartz_crystal" />にフィルタ設定

### ケルタスブロックブレーカー：

* 2つ目の<ItemLink id="annihilation_plane" />（3）はGUIなし。シルクタッチ必須
* 2つ目の<ItemLink id="storage_bus" />（4）は<ItemLink id="quartz_block" />にフィルタ設定

### バドゥングブロック設置：

* <ItemLink id="formation_plane" />（5）：デフォルト設定
* <ItemLink id="import_bus" />（6）：デフォルト設定

### メインネットワーク側：

* 3つ目の<ItemLink id="storage_bus" />（7）は<ItemLink id="certus_quartz_crystal" />にフィルタ設定し、[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)をメインストレージより高く設定

## 動作原理

### クラスターブレーカー：

このサブネットは[シンプルなケルタスファーム](simple-certus-farm.md)のサブネットと非常によく似ています。

1. <ItemLink id="annihilation_plane" />は前方のブロックを破壊しようとしますが、サブネット上の唯一のストレージである<ItemLink id="storage_bus" />がケルタス水晶にフィルタされているため、<ItemLink id="quartz_cluster" />のみ破壊可能です
2. <ItemLink id="storage_bus" />はケルタス水晶をバレルに格納します

### ケルタスブロックブレーカー：

このサブネットは、バドゥングブロックが消耗して通常の<ItemLink id="quartz_block" />になった際に破壊する役割を持ちます。クラスターブレーカーと同様に動作します。

1. <ItemLink id="annihilation_plane" />は前方を破壊しようとしますが、ストレージバスが<ItemLink id="quartz_block" />にフィルタされているためそれのみ破壊可能です。シルクタッチによりバドゥングブロックが劣化せず、早期破壊も防ぎます
2. <ItemLink id="storage_bus" />はケルタスブロックを消費済みバドゥング用バレルへ格納します。その後、水中で<ItemLink id="charged_certus_quartz_crystal" />と組み合わせてリフレッシュする必要があります

### バドゥングブロック設置：

このサブネットは、破壊された消耗ブロックの代わりに新しい<ItemLink id="flawed_budding_quartz" />を設置する役割を持ちます。

1. <ItemLink id="import_bus" />が入力バレルからバドゥングブロックを取り出す
2. サブネット上の唯一のストレージである<ItemLink id="formation_plane" />がそれを設置する

### メインネットワーク：

* <ItemLink id="storage_bus" />はメインネットワーク（および[チャージャー自動化](charger-automation.md)）からバレル内のすべてのケルタス水晶へアクセス可能にする
* ただしメインストレージより高優先度に設定されているため、ケルタス水晶は優先的にバレルへ戻される
