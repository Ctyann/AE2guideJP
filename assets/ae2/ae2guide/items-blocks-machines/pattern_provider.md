---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: パターンプロバイダー
  icon: pattern_provider
  position: 210
categories:
- devices
item_ids:
- ae2:pattern_provider
- ae2:cable_pattern_provider
---

# パターンプロバイダー

<Row gap="20">
<BlockImage id="pattern_provider" scale="8" />
<BlockImage id="pattern_provider" p:push_direction="up" scale="8" />
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

パターンプロバイダーは、[自動クラフト](../ae2-mechanics/autocrafting.md)システムがワールドとやり取りするための主要な手段です。[パターン](patterns.md)に従って
隣接するインベントリへ材料を押し出し、アイテムを挿入することでネットワークへ取り込むこともできます。多くの場合、
<ItemLink id="import_bus" />を使って機械の出力をネットワークへ取り込む代わりに、機械の出力を近くのパターンプロバイダー
(多くの場合、材料を押し出したそのパターンプロバイダー)へ戻すことで、チャンネルを1つ節約できます。

注目すべき点として、クラフトCPU内の[クラフトストレージ](crafting_cpu_multiblock.md#crafting-storage)から直接材料を押し出すため、
実際にはインベントリ内に材料を保持しません。そのため、そこからパイプで引き出すことはできません。プロバイダーから別のインベントリ
(樽など)へ押し出し、そこからパイプで搬出する必要があります。

また、プロバイダーはすべての材料を一度に押し出す必要があり、半分のバッチだけを押し出すことはできません。これは活用できます。

パターンプロバイダーは、[サブネット](../ae2-mechanics/subnetworks.md)上のインターフェースと特別な相互作用を持っています。インターフェースが未変更
(リクエストスロットに何も入っていない)の場合、プロバイダーはインターフェースを完全にスキップし、そのサブネットの[ストレージ](../ae2-mechanics/import-export-storage.md)へ
直接押し出します。これによりインターフェースを介さず、レシピのバッチで埋めることもなく、さらに重要なこととして、機械に空きができるまで次の
バッチを挿入しません。これはブロッキングモードでも正しく動作し、プロバイダーはインターフェースのスロットではなく、機械内の材料スロットを監視します。

たとえば、この構成では製錬するアイテムと燃料の両方を、かまどの対応するスロットへ直接押し込みます。
これを使うことで、機械の複数面、あるいは複数の機械へパターン供給できます。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) パターンプロバイダー: ケルタスクォーツレンチを使用した方向指定バリアント。対応する加工パターンを設定。

        ![Iron Pattern](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) インターフェース: デフォルト設定。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) ストレージバス #1: 石炭でフィルター。
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) ストレージバス #2: インバーターカードを使用して石炭をブラックリスト指定。
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

これは複数の機械へ供給する一般的な例です

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        インターフェース (フルブロックではなくフラットである必要があります)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        ストレージバス
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        パターン供給したい場所
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

同一パターンを持つ複数のパターンプロバイダーにも対応しており、並列動作します。

パターンプロバイダーは各面へ順番にバッチを割り振ろうとするため、接続されたすべての機械を並列利用します。

## バリアント

パターンプロバイダーには、通常、方向指定、フラット/[サブパーツ](../ae2-mechanics/cable-subparts.md)の3種類があります。これにより、どの面へ材料を
押し出すか、どの面からアイテムを受け取るか、どの面にネットワーク接続を提供するかが変化します。

* Normal pattern providers push ingredients to all sides, receive inputs from all sides, and, like most AE2 machines, act
    like a cable providing [network connections](../ae2-mechanics/me-network-connections.md) to all sides.

* Directional pattern providers are made by using a <ItemLink id="certus_quartz_wrench" /> on a normal pattern provider to change its
    direction. They only push ingredients to the selected side, receive inputs from all sides, and specifically don't provide a
  [network connection](../ae2-mechanics/me-network-connections.md) on the selected side. This allows them to push to AE2 machines without connecting networks, if you want to make a subnetwork.

