---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ケーブル
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# ケーブル

<GameScene zoom="3" background="transparent">
  <ImportStructure src="../assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

MEネットワークは隣接するME対応の機械によっても作成されますが、ケーブルはMEネットワークを広い範囲に拡張するための主要な方法です。

異なる色のケーブルを使用することで、隣接するケーブルが互いに接続しないようにし、[チャンネル](../ae2-mechanics/channels.md)をより効率的に分配することができます。また、接続された端末の色にも影響を与えるため、すべての端末を紫色にする必要はありません。フルーシュケーブルは他のすべての色に接続します。

注目すべき点として、**チャンネルはケーブルの色とは無関係です**。

## 重要な注意点

**AE2に不慣れでチャンネルに精通していない場合は、スマートケーブルや高密度スマートケーブルをできるだけ使用してください。これにより、チャンネルがネットワーク内でどのようにルートされているかが表示され、その動作をより理解しやすくなります。**

## もう1つの注意点

**これらはアイテムや液体、エネルギーなどのパイプではありません。** 内部インベントリはなく、MEパターンプロバイダーや機械がそれらに「プッシュ」することはありません。これらはAE2の[デバイス](../ae2-mechanics/devices.md)をネットワークに接続するだけです。

## ガラスケーブル

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/fluix_glass_cable.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" />は最も簡単に作成できるケーブルで、電力と最大8つの[チャンネル](../ae2-mechanics/channels.md)を転送します。17種類の異なる色があり、デフォルトはフルーシュで、16種類の染料を使用して任意の色に染めることができます。

色付きケーブルをクラフトするには、任意の種類の染料を8本の同じタイプのケーブルで囲みます（ケーブルの色は関係ありませんが、同じタイプである必要があります。ガラス、スマートなど）。また、Forge互換のペイントブラシを使用してケーブルを塗装することもできます。

水バケツで任意の色付きケーブルをクラフトすると、染料を取り除くことができます。

ケーブルに羊毛を被せて<ItemLink id="fluix_covered_cable" />を作成し、<ItemLink id="fluix_smart_cable" />をクラフトして[チャンネル](../ae2-mechanics/channels.md)の状況をよりよく把握することができます。

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

## 被覆ケーブル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

被覆ケーブルのバリエーションは、その<ItemLink id="fluix_glass_cable" />対応品と比較してゲームプレイ上の利点はありません。ただし、被覆された外観を好む場合は代替の美的選択肢として使用できます。

<ItemLink id="fluix_glass_cable" />と同じ方法で色を付けることができます。4つの<ItemLink id="fluix_covered_cable" />をレッドストーンとグロウストーンでクラフトすると、<ItemLink id="fluix_covered_dense_cable" />を作成できます。

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

## 高密度ケーブル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

高容量ケーブルで、標準ケーブルが8チャンネルしか運べないのに対し、32チャンネルを運ぶことができます。ただし、バスをサポートしていないため、バスやパネルを使用する前に高密度ケーブルから<ItemLink id="fluix_glass_cable" />や<ItemLink id="fluix_smart_cable" />などの小さなケーブルに切り替える必要があります。

高密度ケーブルは「最短経路」動作をわずかに上書きします。チャンネルは高密度ケーブルへの最短経路を取り、その後その高密度ケーブルを通じてコントローラーへの最短経路を取ります。

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

## スマートケーブル

<Row>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

<ItemLink id="fluix_covered_cable" />に外観が似ていますが、チャンネル使用状況を視覚化する診断機能を提供します。チャンネルは、ケーブルの黒いストライプに沿って走る点灯した色付きの線として表示され、ネットワークでチャンネルがどのように使用されているかを理解するのに役立ちます。通常のスマートケーブルでは、最初の4チャンネルがケーブルの色に一致する線として表示され、次の4チャンネルは白い線として表示されます。高密度スマートケーブルでは、各ストライプが4チャンネルを表します。

<ItemLink id="controller" />を備えたネットワークでは、ケーブル上の線がチャンネルが通る正確な経路を示します。

アドホックネットワーク上のスマートケーブルは、代わりにその特定のケーブルを通るチャンネル数ではなく、ネットワーク全体で使用されているチャンネル数を示します。

これらも<ItemLink id="fluix_glass_cable" />と同じ方法で色を付けることができます。

<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />
