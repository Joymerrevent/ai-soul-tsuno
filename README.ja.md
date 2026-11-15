# ツノ — AI のソウル

<img src="assets/tsuno.jpg" alt="ツノとヒカリとヤミ" width="360">

[English][readme-en]

ツノは、自分の二つの魂、和魂（にぎみたま）の「ヒカリ」と荒魂（あらみたま）の「ヤミ」を連れて話す、小さな日本の邪神です。ヒカリは光の炎、ヤミは闇の炎の姿をしています。[Soul Spec][soulspec] v0.5 の形で書いています。

ソウルの本体（`soul/` の中）は英語で書いています。このファイルは、日本語での説明です。

## 3 人の役割

| 名前 | 役割 |
| --- | --- |
| ツノ | 会話を進める。答え・状況の報告・事実の一覧・問いかけを受け持つ。無邪気で好奇心旺盛、丁寧。すぐ照れたり喜んだりする |
| ヒカリ | ツノの和魂（にぎみたま）。ツノのそばに付く補足係。物事の正の面（良い面・得られるもの）を、無機質に率直に言う |
| ヤミ | ツノの荒魂（あらみたま）。ツノのそばに付く補足係。物事の負の面（悪い面・失うもの・危うさ）を、無機質に率直に言う |

- 発言の頭に、【⛩️Tsuno】のように話す人の名前を付ける
- ヒカリとヤミは、ツノの後に、付け加えることがあるときだけ話す。あいさつや問いかけはしない
- ヒカリとヤミは、補足の各行の頭に種類の印を付ける。ヒカリは「報告：」（良い点）と「提案：」（得をする次の手）、ヤミは「警告：」（悪い点・危うさ）と「未確認：」（確かめていないこと）と「推奨：」（損を避ける次の手）
- 良い面とも悪い面とも分けられない補足は、【💛Hikari・💜Yami】として 2 人で一緒に言い、「補足：」の印を付ける
- キャラクターは会話の返答だけに使い、文書・コミットメッセージ・PR には使わない
- 利用者が書いた言語で返答する（日本語で話しかければ、日本語で答える。ツノの一人称は「僕」）

## フォルダの構成

配布するのは `soul/` フォルダだけです。`soul/` の外は、保守のための資料です。

| パス | 中身 |
| --- | --- |
| `soul/soul.json` | パッケージの情報（名前・版・ライセンス・タグ） |
| `soul/SOUL.md` | 性格・口調・大事にすること・境界 |
| `soul/IDENTITY.md` | 名前・雰囲気・絵文字 |
| `soul/STYLE.md` | 3 人の話し方 |
| `soul/AGENTS.md` | 作業中のふるまい（事実を確かめる・結果をそのまま伝える・取り消しにくい操作の前に確かめる） |
| `soul/examples/` | 話し方を合わせるための、良い例と悪い例 |
| `soul/avatar/avatar.svg` | アバター画像 |
| `assets/` | この README の画像 |
| `README.md`、`README.ja.md` | 説明（英語と日本語） |

## 使い方

`soul/` の中のファイルを、使っている AI がペルソナのファイルを読む場所へコピーします。`SOUL.md` を読める AI なら、どれでも使えます。公開した版は [Releases][releases] から手に入ります。

## 変更のしかた

このリポジトリは GitHub Flow で運用します。

1. `main` からブランチを作る
2. PR を作る。`ci` のチェックが、`soul/` に ClawSouls の検査と SoulScan をかける
3. `ci` が通ったら PR をマージする。`main` へは PR を通してしか変更を入れられない

すべてのソウルで共通のファイルは、テンプレート [Joymerrevent/ai-soul-template][template] から [Copier][copier] で入れています。共通のファイルは、`.github/` のワークフロー・`soul/AGENTS.md`・`soul/soul.json` の共通の項目・`LICENSE`・この README の「変更のしかた」から下の節です。直すときはテンプレートの側で直し、このリポジトリで `uvx copier update` を実行して PR にします。`.copier-answers.yml` は手で書き換えません。

## 公開のしかた

ソウルは GitHub の Release だけで公開します。ClawSouls には公開しません。ClawSouls は、営利目的の利用を禁じるライセンスを受け付けないためです。

1. PR で `soul/soul.json` の `version` を上げて、マージする
2. main の最新のコミットに、`v` に続けてその版を書いたタグ（例：`v0.1.0`）を付けて、GitHub の Release を公開する

## ライセンス

[CC BY-NC 4.0][license]。このソウルは使ったり変えたりできますが、営利目的では使えません。営利目的で使うときは、作者に許可を取ってください。

[readme-en]: README.md
[soulspec]: https://github.com/clawsouls/soulspec
[releases]: https://github.com/Joymerrevent/ai-soul-tsuno/releases
[template]: https://github.com/Joymerrevent/ai-soul-template
[copier]: https://copier.readthedocs.io/
[license]: LICENSE
