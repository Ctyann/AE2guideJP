---
navigation:
  parent: example-setups/example-setups-index.md
  title: 自動調整式丸石生成機
  icon: minecraft:cobblestone
---

# 自動調整式丸石生成機

丸石生成機の自動化は簡単で、標準的なバニラの手動丸石生成機に向けて<ItemLink id="annihilation_plane" />を設置するだけです。
しかしこの方法だけでは、最終的にネットワークが丸石で埋まってしまうため、適切な制御が必要になります。

ME消滅プレーンの挙動上（<ItemLink id="import_bus" />のように動作するため）、単純に<ItemLink id="level_emitter" />を<ItemLink id="export_bus" />に向け、<ItemLink id="redstone_card" />を使うだけでは制御できません（ストレージを挟まずにインポートからエクスポートへ直接つなぐことができないためです）。そのため、もう少し回りくどい方法が必要になります。

<ItemLink id="toggle_bus" />はレッドストーン信号によってネットワークの一部を接続・切断できますが、そのたびにネットワークが再起動してしまいます。
ただし簡単な回避策として、これを[サブネットワーク](../ae2-mechanics/subnetworks.md)上に配置すれば、そのサブネットだけを再起動させることができます。

そこで、<ItemLink id="annihilation_plane" />と<ItemLink id="storage_bus" />だけで構成された[サブネットワーク](../ae2-mechanics/subnetworks.md)を作り、それをメインネットワーク上の<ItemLink id="interface" />へ出力します。
toggle busは<ItemLink id="quartz_fiber" />を介してサブネットワークを接続・切断し、プレーンへの電力供給を遮断します。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/regulated_cobble_gen.snbt" />

<BoxAnnotation color="#dddddd" min="3 2 2" max="7 2.3 3">
        (1) ME消滅プレーン：GUIは存在しませんが、効率や耐久力のエンチャントで消費電力を削減できます
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 2 2" max="2.3 3 3">
        (2) MEストレージバス：デフォルト設定
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 2.3 2" max="2.7 2.7 2.3">
        (3) トグルバス：必ずサブネットワーク側に配置する必要があり、メインネットワーク側に置いてはいけません
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 3 2.3" max="2.7 3.3 2.7">
        (4) レベルエミッタ：丸石と必要数量を設定し、「指定量未満で信号出力」に設定
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 3" max="2 3 2">
        (5) MEインターフェース：デフォルト設定
  </BoxAnnotation>

<DiamondAnnotation pos="0 2.5 1.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

<DiamondAnnotation pos="5 1.5 3.5" color="#00ff00">
        水没した階段は水の流れを止め、溶岩が黒曜石になるのを防ぎます
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 構成

* <ItemLink id="annihilation_plane" />（1）：GUIはありませんが、効率・耐久力エンチャントで消費電力を削減可能
* <ItemLink id="storage_bus" />（2）：デフォルト設定
* <ItemLink id="toggle_bus" />（3）：クォーツファイバーのメインネットワーク側ではなく、必ずサブネットワーク側に配置する必要があります。そうしないと切り替えのたびにメインネットワークが再起動します
* <ItemLink id="level_emitter" />（4）：対象アイテムと数量を設定し、「指定量未満で信号出力」に設定
* <ItemLink id="interface" />（5）：デフォルト設定

## 動作原理

1. 丸石生成機が丸石を生成する
2. <ItemLink id="annihilation_plane" />が丸石を破壊する
3. <ItemLink id="storage_bus" />が丸石を<ItemLink id="interface" />へ格納し、メインネットワークへ送信する
4. メインネットワーク内の丸石量が設定値を超えると、<ItemLink id="level_emitter" />が信号を停止し、<ItemLink id="toggle_bus" />をオフにする
5. これによりサブネットワークへの電力供給が遮断され、ME消滅プレーンの動作が停止する
