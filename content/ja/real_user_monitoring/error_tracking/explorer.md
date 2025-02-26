---
description: エラー追跡エクスプローラーについて説明します。
further_reading:
- link: /monitors/types/error_tracking
  tag: Documentation
  text: エラー追跡モニターについて
- link: /real_user_monitoring/error_tracking
  tag: Documentation
  text: RUM のエラー追跡について
kind: ドキュメント
title: Error Tracking Explorer
---

## 概要

{{< img src="real_user_monitoring/error_tracking/rum_error_tracking.png" alt="RUM のエラー追跡エクスプローラーは、Web およびモバイルアプリケーションのクラッシュレポートから問題を表示します" style="width:100%;" >}}

Error Tracking Explorer を使用すると、さまざまな問題を見つけることができます。問題とは、同じバグに関連する同様のエラーのまとまりでのことです。Datadog では、エラータイプ、エラーメッセージ、またはスタックトレースなどのフィンガープリントを計算し手問題を作成します。同じフィンガープリントを持つエラーは 1 つの問題にグループ化されます。

## 問題を探索

エラー追跡エクスプローラーに表示される各項目は、問題であり、以下のようなエラーに関する概要情報が含まれています。

-   エラータイプやエラーメッセージ
-   基になるエラーが発生したファイルへのパス
-   問題の存続期間に関する重要な情報:
    -   確認された最初と最後の時期
    -   経時的な発生グラフ
    -   指定期間内の発生回数


### タイムレンジ

{{< img src="real_user_monitoring/error_tracking/time_range.png" alt="エラー追跡の時間範囲" style="width:80%;" >}}


Explorer の右上に、タイムラインの形式で時間範囲が表示されます。ここで、選択した期間内に発生したエラーとともに問題を確認できます。プリセットされた期間をドロップダウンから選択することで、期間を変更できます。

### ファセット

{{< img src="real_user_monitoring/error_tracking/facet.png" alt="エラー追跡ファセット" style="width:80%;" >}}

Error Tracking により、問題は事前定義された属性リストに自動的に指数化され、ファセットが作成されます。ファセットは、選択した期間の 1 つの属性の個別メンバーをすべて表示するほか、確認された問題の数など基本的な分析も提供します。ファセットを使用すると、特定の属性に基づいて問題を絞り込んだり、切り口を変えたりすることができます。

## 問題の調査

問題をクリックすると、問題パネルが開いて詳細が表示されます。

{{< img src="real_user_monitoring/error_tracking/issue_panel_upper_part.png" alt="エラー追跡問題パネルの上部" style="width:80%;" >}}

パネルの右上には、トラブルシューティングの際に必要となる情報の詳細が表示されます。ここで、問題発生の初日および最終日、総発生回数、一定期間に発生した回数など、問題のライフサイクルについて確認できます。

{{< img src="real_user_monitoring/error_tracking/issue_panel_lower_part.png" alt="エラー追跡問題パネルの下部" style="width:80%;" >}}

問題パネルの下部では、関連する問題からのエラーサンプルにアクセスできます。各エラーサンプルには、トラブルシューティングに役立つ情報が含まれています。例:

-   各スタックフレームがコードスニペットを提供するスタックトレースが、エラーを発生したコード行に集中。
-   RUM SDK により実際に収集された場合、エラーが発生した RUM セッションの情報。
-   エラーが発生したときに使用していたブラウザや OS (および関連バージョン) などのユーザー情報。

## 新規エラーをアラート通知

新しい問題が発生したらすぐに発見できると、積極的に問題を特定し重大になる前に修正することが可能になります。所定のサービスおよび環境で最初に問題が発見されると、エラー追跡機能により [Datadog イベント][1]が生成されるため、結果として[イベントモニター][2]を構成することでこのようなケースに関するアラートを受信することができます。

生成された各イベントは、バージョン、サービス、環境でタグ付けされるため、アラートを受信したい問題についてきめ細かな制御が可能です。エクスプローラーから直接検索クエリをエクスポートして、関連スコープのイベントモニターを作成できます。

{{< img src="real_user_monitoring/error_tracking/export_to_monitor.mp4" alt="検索クエリをエラー追跡モニターにエクスポート" video=true >}}

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: /ja/events
[2]: /ja/monitors/types/event/