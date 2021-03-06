# QUASI-RECURRENT NEURAL NETWORKS

### Abstract
RNNはシーケンシャルなデータをモデリングするのに心強いツールだ。
しかし、直前のステップの出力との依存関係のせいで並列化に限界があり、長い実行時間のせいで扱いづらくなってしまっている。

そこで、私たちはQRNNを提案する。手法としてニューラルネットワークのモデリングに畳み込み層を繰り返す。それはタイムステップを無視し、チャネル間で並列に適用される最小限の反復プーリング機能です。

訓練可能な再帰層が欠けているにも関わらず、同じ層数のLSTMよりも優れた予測精度を有する。並行性が向上しているため、学習と試験時間で最大１６倍も高速です。


