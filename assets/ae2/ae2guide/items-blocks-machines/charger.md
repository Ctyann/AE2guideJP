---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: チャージャー
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# チャージャー

<BlockImage id="charger" scale="8" />

チャージャーは、対応するツールや<ItemLink id="certus_quartz_crystal" />を充電する方法を提供します。

電力は上部または下部から供給でき、AE2の[ケーブル](cables.md)や他のモッドの電力ケーブルを使用できます。AE2の電力（AE）またはForge Energy（FE）のいずれも受け入れます。アイテムはどの側面からでも挿入または取り出すことができます。結果のみが取り出されるため、チャージドケルタスではなく通常のケルタスクリスタルを取り出すのを防ぐためのフィルターは不要です。自動化を容易にするために<ItemLink id="certus_quartz_wrench" />で回転させることができます。

<ItemLink id="certus_quartz_crystal" />から<ItemLink id="charged_certus_quartz_crystal" />を作成したり、<ItemLink id="minecraft:compass" />から<ItemLink id="meteorite_compass" />を作成するために使用できます。

手動で電力を供給するには、上部または下部に<ItemLink id="crank" />を取り付け、アイテムが充電されるまで右クリックします。

また、[フルーシュ研究者](fluix_researcher.md)の作業台としても機能します。

## 簡単な自動化

例として、回転可能な特性を利用して、以下のようにチャージャーを半自動化できます:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/charger_hopper.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## レシピ

<RecipeFor id="charger" />
