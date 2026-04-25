---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: マターキャノン
  icon: matter_cannon
  position: 410
categories:
- tools
item_ids:
- ae2:matter_cannon
---

# マターキャノン

<ItemImage id="matter_cannon" scale="4" />

マターキャノンは携帯型レールガンで、<ItemLink id="matter_ball" />や金属ナゲットのような小さなアイテムを投射物として発射できます。
ダメージは発射するアイテムに依存し、金ナゲット(10ダメージ)のような「重い」アイテムほど、マターボール(2ダメージ)のような軽いアイテムより高ダメージになります。
1発ごとに基本1600 AEを消費します。

設定項目「matterCannonBlockDamage」がtrueの場合、キャノンはブロックの硬さと弾薬のダメージに応じてブロックを破壊できます。

エネルギーは<ItemLink id="charger" />で再充電できます。

マターキャノンは[ストレージセル](storage_cells.md)のように動作し、弾薬マガジンは
<ItemLink id="chest" />のストレージセルスロットに差し込むことで最も簡単に補充できます。

## アップグレード

マターキャノンは、<ItemLink id="cell_workbench" />から挿入する以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="fuzzy_card" /> セルが耐久値でのパーティションや、アイテムNBTの無視を可能にします
*   <ItemLink id="inverter_card" /> フィルターをホワイトリストからブラックリストへ切り替えます
*   <ItemLink id="speed_card" /> 1発ごとの消費エネルギーを増やし、より高威力で発射します
*   <ItemLink id="void_card" /> セルが満杯の時、挿入されたアイテムを消去します。必ずパーティション設定してください
*   <ItemLink id="energy_card" /> バッテリー容量を増加させます

## レシピ

<RecipeFor id="matter_cannon" />
