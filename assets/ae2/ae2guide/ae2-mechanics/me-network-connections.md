---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: ネットワーク接続
  icon: fluix_glass_cable
---

# ネットワーク接続

## 「ネットワーク」とは何か？

「ネットワーク」とは、[チャンネル](../ae2-mechanics/channels.md)を通してブロック同士が接続されることで構成される、[デバイス](../ae2-mechanics/devices.md)の集合のことです。これには[ケーブル](../items-blocks-machines/cables.md)やフルブロックの機械、そして[デバイス](../ae2-mechanics/devices.md)
（<ItemLink id="charger" />、<ItemLink id="interface" />、<ItemLink id="drive" />など）が含まれます。

技術的には、ケーブル1本だけでもそれはネットワークです。

## デバイス配置に関する補足

[デバイス](../ae2-mechanics/devices.md)の中には、特定のネットワーク機能を持つものがあります（例えば、<ItemLink id="interface" />が[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)への入出力を行う、<ItemLink id="level_emitter" />がネットワークストレージの内容を読み取る、<ItemLink id="drive" />がネットワークストレージとして機能するなど）。

これらにおいて重要なのは、**デバイスの物理的な位置は関係ない**ということです。

もう一度言います。**デバイスの物理的な位置は関係ありません。**

重要なのは、そのデバイスがネットワークに接続されているかどうか（そしてどのネットワークに接続されているか）だけです。

## ネットワーク接続

どの要素がネットワークに接続されているかを簡単に確認する方法として、<ItemLink id="network_tool" />があります。これはネットワーク上のすべてのコンポーネントを表示するため、見えるべきものが見えない、または見えるべきでないものが見える場合は問題があります。

例えば、これは2つの別々のネットワークです。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        ネットワーク1
  </BoxAnnotation>

<BoxAnnotation color="#5CA7CD" min="2 0 0" max="3 2 2">
        ネットワーク2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

これはまた別の2つのネットワークです。<ItemLink id="quartz_fiber" />は[エネルギー](../ae2-mechanics/energy.md)を共有しますが、ネットワーク接続は提供しません。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        ネットワーク1
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="1.3 0 0" max="3 2 2">
        ネットワーク2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

しかしこれは1つのネットワークであり、2つの別々のネットワークではありません。[クォンタムブリッジ](../items-blocks-machines/quantum_bridge.md)はワイヤレスの[デンスケーブル](../items-blocks-machines/cables.md#dense-cable)のように振る舞うため、両端は同一ネットワーク上にあります。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        すべて1つのネットワーク
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

これもまた1つのネットワークです。なぜなら[ケーブル](../items-blocks-machines/cables.md)の色はネットワーク接続には関係がなく、異なる色同士が接続されないという点だけが違いです。すべての色はフルクシ（または「無色」）ケーブルに接続できます。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        すべて1つのネットワーク
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## サブネットの文脈における接続

[サブネットワーク](../ae2-mechanics/subnetworks.md)はネットワーク接続（特に接続されていないこと）を利用して、どの[デバイス](../ae2-mechanics/devices.md)が他のデバイスへアクセスできるかを制限します。

サブネットとは本質的には、別のネットワークにすぎません。

例えば[自動鉱石フォーチュナー](../example-setups/ore-fortuner.md)を見てみると、ここには3つの別々のネットワークがあり、それぞれが特定の役割を持っています。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 2" max="3 1 3">
        ネットワーク1：パイプサブネットのように機能し、インポートバスがフォーメーションプレーン経由で鉱石ブロックを扱えるよう制限する
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="0 0 0" max="3 1 1">
        ネットワーク2：別のパイプサブネットとして機能し、アニヒレーションプレーンがフォーチュン後の鉱石をメインネットワークではなくバレルに格納するよう制限する。またメインネットワークのチャンネルを消費しない
  </BoxAnnotation>

  <BoxAnnotation color="#82CD5C" min="2 0 1" max="4 1 2">
        ネットワーク3：ストレージとクラフトをすべて管理するメインネットワーク。ここでは主に電力供給のみを行い、2つのサブネットとは*接続されていない*
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## P2Pの文脈における接続

[パラレル・トゥ・パラレル（P2P）トンネル](../items-blocks-machines/p2p_tunnels.md)の一部の種類は、アイテムや液体、レッドストーンではなく[チャンネル](channels.md)を運びますが、これは混乱の元になります。

トンネルが設置されているネットワークと、トンネルが運んでいるネットワークは無関係です。同じネットワークであることもできますが、通常は別ネットワークです。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_channels_network_connection.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1.98 2 1">
        ネットワーク1：運ばれている側（通常はメインネットワーク）
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="2.02 0 0" max="3.98 1 1">
        ネットワーク2：ME P2Pトンネルが動作しているネットワーク（通常メインではない）
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="4.02 0 0" max="6 1 1">
        ネットワーク1：運ばれている側（通常はメインネットワーク）
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 直感に反する接続

この場合は1つのネットワークです。なぜなら<ItemLink id="pattern_provider" />はフルブロックのデバイスとしてケーブルのように振る舞い、<ItemLink id="inscriber" />も同様の動作をするため、ネットワーク接続がそのまま通過するからです。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        すべて1つのネットワーク
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

これを防ぐには（[サブネットワーク](../ae2-mechanics/subnetworks.md)を使う多くの自動クラフト構成で有用）、<ItemLink id="certus_quartz_wrench" />で右クリックして方向性を持たせることで、その面からはチャンネルが通らなくなります。

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1.98 2 2">
        ネットワーク1
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="2.02 0 0" max="4 2 2">
        ネットワーク2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        ケーブルが接続されていないことに注目
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

他にも方向性のネットワーク接続を提供しないものとして、<ItemLink id="import_bus" />や<ItemLink id="storage_bus" />、<ItemLink id="cable_interface" />などの多くの[サブパート](../ae2-mechanics/cable-subparts.md)[デバイス](../ae2-mechanics/devices.md)があります。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
