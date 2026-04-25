---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: エネルギー
  icon: energy_cell
---

# エネルギー

あなたのネットワークは動作のためにエネルギーを必要とします。ネットワークにはエネルギープールがあり、そこから[デバイス](../ae2-mechanics/devices.md)が直接エネルギーを引き出します。また
<ItemLink id="vibration_chamber" />、<ItemLink id="energy_acceptor" />（および <ItemLink id="controller" />）がエネルギーを追加します。ネットワークのエネルギー統計は、どこでも <ItemLink id="network_tool" /> を使って右クリックするか、またはコントローラーがある場合はそれを右クリックすることで確認できます。このネットワーク全体でのストレージと分配により、エネルギー転送速度の制限は存在せず、デバイスは任意に高い量のエネルギーを引き出すことができ、エネルギー受容器も実質的に無制限の速度で受け入れることができます（制限はエネルギー貯蔵量のみです）。

## エネルギー受容

<Row>
  <BlockImage id="energy_acceptor" scale="4" />

  <GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
  </GameScene>

  <BlockImage id="controller" p:state="online" scale="4" />

  <BlockImage id="vibration_chamber" p:active="true" scale="4" />

  <BlockImage id="crystal_resonance_generator" scale="4" />
</Row>

AE2は内部的にForge Energy（Forge環境）やTechReborn Energy（Fabric環境）を使用しません。その代わりに、それらを独自の単位であるAEに変換します。この変換は一方向です。エネルギーは<ItemLink id="energy_acceptor" />や<ItemLink id="controller" />によって変換されますが、コントローラーの面は[チャンネル](../ae2-mechanics/channels.md)のためにより有効に使用されます。また、<ItemLink id="vibration_chamber" />によって生成したり、<ItemLink id="crystal_resonance_generator" />を使って受動的に生成することもできますが、AE2は他のエネルギー生成が優れたテック系MODと併用されることを前提に設計されています。

つまり、AE2ネットワークは基地のエネルギー配線インフラを設計する際には、単一の大きなマルチブロック機械として考えるのが最適です。

Forge EnergyおよびTechReborn Energyの変換比率は以下の通りです：

*   2 FE = 1 AE（Forge）
*   1 E  = 2 AE（Fabric）

## エネルギー貯蔵

<Row>
  <BlockImage id="energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="4" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="4" />
</Row>

比較的明らかな理由により、ネットワークは1ゲームティックあたりに貯蔵できる量以上のエネルギーを吸収したり消費したりすることはできません。もしネットワークの最大ストレージが800 AEしかない場合、[デバイス](../ae2-mechanics/devices.md)がエネルギーを要求しても最大800 AEまでしか使用できず（ストレージが満タンである場合）、エネルギー受容器もネットワークが空である場合には最大800 AEまでしか注入できません。

これはよくある奇妙な挙動の原因です。例えば、小さなネットワーク（エネルギー受容器、ドライブ、ターミナル、いくつかのデバイスのみ）を作り、インベントリいっぱいの丸石をネットワークに一気に投入しようとすると、その大量投入は1ゲームティックでネットワークのストレージを超えるエネルギーを必要とするため、すべての丸石は一度に処理されず、ネットワークがエネルギー不足になり、その結果再起動します。

**これはエネルギーセルの追加によって解決できます。**

ネットワークには、ケーブル・機械・パーツ1つあたり25 AEの内部エネルギーバッファがあります。

<ItemLink id="controller" />は内部に少量のエネルギーを保持でき、8,000 AEを蓄えます。

<ItemLink id="energy_cell" />は200k AEを蓄えることができ、ほとんどの用途では1つあれば十分で、通常のネットワーク利用における電力スパイクを問題なく処理できます。

<ItemLink id="dense_energy_cell" />は1.6M AEを蓄えることができ、ネットワークを蓄積電力のみで運用したい場合や、[空間ストレージ](spatial-io.md)の大規模セットアップによる巨大な瞬間的エネルギー消費を処理するためのものです。

<ItemLink id="creative_energy_cell" />はクリエイティブ用アイテムでテスト用です。無限のパワー（UNLIMITED POWAHHHHとかそんな感じ）を提供します。
