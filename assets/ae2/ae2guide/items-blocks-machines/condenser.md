---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: マターコンデンサー
  icon: condenser
  position: 310
categories:
- machines
item_ids:
- ae2:condenser
---

# マターコンデンサー

<BlockImage id="condenser" scale="8" />

マターコンデンサーは、ゴミ箱として使用するか、<ItemLink id="matter_ball" />や[特異点](singularities.md)を作成するために使用できます。ストレージセルが保存できるアイテムや液体など、あらゆるものを受け入れることができます。

## 設定/レシピ

* ゴミ箱モードでは、マターコンデンサーは入力されたすべてのものを無効化します。
* マターボールモードでは、投入されたものから<ItemLink id="matter_ball" />を作成します。このモードでは、コンデンサーの上部スロットにストレージコンポーネントを配置する必要があります。マターボールは256個のアイテムまたはバケツごとに1つ作成されるため、<ItemLink id="cell_component_1k" />（8192ビットの容量を提供）があれば十分です。
* マター特異点モードでは、投入されたものから[特異点](singularities.md)を作成します。このモードでは、コンデンサーの上部スロットにストレージコンポーネントを配置する必要があります。特異点は256,000個のアイテムまたはバケツごとに1つ作成されるため、<ItemLink id="cell_component_64k" />（524,288ビットの容量を提供）があれば十分です。

後者の2つのモードでは、エネルギーと出力アイテムのバッファが完全に満杯になると、マターコンデンサーはバックアップし、それ以上の入力を受け付けなくなることに注意してください。

## レシピ

<RecipeFor id="condenser" />
