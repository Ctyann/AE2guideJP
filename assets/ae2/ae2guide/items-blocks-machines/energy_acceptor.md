---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: エネルギーアクセプター
  icon: energy_acceptor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_acceptor
---

# エネルギーアクセプター

<Row gap="20">
<BlockImage id="energy_acceptor" scale="8" />

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
</GameScene>
</Row>

エネルギーアクセプターは、他のテックモッドの一般的なエネルギー形式をAE2の内部エネルギー形式である[AE](../ae2-mechanics/energy.md)に変換します。<ItemLink id="controller" />もこの機能を持っていますが、コントローラーの面は貴重なので、代わりにエネルギーアクセプターを使用する方が良い場合があります。

Forge EnergyとTechreborn Energyの変換比率は以下の通りです：

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

変換速度は、ネットワークが蓄えられるAEの量に完全に依存します。この理由については[こちらのページ](../ae2-mechanics/energy.md)で説明されています。

## バリエーション

エネルギーアクセプターには、通常タイプとフラット/サブパーツ([subpart](../ae2-mechanics/cable-subparts.md))タイプの2種類があります。これにより、一部のセットアップをよりコンパクトにすることができます。

エネルギーアクセプターは、クラフティンググリッドで通常タイプとフラットタイプを切り替えることができます。

## レシピ

<RecipeFor id="energy_acceptor" />

<RecipeFor id="cable_energy_acceptor" />
