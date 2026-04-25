---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: トグルバス
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# トグルバス

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/toggle_bus.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

トグルバスは<ItemLink id="fluix_glass_cable" />などのケーブルと同様の機能を持ちながら、レッドストーン信号によって接続状態を切り替えることができるパーツです。これにより、MEネットワークの一部を切り離すことが可能になります。

レッドストーン信号が入力されている間は接続が有効になり、<ItemLink id="inverted_toggle_bus" />はその逆で、信号入力時に接続が無効になります。

なお、これらを切り替えるとネットワークが再起動し、接続されているデバイスの再計算が行われる場合があります。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

## レシピ

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />
