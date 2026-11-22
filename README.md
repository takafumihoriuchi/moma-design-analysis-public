# MoMAのDesign分類の作品に紐づくデザイナーの出身教育機関（データ）

ニューヨーク近代美術館（MoMA）の収蔵作品のうち、Architecture & Design部門でDesignに分類された作品について、作り手のデザイナーがどの教育機関（大学・大学院・芸術やデザインの専門教育機関）を卒業・修了したかを公開資料で調べ、集計したデータです。noteの連載記事の裏付けとして公開しています。

**2026-11-18時点の暫定集計です（2026-11-22修正）。** 対象作品のすべてで、MoMAの学芸員確認状態（データが確認済みかどうかの表示）を判定できていません。制作者名義の一部（211件）も、個人・組織などの判定を保留しています。

*English summary:* Provisional data (as of 2026-11-18; see the change log below for later corrections) on the educational institutions from which designers of works in MoMA's Architecture & Design department, classification "Design", graduated. Built on MoMA's official collection data (commit `51a140d`) plus independent research of public sources. CSV files only. Not an official MoMA statistic.

## 主な結果

卒業・修了を資料で確認し、学位などの授与校まで特定できた844人を、学校ごとに数えました。数え方は次のとおりです。
- 同じ学校の複数学位は1人として数える
- 複数校を修了した人は、各校で1人として数える
- 同数は同順位

| 順位 | 教育機関 | 所在国 | 卒業・修了者数 |
|---:|---|---|---:|
| 1 | Royal College of Art | 英国 | 58 |
| 2 | Politecnico di Milano | イタリア | 48 |
| 3 | Massachusetts Institute of Technology | 米国 | 29 |
| 4 | Design Academy Eindhoven | オランダ | 27 |
| 5 | Pratt Institute | 米国 | 25 |
| 6 | Yale University | 米国 | 21 |
| 7 | Columbia University | 米国 | 15 |
| 8 | Cooper Union | 米国 | 14 |
| 8 | New York University | 米国 | 14 |
| 8 | Università degli Studi di Firenze | イタリア | 14 |
| 11 | Art Center School | 米国 | 13 |
| 11 | Cranbrook Academy of Art | 米国 | 13 |
| 11 | Rhode Island School of Design | 米国 | 13 |
| 14 | Academy of Plastic Arts, Warsaw | ポーランド | 12 |
| 14 | Helsingin Taideteollinen Oppilaitos | フィンランド | 12 |
| 14 | Stanford University | 米国 | 12 |
| 17 | Harvard University | 米国 | 10 |
| 17 | Parsons School of Design | 米国 | 10 |
| 17 | 東京藝術大学 | 日本 | 10 |

ほかの切り口は次のファイルにあります。

- 全413機関のランキング：`results/05_ranking_by_people.csv`
- 作品数で数えたランキング：`results/06_ranking_by_works.csv`
- 在籍・中退なども含めた「学んだ人数」：`results/07_ranking_learning_inclusive.csv`
- プロダクト（家具・照明・食器・キッチン・日用品・機器・家電・乗り物・道具・玩具）の作品がある人で数えたランキング：`results/29_product_ranking_by_people.csv`（関連は28〜33）

## 対象と数え方

