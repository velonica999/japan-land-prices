# japan-land-prices：日本の不動産取引価格データ（都道府県・市区町村別 CSV）

国土交通省「不動産情報ライブラリ」の不動産取引価格情報をもとに [不動産相場.com](https://fudosan-souba.com/) が集計した、**全国・47都道府県・市区町村 × 土地／戸建／中古マンション**の取引件数・価格・㎡単価・面積・築年数の**中央値**の CSV です。2005年からの年次・四半期の推移も入っています。

- データの説明とダウンロード：https://fudosan-souba.com/data/
- サイトで見る（都道府県・市区町村のページ）：https://fudosan-souba.com/
- 更新：このリポジトリの CSV は、毎日サイトの `/data/` から自動で取り込んでいます。サイトは毎月5日に国土交通省の API から取り直して自動更新します。不動産取引価格情報そのものは年4回（おおむね1・4・7・10月）の公表です。

## ファイル

| ファイル | 内容 |
|-|-|
| `data/prefecture_yearly.csv` | 都道府県（全国＝00）×種別×年 |
| `data/prefecture_quarterly.csv` | 都道府県（全国＝00）×種別×四半期 |
| `data/municipality_latest.csv` | 市区町村×種別の直近1年（4四半期）と、1年前・5年前・10年前からの㎡単価の変化率 |
| `data/municipality_yearly.csv` | 市区町村×種別×年 |

文字コードは UTF-8（BOM 付き）で、Excel でそのまま開けます。価格は円、面積は㎡。都道府県コードは 01〜47（全国は 00）、市区町村コードは5桁。「対象四半期」が空欄でない年は、その四半期だけの集計です（最初と最新の年）。

## 列

| 列名 | 意味 | Description |
|-|-|-|
| 種別 | 土地＝宅地(土地)／戸建＝宅地(土地と建物)のうち用途が住宅（新築を含む）／中古マンション＝中古マンション等のうち用途が住宅 | property type |
| 取引件数 | 取引の件数 | number of transactions |
| 価格中央値_円 | 取引価格の中央値 | median transaction price (yen) |
| ㎡単価中央値_円 | 各取引の「価格÷面積」の中央値（土地は土地面積、戸建は延床面積、マンションは専有面積あたり） | median price per m2 (yen) |
| 面積中央値_㎡ | 土地と戸建は土地面積、マンションは専有面積の中央値 | median area (m2) |
| 延床面積中央値_㎡ | 戸建の延床面積の中央値 | median total floor area (m2), houses only |
| 築年数中央値_年 | 戸建・マンションの築年数の中央値 | median building age (years) |
| 1年前比_%・5年前比_%・10年前比_% | ㎡単価の中央値の変化率（比べる両期間とも30件以上のときだけ） | change in median price per m2 (%) |
| 参考値 | 1＝取引が5件未満で変動が大きい | 1 = fewer than 5 transactions |

面積が「2,000㎡以上」と公表されている取引は、単価と面積の集計から外しています（価格と件数には含みます）。2007年ごろまでは収録されている地域に偏りがあり、県全体の値が高く出ることがあります。集計方法の詳細は https://fudosan-souba.com/about/ を見てください。

## 利用条件（ライセンス）

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.ja)。商用・非商用を問わず、報道・ブログ・研究・授業・アプリ・AI の学習や回答などに自由に使えます。条件は出典を明記することだけです。

**「出典を明記する」とは？** 使った数字がどこのデータかを、読む人に分かるように書き添えることです。次の1行をコピーして、数字や表・グラフのすぐ下か、記事・資料の最後に貼り付けてください。

```
出典：不動産相場.com（国土交通省「不動産情報ライブラリ」の不動産取引価格情報をもとに集計） https://fudosan-souba.com/data/
```

- ブログ・ホームページ：表やグラフのすぐ下に貼る
- 資料・スライド・レポート：そのページの下の端か、最後の「参考資料」に書く
- SNS・動画：投稿文や概要欄の最後に書く
- 表を加工・グラフ化したとき：「出典：不動産相場.comのデータをもとに作成 https://fudosan-souba.com/data/」と書く
- URL は行の最後に置き、前に空白を入れる（URL のすぐ後ろに文字やカッコを続けると、リンクが切れることがあります）

許可の連絡やお金は要りません。出典さえ書けば、仕事（商用）でも自由に使えます。

元のデータは国土交通省の[不動産情報ライブラリ](https://www.reinfolib.mlit.go.jp/)「不動産取引価格情報」で、[公共データ利用規約（PDL1.0）](https://www.reinfolib.mlit.go.jp/help/termsOfUse/)に基づき、不動産相場.com が集計・加工しています。国土交通省が作成したものではありません。このサービスは、国土交通省の不動産情報ライブラリのAPI機能を使用していますが、提供情報の最新性、正確性、完全性等が保証されたものではありません。

---

## English

Median real estate transaction prices in Japan by **prefecture (47) and municipality × type (land / house / used condominium)**, aggregated by [fudosan-souba.com](https://fudosan-souba.com/) from the MLIT Real Estate Information Library (transaction price information). Includes yearly and quarterly series from 2005. Prices in yen, areas in m2. Files are UTF-8 with BOM. License: CC BY 4.0 — please credit "fudosan-souba.com, based on the MLIT Real Estate Information Library: https://fudosan-souba.com/data/". Source data: MLIT Real Estate Information Library, used under the Public Data License 1.0 (compatible with CC BY 4.0); this dataset was processed by fudosan-souba.com and is not produced by MLIT. Synced daily from https://fudosan-souba.com/data/.
