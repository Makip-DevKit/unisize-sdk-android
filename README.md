# unisizeSDK for Android について

unisizeSDK for Android は、Android Studio Kotlin／Java で開発された Android 向け EC アプリケーションに対して、unisize のバーチャルフィッティング機能を提供する SDK です。  
導入することにより、Android 向けの EC アプリケーションに対して unisize、unisize for KIDS、unisize for バッグのバナー表示、サイズレコメンド機能を提供します。  
また2025年2月にリリースした3D表示機能に対応しています。（対象商品のみ）  
  
## unisize について

unisize は、オンラインでのショッピング体験を向上させるためのサービスです。ユーザーの体型と好みに基づいて最適なサイズを推薦し、EC サイト上でのサイズ選びの不安を解消します。  
ユーザーは簡単な質問に答えることで個別に最適なサイズ推薦を受けられ、返品率の削減にも貢献します。  
国内外の多くの EC サイトで利用されており、ユーザーフレンドリーなインターフェース、精度の高いサイズレコメンドを提供しています。  

## ドキュメント

導入手順や最新のドキュメント、SDK リファレンス、サンプルプロジェクト は GitHub の Wiki をご覧ください。  
[https://github.com/Makip-DevKit/unisize-sdk-doc/](https://github.com/Makip-DevKit/unisize-sdk-doc/)
  
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

### v2.0
- 【iOS】SwiftUI をサポートしました。
- 【iOS】バナーの表示で使用する Class に、新たに UnisizeBannerWebview Class を追加しました。これによりバナー単位（TEXTバナー、EXバナー、CIバナー）で Class の配置が可能となりました。（複数インスタンスの利用可能。Android版に近い方法での実装が可能となりました。）<br>
  Flutter や SwiftUI での実装が UnisizeBanner Class と比べ容易になります。<br>なお、下位互換を持たせているため、すでに unisizeSDK を導入済みで Swift で開発されたアプリの場合は、これまでの UnisizeBanner Class を使った実装方法でも、特に実装を変更することなくそのまま動作しますが、UnisizeBanner Class は将来（数年以内）に廃止する予定のため、どこかのタイミングで UnisizeBannerWebview Class へ切り替えていただくことをお勧めいたします。
- 【iOS】UnisizeCVTag に`close()`を追加しました。詳しくはSDKリファレンスをご覧ください。
- 【Android】Android版は軽度の最適化のみです。前バージョンからの大きな変更はございません。
- 【Other】unisizeSDK の配布形態を GitHub を使った配信方式に変更します。iOS は Swift Package Manager、Android は Maven リポジトリによるパッケージ配布となります。
  
## その他
- unisizeSDK 導入に関しての詳細は、弊社担当営業までご相談ください。
- unisizeSDK v1.5.5よりも前のバージョンが必要な場合は、弊社担当営業までご相談ください。
  
## お問い合わせ
unisizeSDK についてのお問い合わせは、下記のお問い合わせフォームよりお気軽にご連絡ください。  
https://makip.co.jp/contact
  
## ライセンス
- 付属の「unisize_SDK 使用許諾契約.pdf」をご覧ください。

