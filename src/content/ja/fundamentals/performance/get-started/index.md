project_path: /web/fundamentals/_project.yaml
book_path: /web/fundamentals/_book.yaml

{# wf_updated_on: 2018-08-17 #}
{# wf_published_on: 2018-02-22 #}
{# wf_blink_components: Blink>PerformanceAPIs,Blink>JavaScript>Runtime #}

# 概要 {: .page-title }

{% include "web/_shared/contributors/dgash.html" %}

Web がブラウザアプリケーションプラットフォームへと進化するにつれて、アプリの用途のほとんどは、高速で信頼性の高いネットワーク接続を備えた強力なデスクトップマシンから、低速で信頼性の低い接続を備えた低電力モバイルデバイスへと移行しました。そのため、プラットフォーム、ネットワーク、またはデバイスに関係なく、速いアプリがより優れたアプリです。デスクトップユーザーを含め、読み込みと実行が高速なページを作成すると、誰もが利益を得ることができます。

幸いなことに、ページスピードを向上させる多くの効果的なテクニックが存在します。読み込み時間を9ミリ秒短縮するのに役立つ最先端の技術革新もありますが、パフォーマンスを大幅に向上させるための直接的で高度な方法も多数あります。このドキュメントセットについて説明します。

これまでパワフルで機能豊富なサイトを構築して展開するために使っていたプロセスは、特にモバイルデバイス上では読み込むにも使うにも遅い Web ページを生成します。読み込みの遅いページは、サイトを利用できない/利用しないユーザーにとってイライラするものであり、それらのユーザーを失う開発者にとっては悪いものです。例えば、さまざまな研究が共通の傾向を明らかにしています。

- 読み込み時間はページの離脱とロイヤリティの大きな要因です。53 ％ のユーザーが、ロードに 3 秒以上かかるサイトを離脱したと報告しています (出典: [SOASTA Google スタディレポート](https://soasta.com/blog/google-mobile-web-performance-study/))。

- ユーザーは、読み込みが遅いサイトよりも速いサイトを頻繁に訪問し、長く滞在し、検索を続け、頻繁に購入します。ある企業では、7 ％ のコンバージョンの増加は、0.85 秒という短いスピードの向上によってもたらされることを明らかにしました (出典: [WPO統計](https://wpostats.com/))。

- 遅い読み込みは検索エンジン最適化 (SEO) にとって有害です。なぜならそれはサイトのランキングを下げる可能性があり、その結果として訪問数、閲覧数、コンバージョン数が少なくなります。2018 年に、グーグルはモバイル検索におけるランキングシグナルとしてサイトスピードを実装するでしょう (出典: [Search Engine Land](https://searchengineland.com/google-speed-update-page-speed-will-become-ranking-factor-mobile-search-289904))。

Google は、[Mobile Speed Matters](https://www.doubleclickbygoogle.com/articles/mobile-speed-matters/) を含む、ユーザーエンゲージメントに対するパフォーマンスの影響に関する広範な調査を発表しています。[WPOStats](https://wpostats.com) や [PWAStats](https://www.pwastats.com) など、さまざまな Web パフォーマンス統計やケーススタディも独立したサイトで入手できます。

## 目標

開発者は、対話までの時間 (TTI) や最初の意味のあるペイント (FMP) のような測定可能な概念についてよく話します。これは重要で包括的な目標を定量化しようとする試みで、単に最初の訪問、そしてその後の訪問でユーザーができるだけ早くコンテンツと動作の両方にアクセスできるように*できるだけ早くページをロードすることです*。

Web パフォーマンス統計の概念と用語に慣れておらず、さらに詳しく知りたい場合は、Google の概要記事[ユーザエクスペリエンスに最も影響を与えるパフォーマンス統計の活用](/web/updates/2017/06/user-centric-performance-metrics)をご覧ください。

このドキュメントセットには、ローエフォート、ハイリターンのパフォーマンスの向上に焦点を当てた説明、例、および推奨事項が含まれています。内容は累積的ではなくプログレッシブです。つまり、提案 されている手法をすべて使用する必要はなく、また特定の順序で使用する必要もありません。しかし、自分の Webページに適用できる数が多いほど、ページのパフォーマンスは向上します。

## フィードバック {: #feedback }

{% include "web/_shared/helpful.html" %}
