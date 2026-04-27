---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: 空間入出力
  icon: spatial_storage_cell_2
---

# 空間入出力

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/spatial_storage_1x1x1.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="2 2 2">
        移動対象となる空間
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />

</GameScene>

空間入出力は、ワールド内の物理的な空間領域を切り取り、別の場所へ貼り付けるための機能です。これを使うことで<ItemLink id="flawless_budding_quartz" />を移動させたり、拠点内の部屋の内装を入れ替えて用途を切り替えたり、さらにはエンドポータルを移動させることさえ可能です。

これは、定義された領域を空間ストレージ次元内の同じサイズの領域と**交換（スワップ）** することで動作します。ピラミッド（パイロン）配列にあるものは空間ストレージ次元へ送られ、代わりに次元内の内容がパイロン配列へ戻されます。

つまり、次元間移動手段があれば（空間入出力自体でもテレポーターを作れますが、非常に複雑で扱いにくく、このガイドの範囲外です）、これらをカスタムサイズのコンパクトマシンやポケットディメンションのように扱うことができます。

# マルチブロック構成

空間入出力は動作するために特定の構造を必要とし、切り取り対象の空間を定義します。

すべてのコンポーネントは同一の[ネットワーク](me-network-connections.md)上に存在する必要があり、1つのネットワークにつき空間入出力セットアップは1つだけです。そのため、[サブネットワーク](subnetworks.md)の使用が推奨されます。

## 空間ME入出力ポート

<BlockImage id="spatial_io_port" p:powered="true" scale="4" />

<ItemLink id="spatial_io_port" />は空間入出力操作を制御します。マルチブロック構成の状態を表示し、[空間セル](../items-blocks-machines/spatial_cells.md)を保持します。

表示される情報：
- ネットワーク内の保存エネルギーと最大[エネルギー](energy.md)
- 操作に必要なエネルギー（非常に大きくなることがあり、瞬時に消費されるため、十分な[エネルギーセル](../items-blocks-machines/energy_cells.md)が必要）
- パイロン配列の効率
- 定義された空間サイズ

空間入出力を実行するには、空間ストレージセルを入力スロットに入れ、空間ME入出力ポートにレッドストーン信号を与えます。その後、パイロンで定義された空間と空間ストレージ次元の空間が**スワップ**されます。

つまり、一度あるブロック群を空間次元へ送った後、別のブロック群をパイロン内に配置し、同じセルを再び挿入して再実行すると、2回目のブロック群は消え、最初のブロック群が戻ってきます。

**注意：定義された空間内にいるエンティティ（プレイヤー含む）も一緒に移動します。戻る手段がない場合、何もない暗い空間に閉じ込められます。友達へのドッキリに使えます。**

## パイロン

<BlockImage id="spatial_pylon" p:powered_on="true" scale="4" />

<ItemLink id="spatial_pylon" />は空間入出力構成の中心部であり、対象となる空間領域を定義します。

領域はパイロンの外枠バウンディングボックスを基準に、その内側1ブロック分を差し引いた範囲で決まります。

ルール：
- 最小サイズは3×3×3（定義される内部空間は1×1×1）
- すべてのパイロンは外枠バウンディングボックス内に存在する必要がある
- すべてのパイロンは同一ネットワークに接続されている必要がある
- すべてのパイロンは最低2ブロック以上の高さが必要

例えば3×3×3の領域を定義したい場合、パイロンはその外側の5×5×5のシェル内に配置されていなければなりません。配置はその1ブロック厚の範囲内であれば自由です。

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/spatial_storage_3x3x3_pylon_demonstration.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        移動対象の空間
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

より実用的な構成は以下のようになります：

<GameScene zoom="4" interactive={true}>
<ImportStructure src="../assets/assemblies/better_spatial_storage_3x3x3.snbt" />

<BoxAnnotation color="#33dd33" min="1 1 1" max="4 4 4">
        移動対象の空間
  </BoxAnnotation>

<BoxAnnotation color="#3333ff" min="5 5 0" max="0 0 5">
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 効率

パイロン配列の効率はシェルの充填度に依存します。大きな空間を最小限の構成で囲うと非常に非効率になり、**数十億AE**を要求する場合もあります。

## セルの次元

一度使用された[空間セル](../items-blocks-machines/spatial_cells.md)は、XYZ寸法（例：3×4×2）が永続的に固定され、空間ストレージ次元内の特定空間にリンクされます。**一度使用した空間セルはリセット・再フォーマット・リサイズできません。** 異なるサイズを使う場合は新しいセルを作成してください。

また、セル名の「16^3」などは上限サイズを示すだけであり、実際の寸法はその範囲内で任意です（例：最大16×16×16）。

さらに、この空間は方向性を持ち、回転できません。2×2×3と3×2×2は同じ体積でも異なる構造として扱われます。

セルのXYZ寸法がポートで定義された空間サイズと一致しない場合、ME入出力ポートは動作しません。
