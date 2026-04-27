---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: MEインターフェース
  icon: interface
  position: 210
categories:
- devices
item_ids:
- ae2:interface
- ae2:cable_interface
---

# MEインターフェース

<Row gap="20">
<BlockImage id="interface" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_interface.snbt" />
</GameScene>
</Row>

MEインターフェースは小型チェスト兼流体タンクのように動作し、スロットに設定した在庫内容に応じて[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)から
自動で補充・排出を行います。これは1ゲームティックで完了しようとするため、1ゲームティックあたり最大9スタックまで補充または排出でき、
高速なアイテムパイプがあれば非常に高速な搬入・搬出手段になります。

もうひとつ便利な特性として、多くの流体タンクは1種類の流体しか保存できませんが、MEインターフェースはアイテムに加えて最大9種類の流体を保存できます。
本質的には追加機能付きのチェスト/複数流体タンクであり、ネットワークから切り離しておけばその追加機能を無効化できます。
そのため、少量ずつさまざまなものを保存したいような限定的な用途でも役立ちます。

## MEインターフェースの内部動作

前述の通り、MEインターフェースは本質的にチェスト/タンクに、高性能な<ItemLink id="import_bus" />と
<ItemLink id="export_bus" />、そして多数の<ItemLink id="level_emitter" />を組み合わせたものです。

<GameScene zoom="3" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_internals.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 0.3 1.3" max="9.7 1 1.7">
        要求在庫数を制御する多数のレベルエミッター
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 4 1.3" max="9.7 4.7 1.7">
        要求在庫数を制御する多数のレベルエミッター
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/level_emitter.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 1.3 1.3" max="9.7 2 1.7">
        1ゲームティックあたり1スタック転送できる高性能MEインポートバス群
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/import_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 3 1.3" max="9.7 3.7 1.7">
        1ゲームティックあたり1スタック転送できる高性能MEエクスポートバス群
        <GameScene zoom="4" background="transparent">
        <ImportStructure src="../assets/blocks/export_bus.snbt" />
        </GameScene>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="10 3 2">
        9個の独立した内部スロット
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="15" />
</GameScene>

## 特殊な相互作用

MEインターフェースには、他のAE2[デバイス](../ae2-mechanics/devices.md)との特別な機能もいくつかあります。

未設定のMEインターフェースに<ItemLink id="storage_bus" />を接続すると、そのMEインターフェースが属するネットワークの[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)全体が、
あたかもMEストレージバスを置いた先に巨大なチェストがあるかのように、MEストレージバス側のネットワークへ提示されます。
MEインターフェースのフィルタースロットに在庫指定を設定すると、この機能は無効になります。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_storage.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

[サブネット](../ae2-mechanics/subnetworks.md)上のMEパターンプロバイダーは、MEインターフェースと特別な相互作用を持ちます。MEインターフェースが未設定の場合、
プロバイダーはそのMEインターフェースを完全にスキップし、そのサブネットの[ストレージ](../ae2-mechanics/import-export-storage.md)へ直接送り込みます。
これにより、MEインターフェースがレシピバッチで埋まるのを防ぎ、さらに重要なこととして、ストレージに空きができるまで次のバッチを投入しません。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        MEインターフェース (フルブロックではなく平面型である必要があります)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        MEストレージバス
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        パターン供給したい場所 (複数のマシン、または1台の複数面)
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 種類

MEインターフェースには通常型と平面型/[サブパーツ](../ae2-mechanics/cable-subparts.md)の2種類があります。これにより、どの面からインベントリへアクセスできるか、
またどの面にネットワーク接続を提供するかが変化します。

*   通常型MEインターフェースは、すべての面から搬入・搬出・インベントリアクセスが可能で、多くのAE2マシンと同様に
    全方向へネットワーク接続を提供するケーブルとして機能します。

*   平面型MEインターフェースは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)であり、同じケーブル上に複数設置できるため省スペース構成に向いています。
    正面から搬入・搬出・インベントリアクセスが可能ですが、正面にはネットワーク接続を提供しません。

MEインターフェースはクラフトグリッドで通常型と平面型を相互変換できます。

## 設定

MEインターフェース上段のスロットは、内部に保持しておく在庫内容を決定します。そこへアイテムを置くかJEI/REIからドラッグすると、
数量を設定するためのレンチが表示されます。

バケツや流体タンクのような流体コンテナを持って右クリックすると、バケツやタンク自体ではなく、その中の流体をフィルターとして設定できます。

スロットを在庫保持モードに設定すると、そのスロットには外部マシンから別のものを挿入できなくなります。

## アップグレード

MEインターフェースは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="fuzzy_card" /> バスが耐久値でのフィルターや、アイテムNBTの無視を可能にします
*   <ItemLink id="crafting_card" /> MEインターフェースが必要とするアイテムを得るために、[自動クラフト](../ae2-mechanics/autocrafting.md)
    システムへクラフト要求を送信できるようにします。可能なら先にストレージからアイテムを取り出し、その後で
    新しいアイテムのクラフトを要求します。

## 優先度

GUI右上のレンチをクリックして優先度を設定できます。優先度の高いMEインターフェースほど、
低いものより先にアイテムを受け取ります。

## レシピ

<Recipe id="network/blocks/interfaces_interface" />

<RecipeFor id="cable_interface" />
