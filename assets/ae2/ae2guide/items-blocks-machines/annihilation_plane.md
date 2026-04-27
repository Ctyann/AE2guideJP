---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ME消滅プレーン
  icon: annihilation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:annihilation_plane
---

# ME消滅プレーン

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/annihilation_plane.snbt" />
</GameScene>

ME消滅プレーンはブロックを破壊し、アイテムを拾います。これは<ItemLink id="import_bus" />と似たように機能し、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)にアイテムをプッシュします。アイテムを拾うには、プレーンの面に衝突する必要があり、範囲内のアイテムを拾うわけではありません。

ME消滅プレーンには任意のツルハシのエンチャントを付与することができるため、いくつかに高レベルの幸運を付けて[鉱石処理を自動化](../example-setups/ore-fortuner.md)することが可能です（モッドパックが許可している場合）。さらに、シルクタッチは期待通りに機能し、効率はブロックを破壊する際のエネルギーコストを削減し、耐久力はエネルギーを消費しない可能性を与えます。

これらは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

**チャンククレームでフェイクプレイヤーを有効にすることを忘れないでください**

## フィルタリング

ME消滅プレーンは、ネットワークにドロップ/アイテムを保存できる場合にのみブロックを破壊したりアイテムを拾ったりします。つまり、フィルタリングを行うには、*ネットワークに保存できるものを制限する必要があります*。最も可能性が高いのは、[サブネットワーク](../ae2-mechanics/subnetworks.md)に配置することです。<ItemLink id="storage_bus" />や[セル](../items-blocks-machines/storage_cells.md)を[パーティション化](cell_workbench.md)することでこれを実現できます。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/annihilation_filtering.snbt" />

  <DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        壊したいものからドロップするものにフィルタリングされています。
  </DiamondAnnotation>

  <DiamondAnnotation pos=".5 0.5 2.5" color="#00ff00">
        壊したいものからドロップするものにパーティション化されています。
  </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

再度言いますが、*アイテムドロップによってフィルタリングされます*。例えば、<ItemLink id="minecraft:amethyst_cluster" />を壊すのをフィルタリングしたい場合、シルクタッチでエンチャントされたプレーンが必要です。そうでないと、成長の各段階で何もドロップせず、ネットワークは常に「何もない」を保存できるため、プレーンはそれらを壊してしまいます。

## レシピ

<RecipeFor id="annihilation_plane" />
