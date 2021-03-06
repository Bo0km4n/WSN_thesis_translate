## 1.
私はそれらを流れるメッセージ上でカスタマイズされた計算を実行します。例えば、アクティブネットワークのユーザは、各ルータに「トレース」プログラムを送信し、パケットが処理されるときに実行されるようにプログラムを配置することができる。
図1は、IPネットワークのルータが、それらを流れるデータグラム上でそのようなカスタマイズされた処理を実行するためにどのように拡張されるかを示す。
これらのアクティブルータは、伝統的な方法で透過的にデータグラムをフォワードするレガシールータと相互運用することもできます。
これらのネットワークは、ノードがパケットの内容を計算し、変更することができるという意味で有効です。
さらに、この処理は、ユーザー単位またはアプリケーション単位でカスタマイズできます。対照的に、インターネットのような従来のパケットネットワーク内での計算の役割は極めて限られている。
ルータはパケットのヘッダーを変更するかもしれませんが、検査や修正を行うことなく不透明にユーザーデータを渡します。
さらに、ヘッダ計算および関連するルータ動作は、パケットを生成するユーザプロセスまたはアプリケーションとは独立して指定される。

活発なネットワーキングの概念は、1994年と1995年に、ネットワークシステムの将来の方向性に関する広範な国防総省高度研究プロジェクト庁（DARPA）の研究コミュニティ内での議論から浮上した。
現在のネットワークに関するいくつかの問題が特定されました。新しいテクノロジと標準を共有ネットワークインフラストラクチャに統合することの難しさ、いくつかのプロトコルレイヤでの冗長運用によるパフォーマンスの低下、既存のアーキテクチャモデルにおける新しいサービスの適応の難しさです。
アクティブネットワーキングと総称されるいくつかの戦略が、これらの問題に対処するために浮かび上がった。
手順とデータを運ぶメッセージのアイデアは、伝統的な回路とパケットのスイッチングを超えたナショナルステップであり、変化する要求にネットワークを迅速に適応させるために使用できます。
このプログラムベースのアプローチは、ネットワークノード内のよく理解された実行環境と結合して、ネットワーキングシステムを、特定の特性を持つ多くの小さなコンポーネントの構成として表現するための基盤を提供します。アプリケーションは、アプリケーションのニーズを満たすように分散および構成でき、個々のコンポーネントの特性に関してネットワークの全体的な動作について行われる必要があります。

この記事では、アクティブなネットワークの実現に向けた2つのアプローチについて説明します。
プログラマブルスイッチアプローチは、既存のパケットフォーマットを維持し、プログラムのダウンロードをサポートする個別のメカニズムを提供する。 プログラムの注入をメッセージの処理から分離することは、プログラムの選択が個々のエンドユーザではなくネットワーク管理者によって行われる場合に特に魅力的であり得る。
対照的に、カプセルアプローチはいくらか進んで行く。現在のアーキテクチャの受動的パケットは、送信フレームにカプセル化され、その経路に沿って各ノードで実行されるアクティブな小型プログラムに置き換えられる。 
ユーザデータは、ページの内容がPostScriptコードの断片に埋め込まれるのと同じように、これらのカプセルに埋め込むことができます。

能動的なネットワークの研究は、技術の「プッシュ」とユーザーの「プル」の両方によって動機づけられます。
「プル」は、ユーザー主導のファイアウォール、Webプロキシ、マルチキャストルータ、モバイルプロキシ、ビデオゲートウェイなどのさまざまな種類のものです
ネットワーク内のノードでの計算。 これらのリードユーザーの一部は表1で説明されています。
多くの場合、これらのサービスはファイアウォールなどのノードで実装され、ルータのファサードを採用しますが、従来のアーキテクチャ上のガイドラインを超えたアプリケーション固有の処理を実行します。
私たちの目標は、ネットワークベースの計算に対するさまざまなアドホックなアプローチを、ユーザーがネットワークをプログラムできるようにする一般的な機能で置き換えることです。

