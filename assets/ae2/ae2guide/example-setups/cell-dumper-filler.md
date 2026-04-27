---
navigation:
  parent: example-setups/example-setups-index.md
  title: セルダンパー／フィラー
  icon: io_port
---

# セルダンパー／フィラー

「ストレージセルの中身をチェストやドロワー配列、バックパックへ素早く空にしたい、あるいは逆にそれらからセルへ素早く詰め込みたい」と思うことがあります。

その答えは<ItemLink id="io_port" />の使用と、アイテムの出入り先を制限するためのサブネット構成です。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/cell_dumper_filler.snbt" />

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 1">
        (1) ME入出力ポート：中央のGUIにある矢印ボタンで「ネットワークへ転送」または「ストレージセルへ転送」を切り替え可能。アクセラレーションカード3枚搭載
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0.7 0" max="1 1 1">
        (2) MEストレージバス：デフォルト設定
  </BoxAnnotation>

<BoxAnnotation color="#33dd33" min="0 1 0" max="1 2 1">
        ここに空にしたい、または詰め込みたい対象を配置
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0.35 0.35" max="2.3 0.65 0.65">
        クォーツファイバー：別ネットワークから電力供給する場合のみ必要
  </BoxAnnotation>

<DiamondAnnotation pos="3 0.5 0.5" color="#00ff00">
        別ネットワークまたはエナジーアクセプターなどの電源へ接続
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 構成

* <ItemLink id="io_port" />（1）は中央の矢印ボタンで「ネットワークへ転送」または「ストレージセルへ転送」に切り替え可能。最大速度のためアクセラレーションカード3枚を装備
* <ItemLink id="storage_bus" />（2）はデフォルト設定

## 動作原理

### 「ネットワークへ転送」モード

1. <ItemLink id="io_port" />は挿入された[ストレージセル](../items-blocks-machines/storage_cells.md)の中身を[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ移動しようとします
2. サブネット上の唯一のストレージである<ItemLink id="storage_bus" />が、前面にあるインベントリからアイテムや液体などを受け取り、ネットワークへ格納します
* <ItemLink id="energy_cell" />は十分な[エネルギー](../ae2-mechanics/energy.md)バッファを提供し、1ティックあたり大量転送してもネットワークが枯渇しないようにします

### 「ストレージセルへ転送」モード

1. <ItemLink id="io_port" />はネットワークの[ストレージ](../ae2-mechanics/import-export-storage.md)の内容を挿入された[ストレージセル](../items-blocks-machines/storage_cells.md)へ書き込みます
2. サブネット上の唯一のストレージである<ItemLink id="storage_bus" />が、前面のインベントリからアイテムや液体などを引き出し、ネットワークに渡します
* <ItemLink id="energy_cell" />は十分な[エネルギー](../ae2-mechanics/energy.md)バッファを提供し、1ティックあたり大量転送してもネットワークが枯渇しないようにします
