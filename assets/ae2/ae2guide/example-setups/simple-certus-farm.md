---
navigation:
  parent: example-setups/example-setups-index.md
  title: シンプル・ケルタスファーム
  icon: certus_quartz_crystal
  position: 110
---

# シンプル・ケルタスファーム

[ケルタス成長](../ae2-mechanics/certus-growth.md)で述べられている通り、<ItemLink id="certus_quartz_crystal" />の収穫自動化には<ItemLink id="annihilation_plane" />と<ItemLink id="storage_bus" />を使用します。
<ItemLink id="growth_accelerator" />はケルタスの芽の成長を大幅に高速化し、その後アンナイレーションプレーンが成長した<ItemLink id="quartz_cluster" />を破壊します。
このとき、未成熟のケルタス芽は何もドロップしないのではなく、代わりに<ItemLink id="certus_quartz_dust" />をドロップするという性質を利用してフィルタリングされています。

このファームは<ItemLink id="flawless_budding_quartz" />を使う場合は完全自動で動作しますが、欠け・割れ・損傷したバドゥング・ケルタスを使用する場合は手動でブロックを交換する必要があります。
あるいは[セミオート・ケルタスファーム](semiauto-certus-farm.md)や[高度なケルタスファーム](advanced-certus-farm.md)で説明されているように自動化することも可能です。

速度の目安については[ケルタス成長](../ae2-mechanics/certus-growth.md)を参照してください。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/simple_certus_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="3.7 1 1" max="4 2 2">
        (1) アンナイレーションプレーン：GUIなし。ただし幸運エンチャントを付与可能
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="3.3 2 2">
        (2) ストレージバス #1：ケルタス水晶にフィルタ設定
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 .7" max="2 2 1">
        (3) ストレージバス #2：ケルタス水晶にフィルタ設定。メインストレージより高い優先度に設定
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 構成設定

* 最初の<ItemLink id="annihilation_plane" />（1）：GUIなしで設定不可。ただし幸運を付与可能
* 最初の<ItemLink id="storage_bus" />（2）：<ItemLink id="certus_quartz_crystal" />にフィルタ設定
* 2つ目の<ItemLink id="storage_bus" />（3）：<ItemLink id="certus_quartz_crystal" />にフィルタ設定し、[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)をメインストレージより高く設定

## 動作原理

1. <ItemLink id="annihilation_plane" />は前方のブロックを破壊しようとするが、サブネット上の唯一のストレージが<ItemLink id="storage_bus" />であり、ケルタス水晶にフィルタされているため<ItemLink id="quartz_cluster" />のみ破壊可能となる
4. 最初の<ItemLink id="storage_bus" />がケルタス水晶をバレルに格納する
5. 2つ目の<ItemLink id="storage_bus" />がメインネットワークへケルタス水晶へのアクセスを提供する。これは高い[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)に設定されているため、ケルタス水晶はメインストレージよりも優先してバレルへ戻される