テクノロジーの「プッシュ」は、私たちの目標を達成するためのアクティブな技術の出現です。 最近まで、管理者（エンドユーザーはもちろんのこと）のネットワークをプログラミングすることは、インフラの安全性と効率性に関して懸念されていました。
しかし、プログラミング言語、コンパイラ、およびオペレーティングシステムの近年の進歩により、モバイルプログラムのフラグメントを安全かつ効率的に実行するための鍵が提供される可能性があります。
現在、これらのアクティブな技術は、個々のエンドシステム内でエンドツーエンドのネットワークレイヤ（例えば、ウェブサーバとクライアントがJavaアプレットを交換できるようにする）の上に適用される。
アクティブなネットワークは、ネットワーク内での使用について根本的に私たちの考え方を変える方法で、これらのテクノロジを活用して拡張します。

この記事では、アクティブなネットワーク研究活動の現在のスナップショットを提供しています。
次の2つのセクションでは、アクティブネットワークがインフラストラクチャの革新に与える影響と、有効になる新しいアプリケーションについて説明します。 次に、フィールド内での活動の分類と整理に使用できるフレームワーク、または一連の問題を提示します。
最後に、私たちは現在の研究活動を自社の研究所や地域の他の場所で調査します。

## ACCELERATING INFRASTRUCTURE INNOVATION
ネットワーク内で既に起こっていることがあります。 これらのサービスに対する実証済みの要求は、ネットワークアーキテクチャがこの新しい現実に対処するために適応しなければならないことを示唆しています。
より基本的なレベルでは、ネットワークの革新プロセス自体が更新のために熟しています。 ネットワークの革新のペースはあまりにも遅いです。 インターネットが成長するにつれ、このペースを維持することはもちろん、それを加速することはますます困難になっています。
大体において、これはコンセンサスを達成する必要性の関数です。ネットワークの有用性は、相互接続されたノードの数とともに増加します。
今日、プロトタイプのデモンストレーションから大規模な展開までの道のりは、約10年かかります。
このプロセスには、標準化、ベンダーのハードウェアプラットフォームへの組み込み、ユーザーの調達、およびインストールが含まれます。
現在のインターネットサービスのバックログには、マルチキャスト、認証およびモビリティ拡張、予約プロトコル（RSVP）、インターネットプロトコルバージョン6（IPv6）が含まれます。

IPは、標準的なパケットフォーマットとアドレス指定方式を定義することによって相互運用性を可能にします。 ルータの実装は異なるかもしれませんが、おおまかに「同等の」プログラムを実装します。
したがって、IP革新の仕組みはIPサービスを変えています。これはすべてを変えることです（相互運用性の基礎であるため）。 またはオーバーレイ（例えば、MBone）を確立する。

対照的に、アクティブノードは多くの異なるプログラムを実行することができます。 つまり、それらのパケットを流れるパケットごとに非常に異なる計算を実行できます。 アクティブなネットワークは、すべてのルータがすべてのパケットに対して「同等の」計算を実行することを主張する代わりに、すべてのノードが同等の計算モデル（すなわち、仮想命令セット）をサポートすることを指定する。
アクティブなネットワークは、相互運用性が実現される抽象度を高め、アプリケーションが目的に合ったメッセージ処理をカスタマイズできるようにします。

インフラストラクチャに新しいサービスをダウンロードする機能は、新しいサービスの可用性が市場で受け入れられるかどうかに依存するユーザー主導のイノベーションプロセスにつながります。
能動的なネットワークは、ハードウェアとソフトウェアが一緒に束ねられた「メインフレーム」の考え方から、ハードウェアとソフトウェアの革新が分離された「仮想化された」アプローチにネットワーキング産業の構造を変える機会を提示している[7]。
ネットワークプログラミングの抽象化は、インフラストラクチャのユーザー主導のカスタマイズのための強力なプラットフォームを提供し、ベンダー主導のコンセンサスや標準化活動よりも速いペースで新しいサービスを展開できるようにします。

## ENABLING NEW APPLICATION
アクティブなネットワークは、情報のネットワークベースのマージ、ユーザー対応のネットワーク保護、およびアクティブなネットワーク管理に依存する新しいアプリケーションを可能にします。 

