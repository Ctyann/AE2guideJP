---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: レベルエミッター
  icon: level_emitter
  position: 220
categories:
- devices
item_ids:
- ae2:level_emitter
- ae2:energy_level_emitter
---

# レベルエミッター

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/level_emitter.snbt" />
</GameScene>

レベルエミッターは、[ネットワークストレージ](../ae2-mechanics/import-export-storage.md)内のアイテム量に応じて
レッドストーン信号を出力します。

ネットワーク内に蓄えられた[エネルギー](../ae2-mechanics/energy.md)量に応じて
レッドストーン信号を出力するバージョンも存在します。

実際にそのアイテムを所持していなくても、JEI/REIからアイテムや流体をスロットへドラッグできます。

バケツや流体タンクのような流体コンテナを持って右クリックすると、バケツやタンク自体ではなく、その中の流体をフィルターとして設定できます。

これは[ケーブルサブパーツ](../ae2-mechanics/cable-subparts.md)です。

他の[デバイス](../ae2-mechanics/devices.md)とは異なり、レベルエミッターは[チャンネル](../ae2-mechanics/channels.md)を*必要としません*。

## 設定

*   レベルエミッターは「以上」または「未満」モードに設定できます
*   <ItemLink id="crafting_card" />を挿入すると、「アイテムのクラフト中にレッドストーンを出力」または
    「レッドストーン出力でアイテムをクラフト」に設定できます

## アップグレード

レベルエミッターは以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="fuzzy_card" /> エミッターが耐久値でのフィルターや、アイテムNBTの無視を可能にします
*   <ItemLink id="crafting_card" /> クラフト機能を有効化します

## クラフト機能

<ItemLink id="crafting_card" />を挿入すると、エミッターはクラフトモードに切り替わります。

これにより2つの設定が有効になります。

1つ目の「アイテムのクラフト中にレッドストーンを出力」は、[自動クラフト](../ae2-mechanics/autocrafting.md)が
<ItemLink id="pattern_provider" />を通じて特定アイテムをクラフトしている間、エミッターがレッドストーン信号を出力します。
これは、電力消費の大きい自動化設備を実際に使用中の時だけ稼働させるのに役立ちます。

2つ目の「レッドストーン出力でアイテムをクラフト」は、無限農場や、確定出力ではなく確率でしか出力が得られない
自動化設備のような特定用途で非常に有用です。
この設定は、エミッターのフィルタースロットに入っているアイテム用の仮想[パターン](patterns.md)を、
[自動クラフト](../ae2-mechanics/autocrafting.md)用に作成します。
(正しく機能させるため、同じアイテムの実際のパターンは<ItemLink id="pattern_provider" />内に**存在しない**ようにしてください)

この「パターン」は、材料を定義せず、そもそも材料を気にしません。
ただ言っていることは「このレベルエミッターからレッドストーンを出力すれば、MEシステムは近い将来または遠い将来のどこかで
このアイテムを受け取る」ということだけです。これは通常、入力素材を必要としない無限農場の起動・停止や、
標準の自動クラフトでは理解できない[再帰レシピを処理するシステム](../example-setups/recursive-crafting-setup.md)の起動に使われます。
たとえば、丸石を複製するマシンがある場合の「丸石1個 = 丸石2個」のようなものです。

## レシピ

<RecipeFor id="level_emitter" />

<RecipeFor id="energy_level_emitter" />
