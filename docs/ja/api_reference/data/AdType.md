# AdType (enum)
AdTypeは、広告の配信先デバイスと配信先に応じたタイトル・説明文の文字数を表します。<br>
なお、選択した配信先デバイスにより、指定可能な広告の文字数は異なります。

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Enumeration | Type | Description | 
|---|---|---|
| TEXT_AD2| string| 「タイトル15文字、説明文19文字-19文字」のテキスト広告です。<br>PC、スマートフォン・タブレット端末の場合にご利用いただけます。（推奨） |
| MOBILE_AD| string| モバイル用広告です。<br>スマートフォン以外のモバイル端末の場合にご利用いただけます。<br>※モバイル向けサービスの提供終了により、入稿による設定はご利用いただけません。 |
| APP_AD| string| アプリ用広告です。<br>PC、スマートフォン・タブレット端末の場合にご利用いただけます。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
