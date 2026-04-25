---
navigation:
  parent: example-setups/example-setups-index.md
  title: 高度なサートスファーム
  icon: certus_quartz_crystal
  position: 120
---

# 高度なサートスファーム

これは基本的に[半自動サートスファーム](semiauto-certus-farm.md)と同じですが、完全にあなたのMEシステムへ統合された構成です。

大量の芽生えたブロックを手動で補充する代わりに、この構成では[チャージャー自動化](charger-automation.md)と[水中投げ込み自動化](throw-in-water-automation.md)を使ってすべてを自動化します。

速度の目安については[サートス成長](../ae2-mechanics/certus-growth.md)を参照してください。

**この構成は複雑で、いろいろな要素が重なって隠れています。全体を見るために視点を動かしてください。**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) アニヒレーションプレーン #1：GUIなし（設定不可）だがフォーチュンを付与可能
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) ストレージバス #1：サートスクリスタルにフィルタリング
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    クラスターブレーカー・サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) アニヒレーションプレーン #2：GUIなし（設定不可）だがシルクタッチ必須
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) ストレージバス #2：サートスブロックにフィルタリング
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    サートスブロックブレーカー・サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) フォーメーションプレーン：デフォルト設定
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) インポートバス：フレイレッドバッディングサートスにフィルタリング
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    バッディングブロック配置サブネット
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) ストレージバス #3：サートスクリスタルにフィルタリング。メインストレージより高優先度
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) インターフェース：フレイレッドバッディングサートスを1つ保持する設定。クラフティングカード付き
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        メインネットワーク／チャージャー自動化／水中投げ込み自動化へ接続
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## 構成

### クラスターブレーカー：

* 最初の<ItemLink id="annihilation_plane" />（1）はGUIなしで設定不可だが、フォーチュンを付与可能
* 最初の<ItemLink id="storage_bus" />（2）は<ItemLink id="certus_quartz_crystal" />にフィルタリングされている

### サートスブロックブレーカー：

* 2つ目の<ItemLink id="annihilation_plane" />（3）はGUIなしで設定不可だが、シルクタッチ必須
* 2つ目の<ItemLink id="storage_bus" />（4）は<ItemLink id="quartz_block" />にフィルタリングされている

### バッディングブロック配置：

* <ItemLink id="formation_plane" />（5）はデフォルト設定
* <ItemLink id="import_bus" />（6）は<ItemLink id="flawed_budding_quartz" />にフィルタリング

### メインネットワーク側：

* 3つ目の<ItemLink id="storage_bus" />（7）は<ItemLink id="certus_quartz_crystal" />にフィルタリングされ、さらに[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)がメインストレージより高く設定されている
* <ItemLink id="interface" />（8）はフレイレッドバッディングサートスを1つ保持するよう設定され、<ItemLink id="crafting_card" />を搭載

## 動作原理

### クラスターブレーカー：

クラスターブレーカーサブネットは[シンプルなサートスファーム](simple-certus-farm.md)とほぼ同じ仕組みです。

1. <ItemLink id="annihilation_plane" />は前方を破壊しようとしますが、サブネット内のストレージが<ItemLink id="storage_bus" />のみで、かつ<ItemLink id="certus_quartz_crystal" />にフィルタされているため、それ以外は壊せません
2. <ItemLink id="storage_bus" />がサートスクリスタルをバレルに保存します

### サートスブロックブレーカー：

枯渇したバッディングブロックが通常の<ItemLink id="quartz_block" />になったときに破壊するためのサブネットです。

1. <ItemLink id="annihilation_plane" />は前方を破壊しようとしますが、ストレージバスが<ItemLink id="quartz_block" />にフィルタされているためそれのみ破壊可能です
   また、シルクタッチが必要で、バッディングブロックの劣化を防ぎます
2. <ItemLink id="storage_bus" />がブロックを<ItemLink id="interface" />へ送り、水中投げ込み自動化で新しい<ItemLink id="flawed_budding_quartz" />を生成します

### バッディングブロック配置：

枯渇ブロックが破壊された後、新しいバッディングブロックを設置する役割です。

1. <ItemLink id="import_bus" />がインターフェースからバッディングブロックを[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ取り込みます
2. サブネット内の唯一のストレージである<ItemLink id="formation_plane" />がそれを設置します

### メインネットワーク側：

* <ItemLink id="storage_bus" />はメインネットワーク（および[チャージャー自動化](charger-automation.md)）がサートスクリスタルへアクセスできるようにします。高い[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)により、メインストレージより先にバレルへ戻されます
* <ItemLink id="interface" />はサブネットにバッディングブロックを供給し、またサートスブロックブレーカーから戻ってきたブロックを受け取ります。さらに<ItemLink id="crafting_card" />により、メインネットワークの[自動クラフト](../ae2-mechanics/autocrafting.md)から新規バッディングブロックを要求できます
