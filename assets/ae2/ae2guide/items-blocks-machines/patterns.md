---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: パターン
  icon: crafting_pattern
  position: 410
categories:
- tools
item_ids:
- ae2:blank_pattern
- ae2:crafting_pattern
- ae2:processing_pattern
- ae2:smithing_table_pattern
- ae2:stonecutting_pattern
---

# パターン

<ItemImage id="crafting_pattern" scale="4" />

パターンは<ItemLink id="pattern_encoding_terminal" />でブランクパターンから作成し、<ItemLink id="pattern_provider" />や
<ItemLink id="molecular_assembler" />に挿入します。

用途に応じていくつかの異なる種類のパターンがあります:

*   <ItemLink id="crafting_pattern" />は作業台で作成されるレシピを記録します。直接<ItemLink id="molecular_assembler" />に入れることで、
    材料が与えられるたびに結果をクラフトさせることができますが、主な用途は分子組立機の隣に置かれた<ItemLink id="pattern_provider" />です。
    この場合、パターンプロバイダーは特別な動作を行い、隣接する組立機へ材料と一緒に対応するパターンを送信します。
    組立機はクラフト結果を自動的に隣接インベントリへ排出するため、クラフトパターンの自動化に必要なのはパターンプロバイダー上の組立機だけです。

***

*   <ItemLink id="smithing_table_pattern" />はクラフトパターンと非常によく似ていますが、鍛冶台のレシピを記録します。これもパターン
    プロバイダーと分子組立機によって自動化され、まったく同じように機能します。実際、クラフト、鍛冶、石切りパターンは
    同じ構成で使用できます。

***

*   <ItemLink id="stonecutting_pattern" />はクラフトパターンと非常によく似ていますが、石切り機のレシピを記録します。これもパターン
    プロバイダーと分子組立機によって自動化され、まったく同じように機能します。実際、クラフト、鍛冶、石切りパターンは
    同じ構成で使用できます。

***

*   <ItemLink id="processing_pattern" />は、自動クラフトにおける柔軟性の大部分を担うものです。最も汎用的な種類であり、単純に
    「パターンプロバイダーがこれらの材料を隣接インベントリへ押し出した場合、MEシステムは近い将来または遠い将来のどこかで
    これらのアイテムを受け取る」と定義します。これはほぼあらゆるMod機械や、かまどのような装置で自動クラフトを行う方法です。
    用途が非常に汎用的で、材料を押し出してから結果を受け取るまでの間に何が起こるかを気にしないため、かなり変わったこともできます。たとえば、
    材料を巨大で複雑な工場生産ライン全体へ投入し、そこで仕分けを行い、無限生産農場から他の材料を取り込み、
    Bee Movieの台本全文を印刷したとしても、MEシステムはパターンで指定された結果を受け取りさえすれば気にしません。実際のところ、
    材料と結果に関連性があるかどうかすら気にしません。たとえば「サクラの板材1 = ネザースター1」と設定し、
    サクラの板材を受け取ったウィザー農場がウィザーを倒すようにしても機能します。

同一パターンを持つ複数の<ItemLink id="pattern_provider" />にも対応しており、並列動作します。さらに、たとえば
「丸石8 = 石8」とパターンを設定することもでき、その場合パターンプロバイダーは製錬設備へ丸石を1個ずつではなく
1回の処理で8個まとめて投入します。

## レシピ

<RecipeFor id="blank_pattern" />
