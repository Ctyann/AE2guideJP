---
navigation:
  parent: example-setups/example-setups-index.md
  title: バケツ空化装置
  icon: minecraft:bucket
---

# バケツ空化装置

[バケツ充填装置](bucket-filler.md)も参照してください。

この構成は<ItemLink id="pattern_provider" />を使用するため、[自動クラフト](../ae2-mechanics/autocrafting.md)システムへの統合を前提としています。

ゲーム内では、液体そのものが欲しいのに「バケツ入りでしか作れない」という状況が発生することがあります。Thermal ExpansionのFluid Transposerのように便利に処理できるMODもありますが、常にそれがあるとは限りません。そこで役立つのが、バニラMinecraftのやや不便な方法である<ItemLink id="minecraft:dispenser" />です。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/bucket_emptier.snbt" />

<BoxAnnotation color="#dddddd" min="2 1 0" max="3 2 1">
        (1) パターンプロバイダ：クラフトを「レッドストーン信号でロック」に設定し、ブロッキングモードを有効化。対応するプロセッシングパターンを使用

        <Row>
        ![Fill Pattern](../assets/diagrams/water_empty_pattern_small.png)
        ![Fill Pattern](../assets/diagrams/lava_empty_pattern_small.png)
        </Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2.1 2 0.1" max="2.9 2.2 0.9">
        (2) インターフェース：デフォルト設定
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.1 2 1.1" max="3.9 2.2 1.9">
        (3) ストレージバス #1：デフォルト設定
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="4.05 1.05 0.8" max="4.95 1.95 1">
        (4) アニヒレーションプレーン：GUIなし（設定不可）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.2 1.2 0.8" max="3.8 1.8 1">
        (5) インポートバス：バケツにフィルタリング
        <ItemImage id="minecraft:bucket" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1.1 0.1" max="3.2 1.9 0.9">
        (6) ストレージバス #2：デフォルト設定
  </BoxAnnotation>

<DiamondAnnotation pos="0 1.5 0.5" color="#00ff00">
        メインネットワークへ接続
    </DiamondAnnotation>

  <IsometricCamera yaw="225" pitch="45" />
</GameScene>

## 構成

* <ItemLink id="pattern_provider" />（1）は「レッドストーン信号でロック」に設定され、ブロッキングモードが有効。対応する<ItemLink id="processing_pattern" />を使用
* <ItemLink id="interface" />（2）はデフォルト設定
* 最初の<ItemLink id="storage_bus" />（3）はデフォルト設定
* <ItemLink id="annihilation_plane" />（4）はGUIなしで設定不可
* <ItemLink id="import_bus" />（5）はバケツにフィルタリング
  <ItemImage id="minecraft:bucket" scale="2" />
* 2つ目の<ItemLink id="storage_bus" />（6）はデフォルト設定

## 動作原理

1. <ItemLink id="pattern_provider" />が材料を<ItemLink id="interface" />へ送信します
   （実際には最適化により、ストレージバス経由でプロバイダの拡張として直接渡されるため、インターフェースを経由しない場合があります）
2. [パイプサブネット](pipe-subnet.md#providing-to-multiple-places)の仕組みにより、バケツは<ItemLink id="minecraft:dispenser" />へ到達します
3. <ItemLink id="minecraft:comparator" />がディスペンサー内のバケツを検出し、それによりディスペンサーを作動させると同時にパターンプロバイダをロックします
4. ディスペンサーがバケツから液体を排出し、空のバケツが残ります
5. <ItemLink id="import_bus" />がディスペンサーから空のバケツを回収し、<ItemLink id="storage_bus" />経由でメインネットワークへ戻します
6. コンパレータがディスペンサーが空であることを検出し、プロバイダのロックを解除します
