---
navigation:
  parent: example-setups/example-setups-index.md
  title: アメジストファーム
  icon: minecraft:amethyst_shard
---

# アメジストの採取

<ItemLink id="growth_accelerator" />はアメジストにも有効ですが、通常のように[サートス芽](../items-blocks-machines/budding_certus.md)を<ItemLink id="annihilation_plane" />でフィルタリングする方法はアメジストではうまく機能しません。非成熟のサートス芽は<ItemLink id="certus_quartz_dust" />をドロップするのに対し、アメジストの未成熟芽は何もドロップしないため、ネットワークが「空」を常に保持できる結果としてアニヒレーションプレーンは常にそれを破壊してしまいます。

この問題の回避方法は、アニヒレーションプレーンにシルクタッチを付与することです。これにより未成熟のアメジスト芽もブロックとしてドロップするようになり、フィルタリングが可能になります。

その後、<ItemLink id="minecraft:amethyst_cluster" />を<ItemLink id="formation_plane" />によって再設置し、それをシルクタッチなしの<ItemLink id="annihilation_plane" />で再び破壊することで、<ItemLink id="minecraft:amethyst_shard" />を得ることができます。

なお、クラスタは方向性を持つため、フォーメーションプレーンの反対側に必ず固体ブロック面が必要です。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/amethyst_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 1 1" max="3 2 2">
        (1) アニヒレーションプレーン #1：GUIなし（設定不可）、ただしシルクタッチ付き
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1 1" max="2.3 2 2">
        (2) フォーメーションプレーン：アメジストクラスターにフィルタリング
        <ItemImage id="minecraft:amethyst_cluster" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 0.7 1" max="2 1 2">
        (3) アニヒレーションプレーン #2：GUIなし（設定不可）、フォーチュン付与可能
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="1.3 1 2">
        (4) ストレージバス #1：アメジストシャードにフィルタリング
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 .7" max="1 1 1">
        (5) ストレージバス #2：アメジストシャードにフィルタリング。メインストレージより高優先度
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        メインネットワークへ接続
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 構成

* 最初の<ItemLink id="annihilation_plane" />（1）はGUIなしで設定不可だが、シルクタッチ必須
* <ItemLink id="formation_plane" />（2）は<ItemLink id="minecraft:amethyst_cluster" />にフィルタリング
* 2つ目の<ItemLink id="annihilation_plane" />（3）はGUIなしで設定不可だが、フォーチュン付与可能
* 最初の<ItemLink id="storage_bus" />（4）は<ItemLink id="minecraft:amethyst_shard" />にフィルタリング
* 2つ目の<ItemLink id="storage_bus" />（5）は<ItemLink id="minecraft:amethyst_shard" />にフィルタリングされ、さらに
  [優先度](../ae2-mechanics/import-export-storage.md#storage-priority)がメインストレージより高く設定されている

## 動作原理

1. 最初の<ItemLink id="annihilation_plane" />は前方を破壊しようとしますが、サブネット内のストレージがフォーメーションプレーンのみであり、かつアメジストクラスターにフィルタされているため、それのみを対象とします。シルクタッチが付与されていない場合、未成熟状態では何もドロップしないため挙動が変化する点が重要です。
2. <ItemLink id="formation_plane" />がクラスターを反対側のブロック面に設置します。
3. 2つ目の<ItemLink id="annihilation_plane" />がクラスターを破壊し、<ItemLink id="minecraft:amethyst_shard" />を生成します。
4. 最初の<ItemLink id="storage_bus" />がシャードをバレルへ保存します。この構成では実質的にフィルタは必須ではありません（破壊対象が成熟クラスターに限定されるため）。
5. 2つ目の<ItemLink id="storage_bus" />がメインネットワークへアメジストシャードへのアクセスを提供します。高[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)により、メインストレージよりもバレルへ優先的に戻されます。