| 項目 | 内容 |
|---|---|
| 基礎データ | MoMA公式の [MuseumofModernArt/collection](https://github.com/MuseumofModernArt/collection)。コミット [`51a140dae6e6d9bc91f6d711f662df60c80b4f8a`](https://github.com/MuseumofModernArt/collection/tree/51a140dae6e6d9bc91f6d711f662df60c80b4f8a) に固定（DOI [10.5281/zenodo.23685464](https://doi.org/10.5281/zenodo.23685464)） |
| 抽出条件 | `Artworks.json` の `Department` が `Architecture & Design`、かつ `Classification` が `Design`（完全一致） |
| 対象作品 | 12,038件（制作者IDのない作品40件を含む） |
| 制作者ID | 3,891件。個人3,139、組織441、集団65、匿名35、名義判定保留211 |
| 人物（対象 N） | 3,139人。個人の制作者IDから同一人物の別IDを統合（−2）し、集団名義の作品の共同署名で確認した個人を加えた（＋2） |
| 教育機関名を確認 | 1,843人（58.7%）。在籍・中退なども含む |
| 卒業・修了を確認し授与校を特定（ランキングの対象 V） | 844人（26.9%）。学校は413機関、人物×学校は1,029組 |

- **卒業・修了として数えたもの：** 実際に開いた資料の本文に、卒業・修了・学位授与がはっきり書かれている場合だけです。
- **数えていないもの：** 在籍、中退、短期、交換、名誉学位、教員歴。また、検索結果の抜粋や百科事典だけを根拠にした記録も数えていません。
- **根拠：** 卒業・修了の全組について、根拠の資料のURLと参照箇所を `data/graduation_pairs.csv` に載せています。
- **資料で確認できなかったことは、卒業していないという意味ではありません。** 全員の状態と、確認できなかった理由は `data/people.csv` にあります。
- **学校名：** 在籍当時の名前で記録しました。改称した学校は同じ学校として数え、合併前の別の学校は現在の大学に合算していません。同じ学校が別のIDで二重に数えられていた箇所は修正し、その一覧を `data/institution_id_corrections.csv` に載せています。
- **判定の修正：** 資料によって卒業・修了かどうかの記載が食い違い、卒業・修了としては数えないと判断した記録は、理由と両方の資料のURLを `data/graduation_judgment_corrections.csv` に載せています。人物は対象から外さず、ほかの学校の卒業・修了はそのまま数えています。
- **作品の種別：** 素材と題名のキーワードで分けた本調査の目安です。各作品の判定は `data/works.csv` の「作品種別」列にあります。プロダクトの4種別は各40件を抜き取って目で点検しました（`results/90b_product_type_spot_check.csv`）。作品の種別は、対象者の選定には使っていません。

## ファイル

| ファイル | 内容 |
|---|---|
| `data/works.csv` | 対象の全作品（MoMAのデータの題名・制作年・素材・収蔵日・クレジット・URL・制作者ID、本調査の作品種別） |
| `data/work_creator_links.csv` | 作品と制作者IDの対応（MoMAのデータのまま） |
| `data/creators.csv` | 全制作者IDの名義区分（個人・組織・集団・匿名・名義判定保留）と人物ID |
| `data/work_person_links.csv` | 作品と人物の対応（同一人物の統合と、共同署名の個人を反映） |
| `data/people.csv` | 全3,139人の学歴の判明状況、確認できた学校、未確認の理由 |
| `data/graduation_pairs.csv` | 卒業・修了の人物×学校の全組と、根拠のURL・参照箇所 |
| `data/learning_records.csv` | 在籍などを含む学修の記録と、根拠のURL・参照箇所・要約 |
| `data/institutions.csv` | 教育機関の一覧（所在国、学校の性格、人数） |
| `data/institution_id_corrections.csv` | 同じ学校の重複IDの修正一覧 |
| `data/graduation_judgment_corrections.csv` | 卒業・修了の判定を修正した記録（理由と、判断が分かれる資料の両方） |
| `results/01`〜`19` | 母集団、学歴の判明状況、ランキング（人数・作品数・学んだ人数）、所在国、自国か海外か、世代、確認率、学校の性格、専攻、作品の種別、収蔵年代、よく知られた作品の例 |
| `results/28`〜`33` | プロダクトに絞ったランキングと関連の表 |
| `results/90b_product_type_spot_check.csv` | プロダクトの4種別の抜き取り点検の結果 |
| `results/featured_schools/` | 卒業・修了者10人以上の学校ごとの、人物と全作品の一覧（MoMAの作品ページへのリンクつき） |

## 同じ手順で確かめるには

1. MoMAの公式レポジトリから、上のコミットの `Artworks.json` と `Artists.json` を取得する（Git LFSの実体。SHA-256は `Artworks.json` が `6d22dd06bd7cd75921728c05909e50868f785c1e3c7c332d4a3ba48e3c691da9`、`Artists.json` が `bc6a0f649e9c4befca2d4220d0c63d34f78b027ae931953b4b45374248da4f8d`）。
2. 抽出条件で作品を絞り、`ConstituentID` を展開すると、`data/works.csv`・`data/work_creator_links.csv` と一致する。
3. `data/graduation_pairs.csv` を学校の列で数えると、`results/05_ranking_by_people.csv` と一致する。`data/work_person_links.csv` と組み合わせると、`results/06_ranking_by_works.csv` と一致する。

教育歴の調査そのもの（資料の検索と本文の読解）は人の判断を含むため、すべての卒業・修了の組に根拠のURLと参照箇所を付けています。

## 限界

- MoMAの収蔵方針でできた集団であり、世界の優れたデザイナー全体の無作為の標本ではありません。対象は工業デザイナーに限りません。
- 学歴の公開状況や言語によって、確認できた割合に偏りがあります。新しい世代ほど、また国籍によって確認しやすさが違います（`results/11`・`results/13`）。
- ランキングは「確認できた卒業・修了者数による順位」で、学校の教育の効果や優劣を示すものではありません。各校の卒業生全体を調べたものでもありません。

## 更新履歴

- 2026-11-21：初版（2026-11-18時点の暫定集計）
- 2026-11-22：Kenji EkuanのArt Center Schoolの記録を、卒業・修了から短期学修に改め、ランキングから外した（Art Center Schoolは14人→13人）。資料の記載が食い違うため。理由と両方の資料は `data/graduation_judgment_corrections.csv`

## 出典と帰属

本データは、The Museum of Modern Art（MoMA）がGitHubで公開する収蔵作品・制作者データセット（コミット `51a140d`、DOI 10.5281/zenodo.23685464）を基礎にした独自調査です。

- 学歴情報の整備、分類および集計は本調査によるもので、MoMAの公式な学歴統計や認定を示すものではありません。
- MoMAが本調査を推薦・承認しているものでもありません。
- 作品の画像は含みません。

## 利用条件

- **本調査で作成した部分**（学歴の調査結果、分類、集計）：[クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/deed.ja)。出典としてこのレポジトリを示せば、誰でも再利用できます。
- **MoMAのデータに由来する項目**（作品の題名・制作年・素材・収蔵日・クレジット・URL、制作者IDと名義など）：MoMAが [CC0](https://creativecommons.org/publicdomain/zero/1.0/) で公開しているデータです。利用の際はMoMAへの帰属表示をお願いします。
- **根拠として示した外部の資料**（URL先のページ）：権利はそれぞれの発行者にあります。このレポジトリは資料の本文を含まず、URLと参照箇所、短い要約だけを載せています。
