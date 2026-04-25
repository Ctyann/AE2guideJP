---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 振動チャンバー
  icon: vibration_chamber
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:vibration_chamber
---

# 振動チャンバー

<BlockImage id="vibration_chamber" p:active="true" scale="8" />

AEネットワークへの[エネルギー](../ae2-mechanics/energy.md)供給の主な手段は<ItemLink id="energy_acceptor" />ですが、振動チャンバーは少量から中程度のAEを直接生成することができます。

デフォルト状態（アップグレードなし、設定デフォルト）では40 AE/tを生成します。

ネットワークの[エネルギー](../ae2-mechanics/energy.md)ストレージが満杯になると、振動チャンバーは燃料消費を抑えるために出力を抑制しますが、完全に停止することはありません。

## 設定

*   振動チャンバーはグローバル設定として、エネルギー表示をAEまたはE/FEで切り替える機能にアクセスできます。

## アップグレード

振動チャンバーは以下の[アップグレード](upgrade_cards.md)に対応しています：

*   <ItemLink id="energy_card" />：チャンバーの効率を+50%向上（最大+150%、ベースの250%まで）
*   <ItemLink id="speed_card" />：チャンバーの燃焼速度を+50%向上（最大+150%、ベース出力の250%まで）

## 設定ファイル

振動チャンバーの特性は、`.minecraft`ディレクトリ内の`ae2`フォルダにある`config`内の`common.json`で編集できます。

*   `baseEnergyPerFuelTick`：振動チャンバーの基本効率（未強化状態）
*   `minEnergyPerGameTick`：最小エネルギー生成量（ネットワークがエネルギーを必要としない場合でも、チャンバーはわずかに燃料を消費します）
*   `maxEnergyPerGameTick`：未強化状態での最大出力（および速度）

## レシピ

<RecipeFor id="vibration_chamber" />
