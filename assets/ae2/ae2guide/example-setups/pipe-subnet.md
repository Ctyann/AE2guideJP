---
navigation:
  parent: example-setups/example-setups-index.md
  title: アイテム/流体「パイプ」サブネット
  icon: storage_bus
---

# アイテム/流体「パイプ」サブネット

AE2の[デバイス](../ae2-mechanics/devices.md)を使ってアイテム/流体パイプを擬似的に再現するシンプルな方法です。要するに、アイテムや流体パイプとして使えるあらゆる用途に利用できます。
これには、クラフト結果を<ItemLink id="pattern_provider" />へ返送する用途も含まれます。

一般的に、これを実現する方法は2種類あります。

## MEインポートバス → MEストレージバス

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) MEインポートバス：フィルター可能
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) MEストレージバス：フィルター可能。これ（および目的地にしたい他のMEストレージバス）はネットワーク上で唯一のストレージである必要があります。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        供給元
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        送信先
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

ソース側のインベントリにある<ItemLink id="import_bus" /> (1) がアイテムまたは流体を取り込み、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へ格納しようとします。
サブネットである理由は、ネットワーク上に存在する唯一のストレージが<ItemLink id="storage_bus" /> (2) だからです（そのためメインネットワークではなくサブネットになります）。
結果として、アイテムまたは流体は目的地のインベントリへ配置されます。つまり転送が行われます。エネルギーは<ItemLink id="quartz_fiber" />によって供給されます。
MEインポートバスとMEストレージバスの両方はフィルター可能ですが、設定しない場合はアクセス可能なものすべてを転送します。
この構成は複数のMEインポートバスおよび複数のMEストレージバスにも対応しています。

## MEストレージバス → MEエクスポートバス

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) MEストレージバス：フィルター可能。これ（および供給元にしたい他のMEストレージバス）はネットワーク上で唯一のストレージである必要があります。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) MEエクスポートバス：フィルター必須
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        供給元
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        送信先
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

目的地インベントリ側の<ItemLink id="export_bus" />は、フィルターに含まれるアイテムを[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)から引き出そうとします。
サブネットである理由は、ネットワーク上に存在する唯一のストレージが<ItemLink id="storage_bus" />だからです。
その結果、アイテムまたは流体はソースインベントリから引き出され転送されます。エネルギーは<ItemLink id="quartz_fiber" />によって供給されます。
MEエクスポートバスはフィルター必須であるため、この構成はフィルター設定がある場合のみ動作します。
この構成は複数のMEストレージバスおよび複数のMEエクスポートバスにも対応しています。

## 動作しない構成（MEインポートバス → MEエクスポートバス）

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        MEインポートバス：ネットワークにストレージがないため、格納先が存在しません。
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        (2) MEエクスポートバス：ネットワークにストレージがないため、取り出す対象が存在しません。
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        供給元
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        送信先
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

MEインポートバスとMEエクスポートバスだけの構成は動作しません。MEインポートバスはソースインベントリからアイテムを取り込み、ネットワークストレージへ格納しようとします。一方MEエクスポートバスはネットワークストレージからアイテムを取り出して目的地へ送ろうとします。しかし、このネットワークには**ストレージが存在しないため**、インポートもエクスポートも成立せず、何も起こりません。

## 1面での入力と出力

例えば、1つの面から入力を受け取り、同じ面から出力も取り出せる機械（例：<ItemLink id="charger" />）があるとします。
この場合、2つのパイプサブネット方式を組み合わせることで、入力と出力の両方を処理できます。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) MEインポートバス：フィルター可能
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) MEストレージバス：フィルター可能。この（および入出力したい他のMEストレージバス）はネットワーク上で唯一のストレージである必要があります。
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) 対象（入出力したいもの）：この例ではチャージャー
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) MEエクスポートバス：フィルター必須
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        供給元
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        送信先
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## MEインターフェース

実は、MEインポートバスやMEエクスポートバス以外にも[デバイス](../ae2-mechanics/devices.md)には[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)へアイテムを出し入れできるものがあります。
その代表が<ItemLink id="interface" />です。MEインターフェースが保管対象として設定していないアイテムが挿入されると、それはネットワークストレージへ送られます。これはMEインポートバス→MEストレージバスの仕組みと同様に利用できます。
逆に、MEインターフェースで保管設定されているアイテムはネットワークストレージから引き出されます。これはMEストレージバス→MEエクスポートバスと同じ動作です。
MEインターフェースは一部のアイテムのみ保管し、他を保管しないように設定できるため、MEストレージバスを介してリモートで入出力を制御できます（必要なら）。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        MEインターフェース
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        MEストレージバス
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        MEストレージバス
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        MEインターフェース
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 1対多・多対1（および多対多）

もちろん、<ItemLink id="import_bus" />や<ItemLink id="export_bus" />、<ItemLink id="storage_bus" />を1つだけ使う必要はありません。

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## 複数箇所への供給

ここまでを踏まえると、1つの<ItemLink id="pattern_provider" />の面から複数の場所へ材料を送る方法が導き出せます。例えば機械の集合体や、1つの機械の複数面などです。

ただし、パターンプロバイダは実際には材料を保持しないため、インポート→ストレージやストレージ→エクスポートの方式は使えません。代わりにプロバイダは隣接インベントリへ直接アイテムを押し出すため、同様にアイテムを受け取れる隣接インベントリが必要です。

そこで登場するのが…<ItemLink id="interface" />です！
パターンプロバイダを方向付きまたはフラットサブパーツモードにし、かつMEインターフェースもフラットサブパーツモードにして、ネットワーク接続が成立しないようにしてください。

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        MEインターフェース（フルブロックではなくフラット必須）
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        MEストレージバス
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        供給先（複数機械、または1機械の複数面など）
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>
