---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: アップグレードカード
  icon: speed_card
  position: 410
categories:
- tools
item_ids:
- ae2:basic_card
- ae2:advanced_card
- ae2:redstone_card
- ae2:capacity_card
- ae2:void_card
- ae2:fuzzy_card
- ae2:speed_card
- ae2:inverter_card
- ae2:crafting_card
- ae2:equal_distribution_card
- ae2:energy_card
---

# アップグレードカード

<Row>
  <ItemImage id="redstone_card" scale="2" />

  <ItemImage id="capacity_card" scale="2" />

  <ItemImage id="void_card" scale="2" />

  <ItemImage id="fuzzy_card" scale="2" />

  <ItemImage id="speed_card" scale="2" />

  <ItemImage id="inverter_card" scale="2" />

  <ItemImage id="crafting_card" scale="2" />

  <ItemImage id="equal_distribution_card" scale="2" />

  <ItemImage id="energy_card" scale="2" />
</Row>

アップグレードカードはAE2の[デバイス](../ae2-mechanics/devices.md)や各種機械の動作を変更し、速度の向上、フィルタ容量の拡張、レッドストーン制御の追加などを行います。

## カードコンポーネント

<Row>
  <ItemImage id="basic_card" scale="2" />

  <ItemImage id="advanced_card" scale="2" />
</Row>

カードは基本カードまたは高度カードのベースから作成されます。

<Row>
  <RecipeFor id="basic_card" />

  <RecipeFor id="advanced_card" />
</Row>

## レッドストーンカード

<ItemImage id="redstone_card" scale="2" />

レッドストーンカードはレッドストーン制御を追加し、デバイスGUIにトグルボタンを追加して、さまざまなレッドストーン条件を切り替えられるようにします。

<RecipeFor id="redstone_card" />

## 容量カード

<ItemImage id="capacity_card" scale="2" />

容量カードはインポートバス・エクスポートバス・ストレージバス・フォーメーションプレーンのフィルタスロット数を増加させます。

<RecipeFor id="capacity_card" />

## オーバーフロー破壊カード

<ItemImage id="void_card" scale="2" />

オーバーフロー破壊カードは[ストレージセル](storage_cells.md)に対して<ItemLink id="cell_workbench" />で適用でき、セルが満杯の場合に入力されたアイテムを削除します。（セルは必ず[パーティション](cell_workbench.md)してください！）
さらにイコールディストリビューションカードと併用すると、特定アイテム用に割り当てられた領域が満杯の場合、そのアイテムのみが削除されます。

<RecipeFor id="void_card" />

## フジーカード

<ItemImage id="fuzzy_card" scale="2" />

フジーカードはデバイスやツールのフィルタリングを強化し、耐久値やNBTを無視した検索を可能にします。
これにより、ダメージ値に関係なくすべての鉄の斧を対象にしたり、完全修復されていないダイヤモンド剣のみを抽出するなどが可能になります。

以下はフジーダメージ比較の例で、左がバス設定、上が比較対象アイテムです。

| 25%                    | 10%ダメージピッケル | 30%ダメージピッケル | 80%ダメージピッケル | フル修復ピッケル |
| ---------------------- | ------------------- | ------------------- | ------------------- | ---------------- |
| ほぼ破損ピッケル        | ✅                   | \*\*\*\*            | \*\*\*\*            | \*\*\*\*          |
| 完全修復ピッケル        | \*\*\*\*            | ✅                   | ✅                   | ✅                |

| 50%                    | 10%ダメージピッケル | 30%ダメージピッケル | 80%ダメージピッケル | フル修復ピッケル |
| ---------------------- | ------------------- | ------------------- | ------------------- | ---------------- |
| ほぼ破損ピッケル        | ✅                   | ✅                   | \*\*\*\*            | \*\*\*\*          |
| 完全修復ピッケル        | \*\*\*\*            | \*\*\*\*            | ✅                   | ✅                |

| 75%                    | 10%ダメージピッケル | 30%ダメージピッケル | 80%ダメージピッケル | フル修復ピッケル |
| ---------------------- | ------------------- | ------------------- | ------------------- | ---------------- |
| ほぼ破損ピッケル        | ✅                   | ✅                   | \*\*\*\*            | \*\*\*\*          |
| 完全修復ピッケル        | \*\*\*\*            |                     | ✅                   | ✅                |

| 99%                    | 10%ダメージピッケル | 30%ダメージピッケル | 80%ダメージピッケル | フル修復ピッケル |
| ---------------------- | ------------------- | ------------------- | ------------------- | ---------------- |
| ほぼ破損ピッケル        | ✅                   | ✅                   | ✅                   | \*\*\*\*          |
| 完全修復ピッケル        | \*\*\*\*            | \*\*\*\*            | \*\*\*\*            | ✅                |

| 無視                   | 10%ダメージピッケル | 30%ダメージピッケル | 80%ダメージピッケル | フル修復ピッケル |
| ---------------------- | ------------------- | ------------------- | ------------------- | ---------------- |
| ほぼ破損ピッケル        | ✅                   | ✅                   | ✅                   | **✅**            |
| 完全修復ピッケル        | **✅**               | **✅**               | **✅**               | ✅                |

<RecipeFor id="fuzzy_card" />

## 加速カード

<ItemImage id="speed_card" scale="2" />

加速カードは動作速度を向上させ、インポート・エクスポートバスの転送量を増加させたり、インサイバーやアセンブラーの処理速度を上げます。

<RecipeFor id="speed_card" />

## 反転カード

<ItemImage id="inverter_card" scale="2" />

反転カードはデバイスやツールのフィルタをホワイトリストからブラックリストへ切り替えます。

<RecipeFor id="inverter_card" />

## クラフトカード

<ItemImage id="crafting_card" scale="2" />

クラフトカードはデバイスに[自動クラフト](../ae2-mechanics/autocrafting.md)システムへのクラフト要求機能を追加します。

<RecipeFor id="crafting_card" />

## 均等分配カード

<ItemImage id="equal_distribution_card" scale="2" />

均等分配カードは<ItemLink id="cell_workbench" />を通じて[ストレージセル](storage_cells.md)に適用でき、指定されたアイテムごとにセル容量を均等に分割します。これにより、単一アイテムがセル全体を占有することを防ぎます。

<RecipeFor id="equal_distribution_card" />

## エネルギーカード

<ItemImage id="energy_card" scale="2" />

エネルギーカードはポータブル端末などの一部ツールのエネルギー容量を増加させ、<ItemLink id="vibration_chamber" />の効率を向上させます。

<RecipeFor id="energy_card" />