### MERGING AND DISTRIBUTION OF lNFORMATlON 
マルチユーザ、マルチサイトアプリケーションの時代が始まったばかりです。 MBoneとWebの成功は、何が先にあるかもしれないのだろうか。
情報の統合と配布をサポートするためにネットワークベースのサービスを必要とするアプリケーションの未使用のリザーバがあります。
しかしながら、既存のシステムは、ネットワークベースの記憶装置または情報融合にとどまらず、アプリケーション特有の配信をサポートすることなく、極めて限定された機能（すなわち、IPパケットのコピー）を提供するサービスに基づいている。

図2は、高度なマルチサイトアプリケーションがネットワーク内の計算とストレージをどのように活用するかを示しています。
この図では、シミュレーションや遠隔操作などのアプリケーションにより、各ユーザーは、多数のセンサーから得られた情報を融合して構成された合成画像を「見る」ことができます。
さらに、各センサは、アクセスする情報の符号化および提示に関する異なる要件を有する多数のユーザによって「監視」されることが可能である。
ネットワーク内のデータをマージすることにより、ネットワークの（低帯域幅）周辺に位置するユーザの帯域幅要件が低減される。
同様に、ネットワーク内のユーザ固有のマルチキャストサービスは、センサとネットワークバックボーンの負荷を軽減します。

情報のページをキャッシュするウェブプロキシは、ネットワークベースの計算および記憶の恩恵を受けることができるマルチユーザサービスの別の例である。
Harvest [a]は、個々のユーザーが経験するレイテンシと消費される総帯域幅を削減できる階層型キャッシュ方式を採用しています。
キャッシュノードは、現在、ネットワークのエッジの近く、すなわち、エンドユーザ組織内のノードに配置されている。
これらのシステムは、階層のノードがインターネット・アクセス・プロバイダおよびインターチェンジャー・キャリアのネットワーク内の戦略的ポイントに位置することを可能にすることによって拡張することができる。
興味深い問題は、キャッシュされた情報だけでなく、キャッシュ自体の位置を変更して階層を自動的に「均衡させる」アルゴリズムとツールの開発です。
Webキャッシングにアクティブなテクノロジを使用することを支持するもう一つの議論は、Webページのかなりの部分が動的に計算され、パッシブキャッシングの影響を受けないことです。
これは、これらのページを生成するプログラムを格納して実行するアクティブなキャッシュをサポートするスキームの開発を示唆しています。

### USER-AWARE NTWORK PROTECTIO
情報の保護とは、正しい情報が適切な場所と時間に適切な人に届くことを意味します。
多くのネットワーキングフォーラムでは、ネットワークセキュリティと認証メカニズムが提案されていますが、アクティブネットワーキングでは、すべてのネットワークリソースとそれらを流れる情報を管理する統合メカニズムの設計が認められます。 
これにより、各通信プロトコル層で独立して動作する複数のセキュリティ認証システムの必要性が排除される。
これにより、ユーザーごとまたは使用ごとにネットワークのセキュリティポリシーをプログラムすることができます。
最後に、厳格な仕様と言語強制型の安全性を使用した正式なアプローチを使用して、保護方針とその実装の仕組みを推論することができます。

### ACTIVE NETWORK MANAGEME
多くのネットワーク管理タスクは、イベント数などのデータの収集と照合から構成されます。
例外表示などの最も有用なネットワーク管理データを提供するには、無関係な（例外ではない）イベントをフィルタリングするためにインテリジェンスを使用する必要があります。
アクティブなテクノロジーを使用して、ネットワーク監視とイベントフィルタリングに対する洗練されたアプローチを実装することができます。
ルータなどのネットワーク構成要素は、（例えば、カスタマイズされた監視および診断プログラムをそれらの最も近い近隣に注入することによって）監視するためのある程度の責任を負うことさえある。
同様に、アクティブなネットワークは、障害検出を改善し、地震や悪意のある侵入者などの相関障害に対するコンポーネントの応答を管理するサバイバビリティポリシーを更新するために必要な柔軟性を提供します。
