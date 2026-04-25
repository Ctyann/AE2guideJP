---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 形成プレーン
  icon: formation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:formation_plane
---

# 形成プレーン

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/formation_plane.snbt" />
</GameScene>

形成プレーンはブロックを設置し、アイテムをドロップします。挿入専用の<ItemLink id="storage_bus" />のように動作し、
<ItemLink id="import_bus" />や<ItemLink id="interface" />のような[デバイス](../ae2-mechanics/devices.md)が[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ挿入して
そこへ「格納」したものを設置/ドロップします。

<GameScene zoom="8" interactive={true}>
  <ImportStructure src="../assets/assemblies/formation_plane_demonstration.snbt" />
  <IsometricCamera yaw="255" pitch="30" />
</GameScene>

これは、[パイプサブネット](../example-setups/pipe-subnet.md)における import bus -> storage bus および interface -> storage bus の配管に似ていることに注目してください。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_storage_pipe.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

この[デバイス](../ae2-mechanics/devices.md)は、[パイプサブネット](../example-setups/pipe-subnet.md)などでストレージバスが使う仕組みを利用しており、
アイテムを搬送する代わりにドロップしたりブロックを設置したい場合、そうした構成ではストレージバスの代わりに使用できます。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

**チャンククレームでフェイクプレイヤーを有効化するのを忘れないでください**

## フィルター

デフォルトでは、このプレーンは何でも設置/ドロップします。フィルタースロットに入れたアイテムがホワイトリストとして機能し、
その特定のアイテムのみ設置できるようになります。

実際にそのアイテムを所持していなくても、JEI/REIからアイテムや流体をスロットへドラッグできます。

バケツや流体タンクのような流体コンテナを持って右クリックすると、バケツやタンク自体ではなく、その中の流体をフィルターとして設定できます。

## 優先度

GUI右上のレンチをクリックして優先度を設定できます。
ネットワークに入るアイテムは、最も高い優先度のストレージから処理されます。

## 設定

*   プレーンは、ワールド内にブロックを設置するか、アイテムをドロップするか設定できます

## アップグレード

形成プレーンは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="capacity_card" /> フィルタースロット数を増やします
*   <ItemLink id="fuzzy_card" /> 耐久値でのフィルターや、アイテムNBTの無視を可能にします
*   <ItemLink id="inverter_card" /> フィルターをホワイトリストからブラックリストへ切り替えます

## レシピ

<RecipeFor id="formation_plane" />
