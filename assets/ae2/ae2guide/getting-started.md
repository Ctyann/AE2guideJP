---
navigation:
  title: はじめに (1.20+)
  position: 10
---

<div class="notification is-info">
  以下の情報は、Minecraft 1.20以降のApplied Energistics 2にのみ適用されます。
</div>

# はじめに

## 初期素材の入手

<GameScene zoom="4" background="transparent">
  <ImportStructure src="assets/assemblies/meteor_interior.snbt" />
</GameScene>

Applied Energistics 2を始めるには、まず[隕石](ae2-mechanics/meteorites.md)を見つける必要があります。これらは比較的一般的で、地形に大きな穴を残す傾向があるため、旅の途中で見かけたことがあるかもしれません。
もし見つけていない場合は、<ItemLink id="meteorite_compass" />をクラフトすると、最寄りの<ItemLink id="mysterious_cube" />の方向を指し示してくれます。

隕石を見つけたら、その中心部を掘り進めてください。そこには、様々な種類のケルタスクォーツの塊、ケルタスクォーツバッド、[芽生えたケルタスブロック](items-blocks-machines/budding_certus.md)、そして中心にはミステリアスキューブが見つかります。

ケルタスクォーツの塊や見つけたケルタスクォーツブロックを採掘してください。また、芽生えたケルタスブロックもシルクタッチなしで採掘できますが、1段階劣化します。

完璧な芽生えたケルタスを破壊しないでください。シルクタッチを使っても劣化して欠陥のある芽生えたケルタスになり、元に戻すことはできません。

また、隕石の中心にあるミステリアスキューブを採掘して、4つのインスクライバープレスを手に入れましょう。

## ケルタスクォーツの成長

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_1.snbt" />
</GameScene>

ケルタスクォーツバッドは、[芽生えたケルタスブロック](items-blocks-machines/budding_certus.md)からアメジストのように芽を出します。成長が完了していないバッドを破壊すると、<ItemLink id="certus_quartz_dust" />が1つドロップし、フォーチュンの影響を受けません。完全に成長した塊を破壊すると、<ItemLink id="certus_quartz_crystal" />が4つドロップし、フォーチュンでその数が増加します。

芽生えたケルタスブロックには、完璧な、傷ついた、欠けた、壊れかけの4つの段階があります。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_blocks.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

バッドが成長するたびに、芽生えたブロックは1段階劣化する可能性があり、最終的には普通のケルタスクォーツブロックになります。これらは修復可能であり、新しい芽生えたブロックを作成するには、芽生えたブロック（またはケルタスクォーツブロック）を<ItemLink id="charged_certus_quartz_crystal" />と一緒に水に投げ入れます。

<RecipeFor id="damaged_budding_quartz" />

完璧な芽生えたケルタスブロックは劣化せず、無限にケルタスを生成します。ただし、クラフトやシルクタッチで移動させることはできません。（[空間ストレージ](ae2-mechanics/spatial-io.md)を使用すれば移動可能です）

ケルタスクォーツバッドは非常にゆっくりと成長しますが、<ItemLink id="growth_accelerator" />を隣接して配置することで、このプロセスを大幅に加速できます。これを最初の優先事項としていくつか作成してください。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

もし<ItemLink id="energy_acceptor" />や<ItemLink id="vibration_chamber" />を作るのに十分なクォーツがない場合は、<ItemLink id="crank" />を作成し、アクセラレータの端に取り付けることができます。

ケルタスを自動で収穫する方法は[こちら](example-setups/simple-certus-farm.md)で説明されています。

## フルイックスについての簡単な説明

もう1つ必要な素材はフルイックスで、これは成長アクセラレータを作る際にすでに出会っています。フルイックスは、チャージドケルタス、レッドストーン、ネザークォーツを水に投げ入れることで作成されます。これを自動化する方法は「読者への課題」として残されています。

<ItemLink id="charger" />は<ItemLink id="charged_certus_quartz_crystal" />を生成するために必要です。まだ作成していない場合は作成してください。

## プロセッサの作成

隕石を略奪する際に、ミステリアスキューブを破壊して4つの「プレス」を見つけたはずです。これらは<ItemLink id="inscriber" />で3種類のプロセッサを作成するために使用されます。

<ItemGrid>
  <ItemIcon id="silicon_press" />

  <ItemIcon id="logic_processor_press" />

  <ItemIcon id="calculation_processor_press" />

  <ItemIcon id="engineering_processor_press" />
</ItemGrid>

インスクライバーは、バニラのかまどのように側面にスロットがある機械です。上部または下部から挿入すると、上部または下部のスロットにアイテムが配置され、側面または背面から挿入すると中央のスロットに配置されます。結果は側面または背面から取り出すことができます。

ホッパーを使用した自動化を容易にするために（おそらくパイプのスパゲッティを減らすために）、インスクライバーは<ItemLink id="certus_quartz_wrench" />で回転させることができます。

