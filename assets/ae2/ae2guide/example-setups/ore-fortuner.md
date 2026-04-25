---
navigation:
  parent: example-setups/example-setups-index.md
  title: 自動鉱石フォーチュン処理
  icon: minecraft:raw_iron
---

# 鉱石フォーチュン自動化

<ItemLink id="annihilation_plane" /> は任意のピッケル系エンチャントを付与でき、その中にはフォーチュンも含まれるため、明確な用途として「フォーチュン付きで鉱石を高速破壊する」構成が可能です。

これを利用し、<ItemLink id="formation_plane" /> と <ItemLink id="annihilation_plane" /> を組み合わせて鉱石を高速で設置・破壊することで、自動的にドロップ数を増加させることができます。

なお <ItemLink id="import_bus" /> は内部的に「起動して加速する」挙動を持つため、起動直後は遅く、数秒後に最大速度へ到達します。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 0 2" max="3 1 3">
        (1) インポートバス：いくつかの加速カードを搭載している。
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 2" max="2 1 2.3">
        (2) フォーメーションプレーン：デフォルト設定。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 0.7" max="2 1 1">
        (3) アニヒレーションプレーン：GUIなしで設定不可だが、フォーチュンが付与されている。
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 0" max="3 1 1">
        (4) ストレージバス：デフォルト設定。
  </BoxAnnotation>

<DiamondAnnotation pos="3.5 0.5 2.5" color="#00ff00">
        入力
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 0.5 0.5" color="#00ff00">
        出力
    </DiamondAnnotation>

<DiamondAnnotation pos="4 0.5 1.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 設定

* <ItemLink id="import_bus" />（1）には複数の <ItemLink id="speed_card" /> が入っている。フォーメーションプレーンの数が増えるほど、より多くの加速カードが必要になる。
* <ItemLink id="formation_plane" />（2）はデフォルト設定。
* <ItemLink id="annihilation_plane" />（3）はGUIなしで設定不可だが、フォーチュンが付与されている。
* <ItemLink id="storage_bus" />（4）はデフォルト設定。

## 動作

1. 緑サブネット上の <ItemLink id="import_bus" /> が最初のチェストからブロックを[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ取り込む。
2. 緑サブネットの唯一のストレージである <ItemLink id="formation_plane" /> がブロックを設置する。
3. オレンジサブネット上の <ItemLink id="annihilation_plane" /> がブロックを破壊し、フォーチュン効果を適用する。
4. オレンジサブネットの <ItemLink id="storage_bus" /> がドロップ結果を回収し、第二のチェストへ保存する。
