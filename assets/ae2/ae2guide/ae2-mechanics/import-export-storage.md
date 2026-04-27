---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: インポート・エクスポート・ストレージ
---

# インポート・エクスポート・ストレージ

**あなたのMEシステムとワールド**

AE2における重要な概念のひとつが「ネットワークストレージ」です。これはネットワークの中身が保存される場所であり、通常は[ストレージセル](../items-blocks-machines/storage_cells.md)や、<ItemLink id="storage_bus" />が接続されている任意のインベントリです。ほとんどのAE2の[デバイス](../ae2-mechanics/devices.md)は、このストレージと何らかの形で関わります。

例えば：

*   <ItemLink id="import_bus" />はネットワークストレージへアイテムを送り込む
*   <ItemLink id="export_bus" />はネットワークストレージからアイテムを取り出す
*   <ItemLink id="interface" />はネットワークストレージへの入出力の両方を行う
*   [ターミナル](../items-blocks-machines/terminals.md)は、アイテムの出し入れやクラフトスロットの補充を通じて、ネットワークストレージとの入出力を行う
*   <ItemLink id="storage_bus" />は直接ストレージに対して入出力するのではなく、接続されたインベントリをネットワークストレージとして扱う（つまり実際には他のデバイスがそれに対して入出力する）

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_export_storage.snbt" />

  <BoxAnnotation color="#dddddd" min="8 1 1" max="9 1.3 2">
        MEインポートバスは、向いているインベントリからネットワークストレージへアイテムを取り込む
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="8 2 1" max="9 3 1.3">
        ターミナルからインベントリにアイテムを入れる操作は、ネットワークがそれをインポートした扱いになる
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="7 0 1" max="8 1 2">
        MEインターフェースは、内部インベントリのスロットが未設定、または設定より多くアイテムがある場合、その内部インベントリからインポートする。そのためアイテムを押し込んでネットワークへ入れることができる
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="6 0 1" max="7 1 2">
        MEパターンプロバイダーは、内部の返却スロットからインポートする。そのためアイテムを押し込んでネットワークへ入れることができる
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 1" max="5 2 2">
        ドライブは挿入されたセルをネットワークストレージとして提供する
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        MEストレージバスは、接続されたインベントリをネットワークストレージとして使用する
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 1 1" max="2 1.3 2">
        MEエクスポートバスは、ネットワークストレージから接続先インベントリへアイテムを出力する
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 1" max="2 3 1.3">
        ターミナルからアイテムを取り出す操作は、ネットワークがそれをエクスポートした扱いになる
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 1 1" max="1 2 2">
        MEインターフェースは、設定されたスロットがある場合その内部インベントリへエクスポートする。そのためネットワークから取り出すことができる
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

ストレージへの「入れる（プッシュ）」と「取り出す（プル）」という動作は、オートメーションや物流設計において重要なポイントです。

## ストレージ優先度

優先度は一部のGUI右上にあるレンチアイコンから設定できます。

ネットワークに入るアイテムは、最も優先度の高いストレージから順に格納されます。もし同じ優先度のストレージが複数ある場合、その中で既に同じアイテムを含んでいるストレージが優先されます。ホワイトリスト設定されたセルは、同じ優先度グループ内では「既にそのアイテムを含んでいる」とみなされます。

アイテムがストレージから取り出される場合は、最も優先度の低いストレージから取り出されます。この優先度システムにより、アイテムの出し入れに応じて高優先度のストレージが先に満たされ、低優先度のストレージが先に空になります。
