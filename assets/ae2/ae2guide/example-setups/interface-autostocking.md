---
navigation:
  parent: example-setups/example-setups-index.md
  title: インターフェース自動補充
  icon: interface
---

# インターフェース自動補充

「一定量のアイテムを常に在庫として維持し、必要に応じて自動でクラフトさせるにはどうすればいいのか？」という疑問が出ることがあります。

その解決方法の一つが、<ItemLink id="interface" /> と <ItemLink id="crafting_card" /> を使って、ネットワークの[自動クラフト](../ae2-mechanics/autocrafting.md)に新規アイテムを継続的に要求させる方法です。この構成は、少量ずつ多種類のアイテムを維持したい場合に特に適しています。

このデモ構成は横幅が広くなりすぎないよう途中までしか示していませんが、実際には4つの <ItemLink id="interface" /> と4つの <ItemLink id="storage_bus" /> を使うことで、通常の[ケーブル](../items-blocks-machines/cables.md)1本あたりの8[チャンネル](../ae2-mechanics/channels.md)を最大限活用するのが最も効率的です。

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_autostocking.snbt" />

<BoxAnnotation color="#dddddd" min="0 0 0" max="2 1 1">
        (1) インターフェース：設定されたアイテムを常に保持するように設定されている。クラフティングカードを装備している。
        <ItemImage id="crafting_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="2 1.3 1">
        (2) ストレージバス：「入出力モード」が「抽出のみ」に設定されている。
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        メインネットワークへ
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 設定

* <ItemLink id="interface" />（1）は、必要なアイテムをスロットに入れるか、JEIからドラッグして設定し、上部のスロット量を設定ボタン（レンチアイコン）で必要数を指定することで、そのアイテムを保持するように設定する。これらには <ItemLink id="crafting_card" /> が必要。
* <ItemLink id="storage_bus" />（2）は「入出力モード」が「抽出のみ」に設定されている。

## 動作

1. <ItemLink id="interface" /> が設定されたアイテムを[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)から必要量取得できない場合、（かつ <ItemLink id="crafting_card" /> がある場合）、ネットワークの[自動クラフト](../ae2-mechanics/autocrafting.md)に対して不足分のクラフト要求を行う。
2. <ItemLink id="storage_bus" /> はネットワークがインターフェースの内部在庫にアクセスできるようにする。
