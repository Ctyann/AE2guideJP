---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: クラフティングCPUマルチブロック（ストレージ、コプロセッサ、モニター、ユニット）
  icon: 1k_crafting_storage
  position: 210
categories:
- devices
item_ids:
- ae2:1k_crafting_storage
- ae2:4k_crafting_storage
- ae2:16k_crafting_storage
- ae2:64k_crafting_storage
- ae2:256k_crafting_storage
- ae2:crafting_accelerator
- ae2:crafting_monitor
- ae2:crafting_unit
---

# クラフティングCPU

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="crafting_accelerator" scale="4" />

  <BlockImage id="crafting_monitor" scale="4" />

  <BlockImage id="crafting_unit" scale="4" />
</Row>

クラフティングCPUはクラフティングリクエスト/ジョブを管理します。複数のステップを持つクラフティングジョブの中間材料を保存し、ジョブの規模やある程度の速度に影響を与えます。[自動クラフティング](../ae2-mechanics/autocrafting.md)を参照してください。

各クラフティングCPUは1つのリクエストまたはジョブを処理します。そのため、計算プロセッサと256個のスムースストーンを同時にリクエストしたい場合、2つのCPUマルチブロックが必要です。

これらはプレイヤー、オートメーション（MEエクスポートバスやMEインターフェース）またはその両方からのリクエストを処理するように設定できます。

右クリックすると、CPUが処理しているクラフティングジョブの進行状況を確認できるクラフティングステータスUIが表示されます。

## 設定

* CPUは、プレイヤーからのリクエスト、オートメーション（<ItemLink id="export_bus" />に<ItemLink id="crafting_card" />を使用）からのリクエスト、またはその両方を受け入れるように設定できます。

## 構築

クラフティングCPUはマルチブロックであり、隙間のない直方体でなければなりません。いくつかのコンポーネントで構成されています。

各CPUには少なくとも1つのクラフティングストレージブロックが必要です（最小構成のCPUは、実際には1つの1kクラフティングストレージだけです）。

# クラフティングユニット

<BlockImage id="crafting_unit" scale="4" />

（オプション）クラフティングユニットは、他のコンポーネントが不足している場合に、CPUを隙間のない直方体にするためのスペースを埋めるだけのものです。また、他のコンポーネントの基本材料としても使用されます。

<RecipeFor id="crafting_unit" />

# クラフティングストレージ

<Row>
  <BlockImage id="1k_crafting_storage" scale="4" />

  <BlockImage id="4k_crafting_storage" scale="4" />

  <BlockImage id="16k_crafting_storage" scale="4" />

  <BlockImage id="64k_crafting_storage" scale="4" />

  <BlockImage id="256k_crafting_storage" scale="4" />
</Row>

（必須）クラフティングストレージは、すべての標準セルサイズ（1k、4k、16k、64k、256k）で利用可能です。これらはクラフティングに必要な材料や中間材料を保存するため、大きなジョブを処理するにはより大きなストレージまたは複数のストレージが必要です。

<Column>
  <Row>
    <RecipeFor id="1k_crafting_storage" />

    <RecipeFor id="4k_crafting_storage" />

    <RecipeFor id="16k_crafting_storage" />
  </Row>

  <Row>
    <RecipeFor id="64k_crafting_storage" />

    <RecipeFor id="256k_crafting_storage" />
  </Row>
</Column>

# クラフティングコプロセッシングユニット

<BlockImage id="crafting_accelerator" scale="4" />

（オプション）クラフティングコプロセッサは、CPUの動作速度を上げることで、<ItemLink id="pattern_provider" />からの材料バッチをより頻繁に送信できるようにします。
これにより、高速で処理するマシンに対応できます。例として、<ItemLink id="molecular_assembler" />に囲まれたMEパターンプロバイダーが、単一の分子組立機が処理できる速度を超えて材料をプッシュし、周囲の分子組立機間で材料バッチを分配することができます。

一部の複雑なレシピには、並行して実行できる複数のステップがあります。たとえば、本棚を作るために板材と本を同時に作ることができます。
クラフティングステータス画面（CPUを右クリックするか、[端末](terminals.md)のハンマーアイコンで表示）では、これらのステップはすべて「スケジュール済み」として表示されます。追加のコプロセッサごとに、これらのステップの1つを並行して実行できるようになります（「クラフティング中」として表示されます）。
ただし、通常は挿入速度のためにコプロセッサを追加することが多く、レシピが並行して実行できるステップ数よりも多くなることが一般的です。

<RecipeFor id="crafting_accelerator" />

# クラフティングモニター

<BlockImage id="crafting_monitor" scale="4" />

（オプション）クラフティングモニターは、CPUが現在処理しているジョブを表示します。
画面は<ItemLink id="color_applicator" />で色を付けることができます。

<RecipeFor id="crafting_monitor" />