* Flat pattern providers are [cable subparts](../ae2-mechanics/cable-subparts.md), and so multiple can be placed on the same cable, allowing for compact setups.
    They act similar to the selected side on a directional pattern provider, providing patterns, receiving inputs, and **not**
    providing a [network connection](../ae2-mechanics/me-network-connections.md) on their face.

パターンプロバイダーはクラフトグリッド内で通常版とフラット版を切り替えできます。

## 設定

パターンプロバイダーにはさまざまなモードがあります:

*   **ブロッキングモード** は、機械内にすでに材料がある場合、新しい材料バッチを押し出さないようにします。
*   **クラフトロック** は、さまざまなレッドストーン条件下、または前回のクラフト結果がその特定の
    パターンプロバイダーへ挿入されるまで、プロバイダーをロックできます。
*   プロバイダーを<ItemLink id="pattern_access_terminal" />上に表示または非表示にできます。

## 優先度

優先度はGUI右上のレンチをクリックして設定できます。同じアイテムに対する複数の[パターン](patterns.md)がある場合、
ネットワークに高優先度パターン用の材料がない場合を除き、優先度の高いプロバイダー内のパターンが優先されます。

## よくある誤解

なぜか多くの人がこれをやります。理由はわかりませんが、役立つようここに書いておきます。(おそらく、
<ItemLink id="export_bus" />だけがネットワークから物を出す方法だと思い、パターンプロバイダーも
物を出力できることを知らないのかもしれません)

これは期待している動作にはなりません。[ケーブル](cables.md)で説明したように、ケーブルはアイテムパイプではなく、内部インベントリもありません。
プロバイダーはそこへ押し出すことはできません。

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_1.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        ブラストファーネスではない
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

プロバイダーには押し出し先が存在しないため、
機能しません。ここで行っているのは、<ItemLink id="export_bus" />をネットワークへ接続するケーブルとして
振る舞っているだけです。

また、プロバイダーが<ItemLink id="export_bus" />に何を出力するか指示することもありません。エクスポートバスは
フィルターに入れたものをそのまま出力するだけです。

つまり実際にはこうなっています:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_2.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        ブラストファーネスではない
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

実際に作りたいのはおそらくこちらで、パターンプロバイダーがパターン内容を隣接する機械へ
出力できる構成です:

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/assemblies/provider_misconception_3.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 3" max="2 1 4">
        ブラストファーネスではない
  </BoxAnnotation>

  <IsometricCamera yaw="95" pitch="5" />
</GameScene>

## 分子組立機での使用

<ItemLink id="molecular_assembler" />は、基本的には他の機械と同じです。内部にアイテムを挿入できるインベントリがあり、
その中身に対して処理を行い、その後多くの機械と同様に結果を隣接インベントリへ押し出します。そのため、
他の機械と同様にプロバイダーと組み合わせて使いますが、1つだけ追加点があります。

組立機は、直接挿入された<ItemLink id="crafting_pattern" />、<ItemLink id="smithing_table_pattern" />、<ItemLink id="stonecutting_pattern" />
から目的のパターンを取得できます。
これは組立ラインでは便利ですが、クラフトレシピごとに専用の組立機が必要になるのは面倒です。

そのため、パターンプロバイダーは組立機に対して特別な機能を持ち、材料と一緒にパターンデータも送信できます。
これにより、パターンプロバイダーの隣に組立機を置くだけで、プロバイダーはその組立機を使ってすべての
クラフト、鍛冶、石切りパターンを処理できます。

本当にこれだけです。パターンをプロバイダーに入れるだけです:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

*この例にはちょうど8個のプロバイダーがあります。これは単一の組立機、プロバイダー、または
非高密度ケーブルを通せるチャンネル数の上限です。*

## レシピ

<RecipeFor id="pattern_provider" />

<RecipeFor id="cable_pattern_provider" />
