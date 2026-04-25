---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: コントローラー
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# コントローラー

<BlockImage id="controller" p:state="online" scale="8" />

コントローラーは[MEネットワーク](../ae2-mechanics/me-network-connections.md)のルーティングハブです。
これがない場合、ネットワークは「アドホック」となり、[デバイス](../ae2-mechanics/devices.md)を最大8チャンネルまでしか接続できません。

1つの[MEネットワーク](../ae2-mechanics/me-network-connections.md)に2つのコントローラーを設置することはできません。

コントローラーは各面で32の[チャンネル](../ae2-mechanics/channels.md)を提供します。

コントローラーは機能するために1ブロックあたり6 AE/tを必要とします。各コントローラーブロックは8000 AEを蓄えることができるため、大規模なネットワークでは追加のエネルギー貯蔵が必要になる場合があります。[エネルギー](../ae2-mechanics/energy.md)を参照してください。

マルチブロックコントローラーは比較的自由な形状で構築できます。

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

ただし、いくつかのルールに従う必要があります：

1.  [MEネットワーク](../ae2-mechanics/me-network-connections.md)上のすべてのコントローラーブロックは接続されている必要があります。そうでない場合、ブロックは赤くなります。
2.  コントローラーのサイズは7x7x7以内である必要があります。それを超えると赤くなります。
3.  コントローラーは1つの軸で隣接するブロックを最大2つまで持つことができます。このルールに違反すると、ブロックは無効化され赤くなります。

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

すべてのルールが守られ、電力が供給されている限り、コントローラーは光り、色が循環します。

コントローラーを右クリックすると、<ItemLink id="network_tool" />と同じGUIが表示されます。

## レシピ

<RecipeFor id="controller" />
