---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: ターミナル
  icon: crafting_terminal
  position: 210
categories:
- devices
item_ids:
- ae2:terminal
- ae2:crafting_terminal
- ae2:pattern_encoding_terminal
- ae2:pattern_access_terminal
---

# ターミナル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminals.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="pattern_provider" />、<ItemLink id="import_bus" />、<ItemLink id="storage_bus" />などの各種機構は、AE2ネットワークが世界とやり取りするための主要な手段ですが、ターミナルはAE2ネットワークが**プレイヤーと直接やり取りするための主要手段**です。用途の異なる複数の種類が存在します。

ターミナルは設置されている[ケーブル](cables.md)の色を継承します。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

## ターミナルの設置

ターミナルは最初に設置されることの多い[サブパーツ](../ae2-mechanics/cable-subparts.md)のため、設置方向を間違えて裏向きに置いてしまうことがよくあります。以下は正しい例と間違った例です：

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/terminal_placement.snbt" />
  <IsometricCamera yaw="195" pitch="30" />

  <LineAnnotation color="#ff3333" from="2.5 .5 .5" to="4.5 2.5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="2.5 2.5 .5" to="4.5 .5 .5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="-.5 2.5 .5" to="1 .5 .5" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1 .5 .5" to="1.5 1 .5" alwaysOnTop={true} thickness="0.05"/>
</GameScene>

これでターミナルとエネルギーアクセプターが揃いますが、ターミナルは正しい向きでネットワークに接続され、かつよりコンパクトな構成になります。

<a name="terminal-ui"></a>

# ターミナル検索

検索ボックスは正規表現（Regex）に対応しています。例えば `"gtceu:.*ore"` と入力するとGregTechのすべての鉱石を取得できます。
正規表現の習得は読者の課題とします。

# ターミナル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

基本的なターミナルで、ネットワークの[ストレージ](../ae2-mechanics/import-export-storage.md)の内容を閲覧・操作したり、[自動クラフト](../ae2-mechanics/autocrafting.md)を要求したりできます。

## UI

通常のターミナルUIにはいくつかのセクションがあります。

中央部分ではネットワークのストレージにアクセスできます。アイテムの出し入れが可能です。いくつかのマウス操作・キー操作があります：

* 左クリックでスタック取得、右クリックで半スタック取得
* アイテム・液体などが[自動クラフト](../ae2-mechanics/autocrafting.md)可能な場合、「ブロックを取得」に割り当てられているキー（通常は中クリック）でクラフト量指定UIを開けます。`3*64/2` のような数式や `=32` のように入力して指定量までクラフトすることも可能です。
* Shiftを押すと表示が固定され、アイテム数の変化や新規アイテム追加による並び替えを防ぎます
* バケツ等で右クリックすると液体を格納、空容器で液体を左クリックすると取り出し可能

左側には設定ボタンがあります：

* 名前・MOD・数量などでソート
* ストレージ／クラフト可能／両方の切り替え
* アイテム／液体／両方の切り替え
* ソート順変更
* 詳細設定ウィンドウを開く
* ターミナルUIの高さ変更

右側には<ItemLink id="view_cell" />スロットがあります。

中央右上のハンマーアイコンから[自動クラフト](../ae2-mechanics/autocrafting.md)ステータスUIを開き、クラフト進行状況や各[クラフトCPU](crafting_cpu_multiblock.md)の状態を確認できます。

## レシピ

<RecipeFor id="terminal" />

<a name="crafting-terminal-ui"></a>

# クラフトターミナル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/crafting_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

クラフトターミナルは通常のターミナルと同様の機能を持ちつつ、中央にクラフトグリッドが追加されています。このグリッドはネットワークの[ストレージ](../ae2-mechanics/import-export-storage.md)から自動で補充されます。出力アイテムのShiftクリックには注意してください。

ターミナルはできるだけ早くクラフトターミナルへアップグレードすることが推奨されます。

## UI

通常ターミナルと同様のUIに加えて、中央にクラフトグリッドが追加されています。

さらに2つの追加ボタンがあり、クラフトグリッドの内容をネットワークストレージまたはインベントリへ移動できます。

## レシピ

<RecipeFor id="crafting_terminal" />

<a name="pattern-encoding-terminal-ui"></a>

# パターンエンコーディングターミナル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_encoding_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

パターンエンコーディングターミナルは通常のターミナルと同様の機能に加え、[パターン](patterns.md)のエンコードUIを持ちます。クラフトターミナルに似ていますが、このクラフトグリッド自体は実際のクラフトを行いません。

クラフトターミナルと併用することが推奨されます。

## UI

通常ターミナルと同じUIに加え、[パターン](patterns.md)エンコードUIがあります。

エンコードUIには以下の要素があります：

* <ItemLink id="blank_pattern" />を挿入するスロット
* パターンをエンコードする大きな矢印ボタン
* 既存のエンコード済みパターンを編集するためのスロット

右側には4つのタブがあり、以下のモードを切り替えられます：

* クラフト
* 処理
* 鍛冶
* 石切り

中央UIはモードによって変化します：

* クラフトモード：
  * JEI/REIから材料を配置・削除してレシピを構成
  * 代替素材を有効化すると、任意の木材から棒を作るなどが可能（必要な場合のみ使用推奨）
  * 液体代替でバケツの代わりに液体を使用可能
  * JEI/REIレシピ画面から直接エンコード可能

* 処理モード：
  * JEI/REIまたは手動で入力・出力を設定
  * 液体コンテナで液体を直接指定可能
  * クリック操作でスタック単位・1個単位の調整、ピックブロックキーで正確な数量指定
  * 出力には副産物スロットあり
  * 最大81入力・26副産物までスクロール可能
  * JEI/REIから直接エンコード可能

* 鍛冶・石切りモードはそれぞれの作業台と同様のUI

## レシピ

<RecipeFor id="pattern_encoding_terminal" />

<a name="pattern-access-terminal-ui"></a>

# パターンアクセスターミナル

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/blocks/pattern_access_terminal.snbt" />
  <IsometricCamera yaw="180" />
</GameScene>

パターンアクセスターミナルは特定の問題を解決するために存在します。大量の<ItemLink id="pattern_provider" />や<ItemLink id="molecular_assembler" />が縦に積まれている場合、直接アクセスしてパターンを挿入することが困難です。また、拠点を移動するのが面倒な場合にも有効です。このターミナルを使うことで、ネットワーク上のすべてのパターンプロバイダにアクセスできます。

## UI

他のターミナルとは異なるUIを持ちます。

表示高さや表示対象のパターンプロバイダを設定できます。

各行は1つのパターンプロバイダに対応します。

パターンプロバイダは接続されているブロック、または金床や<ItemLink id="name_press" />で付けられた名前順でソートされます。

## レシピ

<RecipeFor id="pattern_access_terminal" />
