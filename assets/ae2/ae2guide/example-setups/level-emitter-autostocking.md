---
navigation:
  parent: example-setups/example-setups-index.md
  title: レベルエミッター自動補充
  icon: level_emitter
---

# レベルエミッター自動補充

「特定のアイテムを一定数だけ常に在庫として維持し、不足したら自動でクラフトさせるにはどうすればいいのか？」という疑問があります。

その方法の一つが、<ItemLink id="export_bus" />・<ItemLink id="level_emitter" />・<ItemLink id="crafting_card" /> を組み合わせて、ネットワークの[自動クラフト](../ae2-mechanics/autocrafting.md)に不足分を要求させる構成です。この方式は、単一アイテムを大量に安定供給したい場合に適しています。

もちろん、レベルエミッターとレッドストーンカードを省略すれば、常時クラフトし続ける構成にすることもできます。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/level_emitter_autostocking.snbt" />

  <BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (1) エクスポートバス：対象アイテムにフィルタされている。レッドストーンカードとクラフティングカードを装備。
        レッドストーンモードは「信号時に動作」、クラフト挙動は「既存在庫を使用しない」。
        <Row><ItemImage id="redstone_card" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0.7 1 0" max="1 2 1">
        (2) レベルエミッター：対象アイテムと数量が設定されており、「指定量未満で信号を出力」に設定されている。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (3) インターフェース：デフォルト設定。
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 設定

* <ItemLink id="export_bus" />（1）は対象アイテムにフィルタされており、<ItemLink id="redstone_card" /> と <ItemLink id="crafting_card" /> を装備している。
  レッドストーンモードは「信号時に動作」、クラフト挙動は「既存在庫を使用しない」に設定されている。
* <ItemLink id="level_emitter" />（2）は対象アイテムと数量が設定され、「指定量未満で信号を出力」に設定されている。
* <ItemLink id="interface" />（3）はデフォルト設定。

## 動作

1. ネットワークの[ストレージ](../ae2-mechanics/import-export-storage.md)内の対象アイテム量が、<ItemLink id="level_emitter" />で指定した数量を下回ると、レベルエミッターがレッドストーン信号を出力する。
2. レッドストーン信号を受けた <ItemLink id="export_bus" /> は（<ItemLink id="crafting_card" /> の効果と「在庫を使用しない」設定により）ネットワークの[自動クラフト](../ae2-mechanics/autocrafting.md)へ不足分の作成を要求し、その後アイテムをエクスポートする。
3. アイテムが <ItemLink id="interface" /> に入ると、インターフェースはそれをネットワークストレージへ送る。
