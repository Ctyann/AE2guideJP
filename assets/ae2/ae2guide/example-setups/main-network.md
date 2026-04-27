---
navigation:
  parent: example-setups/example-setups-index.md
  title: メインネットワークの例
  icon: controller
---

# メインネットワークの例

これまでの多くの構成では「メインネットワーク」という言葉が登場します。また、これらの[デバイス](../ae2-mechanics/devices.md)が実際にどのように組み合わさって動作するのか疑問に思うこともあるでしょう。ここではその一例を示します。

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/small_base_network.snbt" />

    <BoxAnnotation color="#33dd33" min="5 1 10" max="9 7 14" thickness="0.05">
        パターンプロバイダとアセンブラが密集しており、クラフト・石切り・鍛冶用のパターンを大量に処理できるスペースになっている。
        市松模様の配置により、複数のアセンブラへ並列処理しつつコンパクトに収まる。
        8個単位のグループ構成にすることで、チャンネルのルーティングミスを防いでいる。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="13 10 12" max="14 11 14" thickness="0.05">
        実際にはここまで大きなコントローラは必要なく、よく見かける巨大なリングや立方体のデザインは主に見た目のためである。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="13 12 13" max="14 13 14" thickness="0.05">
        すべての良いネットワークにはエネルギーセルがあり、単位ティックあたりの電力供給上限を引き上げ、電力変動を吸収する役割を持つ。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="2 1 10" max="4 4 13" thickness="0.05">
        AE2は基本的に他MODと併用する設計のため、バニラの振動チェンバーよりも、リアクターやソーラーパネルなど外部発電を使うのが推奨される。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="15 1 9" max="16 3 14" thickness="0.05">
        ファサードは内部配線を壁の中に隠すために使える。
    </BoxAnnotation>
    <BoxAnnotation color="#33dd33" min="15 3 12" max="16 10 14" thickness="0.05">
        ファサードは内部配線を壁の中に隠すために使える。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="13 9 7" max="14 10 9" thickness="0.05">
        一般的なストレージ用途では、ドライブ2〜4台程度と4kまたは16kセルで十分なことが多い。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="13 9 10" max="14 11 11" thickness="0.05">
        バルクストレージには、特定アイテム専用のフィルタ付き大容量セルを優先度を上げて分離して使う。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="10 9 13" max="11.7 13 14" thickness="0.05">
        MEインターフェースを使った自動補充システム。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="6 10 12" max="9 12 15" thickness="0.05">
        チャージャー自動化の拡張構成（複数チャージャー対応）。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="2 10 12" max="5 11 15" thickness="0.05">
        インサーターの自動排出機能を利用した別のプロセッサ自動化方式（1.20以降）。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="3 10 10" max="4 12 11" thickness="0.05">
        同じくプロセッサ自動化の別構成（1.20以降のインサーター対応）。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="7.2 9.2 8.2" max="7.8 10 8.8" thickness="0.05">
        ワイヤレスアクセスポイントは範囲が球状のため中心に配置されている。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="14 1 2" max="16 5 7" thickness="0.05">
        通常、大規模クラフト用に1〜2基の大型CPUを用意し、他に小型CPUをいくつか配置して並列処理を行う。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="5 3 6" max="6 4 7" thickness="0.05">
        サブネットは、8デバイスを超えるような分配用途では独立したコントローラが必要になる場合がある。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="7.3 1 3.3" max="9.7 4 6" thickness="0.05">
        セルツファーム。
    </BoxAnnotation>

    <BoxAnnotation color="#33dd33" min="10.3 1 2.3" max="12.7 3.7 5" thickness="0.05">
        水投入系オートメーション。
    </BoxAnnotation>

  <IsometricCamera yaw="135" pitch="15" />
</GameScene>
