---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 分子組立機
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# 分子組立機

<BlockImage id="molecular_assembler" scale="8" />

分子組立機は、投入されたアイテムを受け取り、隣接する<ItemLink id="pattern_provider" />または挿入された
<ItemLink id="crafting_pattern" />、<ItemLink id="smithing_table_pattern" />、<ItemLink id="stonecutting_pattern" />で定義された処理を実行し、
その結果を隣接インベントリへ送り出します。

この組立機には「オークの原木1個 = オークの板材4個」のレシピを指定したクラフトパターンが設定されています。上部のホッパーからオークの原木を投入すると、
組立機がクラフトを行い、下部のホッパーへオークの板材を排出します。

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/standalone_assembler.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## 分子組立機の主な用途

ただし、主な用途は<ItemLink id="pattern_provider" />の隣に設置することです。この場合、パターンプロバイダーは特別な動作を行い、
対応するパターン情報を材料と一緒に隣接する組立機へ送信します。組立機はクラフト結果を自動で隣接インベントリへ排出し
(そのためパターンプロバイダーの返却スロットへ戻ります)、パターンプロバイダーに接続された組立機だけで
クラフトパターンの自動化が可能になります。

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## アップグレード

分子組立機は以下の[アップグレード](upgrade_cards.md)に対応しています。

*   <ItemLink id="speed_card" />

## レシピ

<RecipeFor id="molecular_assembler" />

## 注意

Optifineは「隣接インベントリへ送り出す」機能を壊すため、組立機を使った多くのクラフト構成は動作しません。
