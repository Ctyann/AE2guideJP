---
navigation:
  parent: example-setups/example-setups-index.md
  title: 特化型ローカルストレージ
  icon: drive
---

# 特化型ローカルストレージ

[インターフェースの特殊な挙動](../items-blocks-machines/interface.md#special-interactions)の1つを利用することで、
[サブネットワーク](../ae2-mechanics/subnetworks.md)はメインネットワークのストレージを参照することなく、その内容をメインネットワークへ提示でき、さらに使用する[チャンネル](../ae2-mechanics/channels.md)は1つだけで済みます。

これはファームなどのローカルストレージ用途に有用で、アイテムがメインストレージへ溢れ出すのを防ぐことができます。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/local_storage.snbt" />

<BoxAnnotation color="#dddddd" min="4 0 0" max="5 2 1">
        (1) アイテムを取り込む手段（この例ではインターフェース）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 0 0" max="4 1 1">
        (2) ドライブ：セルが格納されている。セルはファームの出力に合わせてフィルタ設定する必要がある。
        また、セルには均等分配カードやオーバーフロー破壊カードを設定可能。
        <Row><ItemImage id="item_storage_cell_4k" scale="2" /> <ItemImage id="equal_distribution_card" scale="2" /> <ItemImage id="void_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1 0" max="4 2 0.3">
        (3) クラフティング端末：サブネット上のドライブ内容は参照できるが、メインネットワークのストレージ内容は参照できない
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (4) インターフェース #2：デフォルト設定
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 0" max="2 1 1">
        (5) ストレージバス：メインストレージより高い優先度に設定。ファーム出力に合わせてフィルタ可能
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 0.3">
        クラフティング端末：メインネットワークとサブネットワークの両方のストレージ内容を参照可能
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 構成設定

* サブネット側の最初の<ItemLink id="interface" />（1）は、ファームからのアイテムを受け取りサブネットへ送信するだけの役割
* <ItemLink id="drive" />（2）にはいくつかの[セル](../items-blocks-machines/storage_cells.md)が格納されている。セルはファームの出力に合わせて[パーティション](../items-blocks-machines/cell_workbench.md)設定する必要がある
  またセルには<ItemLink id="equal_distribution_card" />や<ItemLink id="void_card" />を装着可能
* 2つ目の<ItemLink id="interface" />（4）はデフォルト設定
* <ItemLink id="storage_bus" />は[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)をメインストレージより高く設定し、ファーム出力に合わせてフィルタ可能

## 動作原理

* サブネット上の<ItemLink id="interface" />はメインネットワーク側の<ItemLink id="storage_bus" />に対し、<ItemLink id="drive" />内の内容を提示する
  これによりストレージバスはドライブ内のセルへ直接アイテムを出し入れできる
* ストレージバスは高い[優先度](../ae2-mechanics/import-export-storage.md#storage-priority)を持つため、アイテムはメインストレージよりもサブネット側へ優先的に格納される
* 重要な点として、セルが満杯になった場合でもアイテムはメインネットワークへ溢れ出さない
  もしバックアップで動作が停止するタイプのファームであれば、<ItemLink id="void_card" />を使用して余剰アイテムを削除できる
* 複数種類のアイテムを出力するファームの場合、<ItemLink id="equal_distribution_card" />を使用することで特定アイテムだけがセルを占有するのを防げる
