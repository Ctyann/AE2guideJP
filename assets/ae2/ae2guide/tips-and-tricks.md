---
navigation:
  title: ヒントとコツ
  position: 20
---

# ヒントとコツ

ランダムな小さなおすすめの数々

* Optifineを削除する
* ズームや注釈の表示/非表示ボタンがあるガイドブックのシーンは回転やズームが可能です
* ネットワークを木構造に保ち、ループを避ける
* [デバイス](ae2-mechanics/devices.md)を8つ以下のグループにまとめて配置する。ただし、[チャンネル](ae2-mechanics/channels.md)がネットワーク内でどのようにルートされるかを深く理解している場合を除く
* 1種類の木材を選び、それをすべての[パターン](items-blocks-machines/patterns.md)で使用する。パターンでの代替を有効にすることは時々機能しますが、同じ木材タイプを一貫して使用することで手間が大幅に減ります。
* <ItemLink id="pattern_access_terminal" />内で[パターン](items-blocks-machines/patterns.md)を縦に並べるか、[プロバイダー](items-blocks-machines/pattern_provider.md)間でパターンを分配して、レシピを並行して実行できるようにする
* [エネルギーセル](items-blocks-machines/energy_cells.md)を追加して、ネットワークが電力スパイクに対応できるようにする
* <ItemLink id="condenser" />で水を使用できる
* ネットワークを清潔に保つ最良の方法は、剣や防具のようなランダムなモブの戦利品を入れないことです。エンチャントや耐久値の組み合わせごとに新しい[タイプ](ae2-mechanics/bytes-and-types.md)が作成されます。
* [処理パターン](items-blocks-machines/patterns.md)の結果を返す際には、「アイテムがシステムに入る」イベントが発生する必要があります。例えば、<ItemLink id="import_bus" />、<ItemLink id="interface" />、または<ItemLink id="pattern_provider" />の戻りスロットを通じて行う必要があり、<ItemLink id="storage_bus" />を使ってチェストに結果をパイプで送るだけではいけません。
* ズームや注釈の表示/非表示ボタンがあるガイドブックのシーンを回転やズームすることを忘れないでください
* <ItemLink id="pattern_provider" />は完全なレシピバッチのみをプッシュし、1つの側面を通じてのみ行います。これにより、機械が部分的なバッチを受け取らないようにするのに役立ちますが、時には材料を複数の場所に送る必要がある場合もあります。
  これを実現するには<ItemLink id="interface" />を使用します。例えば、["パイプ"サブネット](example-setups/pipe-subnet.md)として使用するか、複数の異なるアイテムスタック、液体、化学物質などを同時に保持できる能力を利用して、中間チェスト/タンクのように使用します。
* ズームや注釈の表示/非表示ボタンがあるガイドブックのシーンを回転やズームすることができます
