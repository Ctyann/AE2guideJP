---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 成長加速器
  icon: growth_accelerator
  position: 310
categories:
- machines
item_ids:
- ae2:growth_accelerator
---

# 成長加速器

<BlockImage id="growth_accelerator" p:powered="true" scale="8"/>

成長加速器は、芽吹きブロックに隣接して設置すると、ケルタスまたはアメジストの[成長](../ae2-mechanics/certus-growth.md)を大幅に加速します。

興味深いことに、さまざまな植物の成長も*同様に*加速できます。

これは、自然発生するランダムティックに加えて、隣接するブロックへ「ランダムティック」を適用することで実現しています。
理論上、加速器1台で成長速度は通常の約90倍になり、その効果は加算で累積します。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/growth_accelerator.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

電力は上面または下面から供給でき、AE2の[ケーブル](cables.md)または他Modの電力ケーブルに対応しています。
AE2の電力(AE)とForge Energy(FE)のどちらも受け入れ可能です。

手動で給電するには、上面または下面に<ItemLink id="crank" />を設置して右クリックします。

上面と下面は、付いているピンク色のフラックス装飾で見分けられます。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/accelerator_connections.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## レシピ

<RecipeFor id="growth_accelerator" />