次のステップで非常に基本的なMEシステムを作成する準備として、各タイプのプロセッサをいくつか作成してください。プロセッサの生産を自動化する方法は「[読者への課題](example-setups/processor-automation.md)」として残されています。

## マターエネルギーテクノロジー: MEネットワークとストレージ

### MEストレージとは？

これは「エムイー」と発音し、マターエネルギーを意味します。

マターエネルギーはApplied Energistics 2の主要な要素で、マッドサイエンティスト版のマルチブロックチェストのようなもので、ストレージ状況を一変させる可能性があります。MEはMinecraftの他のストレージシステムとは非常に異なり、慣れるのに少し工夫が必要かもしれませんが、一度始めると膨大な量のストレージを小さなスペースに収めたり、複数のアクセス端末を使用したりすることが可能になります。

### 始めるために知っておくべきこと

まず、MEは[ストレージセル](items-blocks-machines/storage_cells.md)と呼ばれるアイテムの中にアイテムを保存します。ストレージセルには、容量が増加する5つの段階があります。ストレージセルを使用するには、<ItemLink id="chest" />または<ItemLink id="drive" />のいずれかに配置する必要があります。

<ItemLink id="chest" />は、セルを中に配置するとその内容をすぐに表示し、<ItemLink id="minecraft:chest" />のようにアイテムを追加および削除できます。ただし、アイテムは<ItemLink id="chest" />自体ではなく、ストレージセルに保存されます。

<ItemLink id="chest" />は非常に状況に応じたもので、実用性が限られています。AE2を本当に活用するには、[MEネットワーク](ae2-mechanics/me-network-connections.md)を設定する必要があります。

## 初めてのMEシステム

Applied Energistics 2の基本的な素材と機械がすべて揃ったら、最初のME（マターエネルギー）システムを作成できます。これは非常に基本的なもので、自動クラフトやロジスティクスはなく、シンプルで検索可能なストレージだけです。

<GameScene zoom="6" interactive={true}>
<ImportStructure src="assets/assemblies/tiny_me_system.snbt" />

</GameScene>

* 必要な材料リスト:
    * 1x <ItemLink id="drive" />
    * 1x <ItemLink id="terminal" /> または <ItemLink id="crafting_terminal" />
    * 1x <ItemLink id="energy_acceptor" />
    * [ケーブル](items-blocks-machines/cables.md)をいくつか（ガラス、カバー付き、またはスマートだが、密ではないもの）
    * [ストレージセル](items-blocks-machines/storage_cells.md)をいくつか（4kバリエーションを推奨、容量とタイプの良いバランスのため。4kと1kを混ぜて[パーティション](items-blocks-machines/cell_workbench.md)する方が効率的ですが、ここではその複雑さには触れません）
---
1. ドライブを設置します。
2. エネルギーアクセプター（およびAE2の[デバイス](ae2-mechanics/devices.md)のいくつか）は、キューブとフラットの2つのモードがあります。クラフトグリッドで切り替えることができます。エネルギーアクセプターがキューブの場合は、ドライブの隣に設置します。フラットな場合は、ドライブにケーブルを接続し、その上にアクセプターを設置します。
3. お気に入りのエネルギー生成モッドからケーブル/パイプ/コンジットを使用してエネルギーをエネルギーアクセプターに流します。
4. ドライブの上（または目の高さ）にケーブルを設置し、その上に端末またはクラフティング端末を設置します。
5. ストレージセルをドライブに挿入します。
6. 利益を得る。
7. 端末の設定をいじる。
8. 究極の力と能力を享受する。
9. このネットワークが全体的にはかなり小さいことに気づく。

### ネットワークの拡張

基本的なストレージとそのストレージへのアクセスができるようになりました。良いスタートですが、おそらくいくつかの処理を自動化したいと思うでしょう。

良い例として、かまどの上に<ItemLink id="export_bus" />を設置して鉱石をネットワークから投入し、かまどの下に<ItemLink id="import_bus" />を設置して焼成された鉱石をネットワークに取り込むことが挙げられます。

<ItemLink id="export_bus" />はネットワークからアイテムを取り出して接続されたインベントリに投入し、<ItemLink id="import_bus" />は接続されたインベントリからアイテムを取り込んでネットワークに追加します。

### 制限を克服する

この時点で、[デバイス](ae2-mechanics/devices.md)が8つ程度に近づいているかもしれません。9つ目のデバイスに達すると、[チャンネル](ae2-mechanics/channels.md)を管理する必要が出てきます。多くのデバイス（すべてではありません）が機能するためにチャンネルを必要とします。

デフォルトでは、ネットワークは8つのチャンネルをサポートできます。この制限を超えると、ネットワークに<ItemLink id="controller" />を追加する必要があります。これにより、ネットワークを大幅に拡張できます。[スマートケーブル](items-blocks-machines/cables.md)を使用すると、ネットワーク内のチャンネルのルーティングを確認できます。チャンネルの動作を学ぶために、または大量のレッドストーンやグロウストーンがある場合に、これらを広く使用してください。
