# unisizeSDK for Android について

unisizeSDK for Android は、Android Studio Kotlin／Java で開発された Android 向け EC アプリケーションに対して、unisize のバーチャルフィッティング機能を提供する SDK です。  
導入することにより、Android 向けの EC アプリケーションに対して unisize、unisize for KIDS、unisize for バッグのバナー表示、サイズレコメンド機能を提供します。  
また2025年2月にリリースした3D表示機能に対応しています。（対象商品のみ）  
  
## unisize について

unisize は、オンラインでのショッピング体験を向上させるためのサービスです。ユーザーの体型と好みに基づいて最適なサイズを推薦し、EC サイト上でのサイズ選びの不安を解消します。  
ユーザーは簡単な質問に答えることで個別に最適なサイズ推薦を受けられ、返品率の削減にも貢献します。  
国内外の多くの EC サイトで利用されており、ユーザーフレンドリーなインターフェース、精度の高いサイズレコメンドを提供しています。  

## unisizeSDK の対応 OS、バージョン

・Android 11（API レベル 30）、またはそれ以降

- プロジェクトへの組み込み、ビルドは Android 9（API レベル 28）から可能です。  
  （一部実機で動作確認が取れていない箇所があるため、Android 11 以降のサポートとしています。）
- Android 9（API レベル 28）以降をサポートするプロジェクトに導入する際は、`android.os.Build.VERSION.SDK_INT`を用いて、現在のデバイスの API レベルを確認して Android 11（API レベル 30）以降の環境でのみ unisizeSDK を使用するように実装することを推奨します。

## 対象プロジェクト・言語

Android Studio Kotlin／Java で開発された Android 用アプリケーションのプロジェクトに対して導入可能。

- 商品詳細画面、購入完了画面の全てが WebView で構成されている EC アプリの場合、unisizeSDK を使用することができません。Web 版 unisize をご利用ください。
- 商品詳細画面がネイティブ UI、購入完了画面が WkWebView で構成されている EC アプリでも unisizeSDK の導入は可能です。<br>
  コンバージョンの実装については、アプリの設計、構造に応じで、unisizeSDK の UnisizeCvTag Class を使用する方法と、Web 版 unisize の CV タグを利用する方法の 2 種類の実装方法があります。<br>
  実装方法など、詳しくは付属のドキュメント「unisize のコンバージョンの実装について」をご覧ください。

## バージョン履歴

### v1.5.5

- CI バナーのみを使用している一部クライアント様向けの対応を行いました。v1.5.5 より CI バナーのみの利用が可能になりました。
- 2025年2月にリリースした3D表示機能に対応しました。対象商品でアンケート結果画面でシルエットの3D表示が可能になりました。
- 内部処理の最適化
  
## v1.5.2 （Android 版のみ）

- unisizeSDK で利用している Webview の SSL エラーハンドラの処理が、Google Play Console 上で警告が表示されることがあったため、この部分改良しました。
- UnisizeBanner class の UnisizeBannerListener > fun didBeidChanged() の引数 `recommended_items` の名称を `recommendedItems` に変更しました。
- 内部処理の改善など

## v1.5.1 （Android 版のみ）

- unisizeSDK を導入するアプリ側の設計、実装によって、 unisizeSDK v1.5 Android 版で unisize バナーをタップした際にアンケート画面が表示されないことがある問題を解決しました。<br>
  商品詳細画面で context から取得できる Activity が FragmentActivity、または FragmentActivity を継承した Class（AppCompatActivity など）ではない場合に、SDK 内で動的に FragmentActivity を生成して、アンケート画面を表示するように改良を加えています。<br>
  上記に伴い、AndroidManifest.xml へ下記の設定の追加が必要となります。

  ```xml

  <activity android:name="jp.co.makip.unisizesdk.UnisizeBanner$WebAppInterface$UnisizeDynamicFragmentActivity"
  android:exported="true" />

  ```

## ドキュメント

最新のドキュメント、SDK リファレンスは GitHub の Wiki をご覧ください。  
[https://github.com/Makip-DevKit/unisize-sdk-doc/](https://github.com/Makip-DevKit/unisize-sdk-doc/)


## その他
- unisizeSDK導入に関しての詳細は、弊社担当営業までご相談ください。
- unisizeSDK v1.5.5よりも前のバージョンが必要な場合は、弊社担当営業までご相談ください。

## ライセンス
- 付属の「unisize_SDK 使用許諾契約.pdf」をご覧ください。

