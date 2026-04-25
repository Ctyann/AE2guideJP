---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 芽生えたケルタスクォーツ
  icon: flawless_budding_quartz
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:flawless_budding_quartz
- ae2:flawed_budding_quartz
- ae2:chipped_budding_quartz
- ae2:damaged_budding_quartz
- ae2:small_quartz_bud
- ae2:medium_quartz_bud
- ae2:large_quartz_bud
- ae2:quartz_cluster
---

# 芽生えたケルタスクォーツ

(詳細は[ケルタスの成長](../ae2-mechanics/certus-growth.md)も参照)

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

ケルタスクォーツの芽は、芽生えたケルタスブロックからアメジストのように芽を出します。これらは[隕石](../ae2-mechanics/meteorites.md)で見つかります。
芽生えたケルタスブロックには、完璧、欠陥、欠け、損傷の4つの段階があります。これらは、HWYLA、Jade、The One Probeなどのモッド（またはf3画面）を使用して最も簡単に識別できます。

欠陥、欠け、損傷した芽生えたケルタスでは、芽が成長するたびに、芽生えたブロックが1段階劣化する可能性があり、最終的には普通の<ItemLink id="quartz_block" />に変わります。

完璧な芽生えたケルタスは、芽の成長によって劣化せず、無限の供給源として機能します。

通常のツルハシで破壊すると、芽生えたケルタスブロックは1段階劣化します。シルクタッチでエンチャントされたツルハシで破壊すると劣化しませんが、完璧な場合を除きます。**これは、完璧な芽生えたケルタスブロックはツルハシで拾って移動させることができないことを意味します**。代わりに、[空間ストレージ](../ae2-mechanics/spatial-io.md)を使用して、完璧な芽生えたブロックを切り取り、貼り付けて移動させることができます。

## レシピ

欠陥、欠け、損傷した芽生えたケルタスは、前の段階の芽生えたブロック（または<ItemLink id="quartz_block" />）を水に投げ込み、1つ以上の<ItemLink id="charged_certus_quartz_crystal" />と一緒にクラフトすることで作成できます。

完璧な芽生えたケルタスはクラフトできず、ワールド内でのみ見つかります。

<Row>
  <RecipeFor id="damaged_budding_quartz" />

  <RecipeFor id="chipped_budding_quartz" />

  <RecipeFor id="flawed_budding_quartz" />
</Row>
