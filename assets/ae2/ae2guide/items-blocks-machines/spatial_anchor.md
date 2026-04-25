---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: 空間アンカー
  icon: spatial_anchor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:spatial_anchor
---

# 空間アンカー

<BlockImage id="spatial_anchor" p:powered="true" scale="8"/>

AE2ネットワークは、その[デバイス](../ae2-mechanics/devices.md)が正常に動作するためにチャンクロードされている必要があります。一部だけが読み込まれている場合、正しく動作しない可能性があります。空間アンカーはこの問題を解決します。このブロックは、ネットワークが占有しているチャンクを強制ロードします。チャンク境界をまたぐケーブルが1本あるだけで、その新しいチャンクはロード対象になります。

この「ロード状態」は[量子ブリッジ](quantum_bridge.md)を越えて伝播しますが、異なる次元には適用されません。そのため、ネザーへ量子ブリッジで接続している場合、拠点側ネットワークとネザー側ネットワークの両方に空間アンカーが必要になります。

デフォルトでは、ロードされたチャンクでランダムティックも有効になりますが、これはAE2の設定で無効化できます。

また、<ItemLink id="certus_quartz_wrench" />を使うことで回転させることができます（何らかの理由で回転させたい場合）。

## 設定

* 空間アンカーは、AEまたはE/FEでエネルギーを表示するグローバル設定へのアクセスを提供します。
* ロードされているチャンクを表示するワールド内ホログラムを有効にできます。

## エネルギー

空間アンカーは以下の式に従って[エネルギー](../ae2-mechanics/energy.md)を消費します：

e = 80 + (x*(x+1))/2

ここで x はロードしているチャンク数です

## レシピ

<RecipeFor id="spatial_anchor" />
