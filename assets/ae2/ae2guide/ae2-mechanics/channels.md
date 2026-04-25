---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: チャンネル
  icon: controller
---

# チャンネル

Applied Energistics 2の[MEネットワーク](me-network-connections.md)は、ネットワーク化されたストレージやその他のネットワークサービスを使用する[デバイス](../ae2-mechanics/devices.md)を動作させるためにチャンネルを必要とします。チャンネルは、あなたのデバイスに接続するUSBケーブルのようなものだと考えてください。コンピュータにはUSBポート数の制限があり、同時に接続できるデバイス数にも限りがあります。ほとんどの機械、フルブロック型デバイス、標準ケーブルは最大8チャンネルまでしか通せません。これらは「8本のチャンネル線の束」と考えることができます。ただし、[密度ケーブル](../items-blocks-machines/cables.md#dense-cable)は最大32チャンネルまで対応できます。32チャンネルを扱えるのは他に<ItemLink id="me_p2p_tunnel" />と[クアンタムネットワークブリッジ](../items-blocks-machines/quantum_bridge.md)のみです。デバイスがチャンネルを使用するたびに、その束から「USB線」が1本抜かれるイメージで、その線はそれ以降の接続には使えなくなります。

<GameScene zoom="7" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_demonstration_1.snbt" />

  <LineAnnotation color="#33ff33" from="1 .4 .7" to="2.4 .4 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .7" to="2.4 .6 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .6" to="2.6 .4 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.4 .6 .7" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .4 .7" to="2.4 .4 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .6 .6" to="2.6 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 .6" to="2.6 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.1 .6 1.5" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 1.5" to="2.9 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.6 .6 1.5" to="2.6 .9 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .1 1.5" to="2.4 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .4" to="3.5 .6 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="3.5 .6 .4" to="3.5 .9 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="3.5 .1 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .3" to="1.5 .6 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1.5 .6 .3" to="1.5 .9 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1.5 .1 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#ff3333" from="3.5 .5 .5" to="5.5 .5 .5" alwaysOnTop={true}>
  すべての8チャンネルが使用済みのため、ドライブにはチャンネルが供給されません。
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        すべての8チャンネルが使用済みのため、ドライブにはチャンネルが供給されません。
  </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

チャンネルの使用状況や経路を確認する簡単な方法として、[スマートケーブル](../items-blocks-machines/cables.md)を使用することができます。これにより、ケーブル上にチャンネルの流れと使用状況が表示されます。

チャンネルは通過するノードごとに1⁄128 ae/tを消費します。そのため、8デバイス・96ノードを超えるネットワークに<ItemLink id="controller" />を追加すると、チャネルの割り当て方式が変わることで逆に消費電力が減る場合があります。

重要な点として、**チャンネルとケーブルの色は無関係**です。ケーブルの色は接続を防ぐだけであり、チャンネルには影響しません。

## チャンネルルーティング

<ItemLink id="controller" />を使用する場合、チャンネルは3段階でルーティングされます。まず機械間の最短経路で通常ケーブル（ガラス、カバー、スマート）へ到達します。次にその通常ケーブル内で最短経路を通り密度ケーブルへ向かいます。最後に密度ケーブルを通ってコントローラーへ到達します。最短経路がすでに上限に達している場合、一部のデバイスはチャンネルを受け取れません。意図した経路を作るために、ケーブルアンカーやチューブ、色付きケーブルを活用してください。

例えばこのケースでは、十分な容量があるにもかかわらず最短経路に集中してしまい、一部ケーブルが過負荷になっています。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 3.6" to="1.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.4 0.5 3.6" to="1.4 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 1.6" to="0.6 .5 1.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 1.6" to="0.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 3.4" to="1.4 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 3.4" to="1.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <BoxAnnotation color="#dddddd" min="1.2 0.2 3.2" max="1.8 0.8 3.8" alwaysOnTop={true} thickness="0.05">
        ここに8チャンネル以上が流れ込もうとしているため、一部が遮断されています。
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

この問題は、チャンネルの経路をより制約することで解決できます。ネットワークはツリー状（またはブッシュ状）に設計すべきです。ループや曖昧な経路は避けてください。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## アドホックネットワーク

<ItemLink id="controller" />が存在しないネットワークはアドホックネットワークと見なされ、最大8チャンネル分のデバイスをサポートできます。
8デバイスを超えるとネットワーク内のチャンネル使用デバイスは停止し、不要なデバイスを削除するか、<ItemLink id="controller" />を追加する必要があります。

コントローラー管理下のネットワークとは異なり、アドホックネットワーク上の[スマートケーブル](../items-blocks-machines/cables.md)は、特定のケーブルを流れるチャンネル数ではなく、ネットワーク全体で使用されているチャンネル数を表示します。

アドホックネットワークでは各デバイスはネットワーク全体で1チャンネルを使用します。これは、コントローラーが最短経路に基づいてチャンネルを割り当てる方式とは大きく異なります。

## 設計

前述の[チャンネルルーティング](channels.md#channel-routing)でも説明した通り、ネットワークはツリー構造で設計するのが最適です。コントローラーから密度ケーブルが枝分かれし、そこから通常ケーブルが伸び、各通常ケーブル上にデバイスが8個以下のクラスターで配置される形が理想です。

以下は避けるべき構成例です：

チャンネルの流れに沿って見ると：

1. コントローラーから右に出た直後、ドライブが通常ケーブルとして扱われるため8チャンネル制限によりボトルネックが発生します。ただしスマートケーブルを使っていないため、使用状況は見えません。残り8チャンネル。
2. ドライブが1チャンネル使用。
残り7チャンネル。
3. 2チャンネルがターミナルへ。
残り5チャンネル。
4. さらに右へ進み、インターフェースが1チャンネル使用。
残り4チャンネル。
5. パターンプロバイダーへ1チャンネル。
残り3チャンネル。
6. さらに右へ進み、インポートバスが1チャンネル使用。
残り2チャンネル。
7. アセンブラーへ供給するパターンプロバイダー群は2チャンネルしか受け取れず、結果として2つのプロバイダーはチャンネルを取得できません。

最終的な問題は、チャンネルを適切に分散できておらず、ボトルネック構造になっている点です。

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/bad_network_structure.snbt" />

<LineAnnotation color="#33ff33" from="6.5 .5 1.5" to="6 .5 1.5" alwaysOnTop={true} thickness="0.4">
  32チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="6 .5 1.5" to="5.5 .5 1.5" alwaysOnTop={true} thickness="0.2">
  8チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 1.5 1.5" alwaysOnTop={true} thickness="0.1">
  2チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 1.5 1.5" to="5.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 2.5 1.5" to="5.5 2.5 1.1" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="4.5 .5 1.5" alwaysOnTop={true} thickness="0.158">
  5チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 1.5 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="3.5 .5 1.5" alwaysOnTop={true} thickness="0.122">
  3チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="3.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 2.5 1.5" to="3.7 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="1.5 .5 1.5" alwaysOnTop={true} thickness="0.1">
  2チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="1.5 0.3 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="0.5 0.5 1.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#33ff33" from="0.5 0.5 1.5" to="0.5 0.5 0.5" alwaysOnTop={true} thickness="0.071">
  1チャンネル
</LineAnnotation>

<LineAnnotation color="#ff3333" from="0.5 1.5 1.5" to="0.5 1.3 1.5" alwaysOnTop={true} thickness="0.071">
  チャンネルなし
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  チャンネルなし
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

良い例：

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

  <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        パターンプロバイダーが8個単位で分割されている点に注目してください。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        2本の通常ケーブルが合流する場合は密度ケーブルが必要です。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        ケーブル色で接続を防いでいます。
  </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## チャンネルモード

AE2 10.0.0（Minecraft 1.18向け）では、世界におけるAE2チャンネルの挙動を変更するための新しいオプションが導入されています。
この設定は一般設定の`channels`項目で制御されており、さらに管理者向けにゲーム内からモードや設定を変更できる新しいコマンドも追加されています。

コマンドは以下の通りです：
`/ae2 channelmode <mode>` でモード変更、
`/ae2 channelmode` で現在のモード表示ができます。

ゲーム内でモードを変更すると、既存のすべてのグリッドは即座に再起動し、新しいモードが適用されます。

この機能はMinecraft 1.12に存在したオプションを復活・改良したもので、完全にメカニクスを削除することなく、よりカジュアルなプレイを望むプレイヤー向けの選択肢を提供します。

以下の表は、設定ファイルおよびコマンドで利用可能なモード一覧です。

| 設定 | 説明 |
| ---- | ---- |
| `default`  | 標準モード。ケーブルおよびアドホックネットワークのチャンネル容量は本サイト全体で説明されている通り |
| `x2`       | すべてのチャンネル容量が2倍（通常ケーブル16、密度ケーブル64、アドホック16チャンネル対応） |
| `x3`       | すべてのチャンネル容量が3倍（通常ケーブル24、密度ケーブル92、アドホック24チャンネル対応） |
| `x4`       | すべてのチャンネル容量が4倍（通常ケーブル32、密度ケーブル128、アドホック32チャンネル対応） |
| `infinite` | チャンネル制限を完全に撤廃。コントローラーはグリッドの消費電力を大幅に削減するのみ。スマートケーブルは「オフ（0チャンネル）」か「オン（1以上）」のみを表示するようになる |
