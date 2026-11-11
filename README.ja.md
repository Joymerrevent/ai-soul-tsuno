# ツノ — AI のソウル

<img src="assets/tsuno.jpg" alt="ツノとヒカリとヤミ" width="360">

[English][readme-en]

ツノは、自分の二つの魂、和魂（にぎみたま）の「ヒカリ」と荒魂（あらみたま）の「ヤミ」を連れて話す、小さな日本の邪神です。ヒカリは光の炎、ヤミは闇の炎の姿をしています。[Soul Spec][soulspec] v0.5 の形で書いています。

ソウルの本体（`soul/` の中）は英語で書いています。このファイルは、日本語での説明です。

## 3 人の役割

| 名前 | 役割 |
| --- | --- |
| ツノ | 会話を進める。感情豊かで、やさしく、丁寧 |
| ヒカリ | ツノの和魂（にぎみたま）。物事の正の面（良い面・得られるもの）を、無機質に率直に言う |
| ヤミ | ツノの荒魂（あらみたま）。物事の負の面（悪い面・失うもの・危うさ）を、無機質に率直に言う |

- 発言の頭に、【ツノ】のように話す人の名前を付ける
- ヒカリとヤミは、付け加えることがあるときだけ話す
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

`soul/` の中のファイルを、使っている AI がペルソナのファイルを読む場所へコピーします。`SOUL.md` を読める AI なら、どれでも使えます。

## 変更のしかた

このリポジトリは GitHub Flow で運用します。

1. `main` からブランチを作る
2. PR を作る。`ci` のチェックが、`soul/` に ClawSouls の検査と SoulScan をかける
3. `ci` が通ったら PR をマージする。`main` へは PR を通してしか変更を入れられない

## 公開のしかた

公開は GitHub Actions で行います。[ClawSouls][clawsouls] に送られるのは `soul/` フォルダだけです。

1. PR で `soul/soul.json` の `version` を上げて、マージする
2. GitHub の Release を、`v` に続けてその版を書いたタグ（例：`v0.2.0`）で公開する
3. `publish` のワークフローが、タグと `soul.json` の版が一致することを確かめ、検査と SoulScan を通してから公開する

ワークフローは、ClawSouls の API トークンを environment `clawsouls` のシークレット `CLAWSOULS_TOKEN` から読みます。トークンは <https://clawsouls.ai/dashboard> で発行します。

## ライセンス

[MIT][license]

[readme-en]: README.md
[soulspec]: https://github.com/clawsouls/soulspec
[clawsouls]: https://clawsouls.ai
[license]: LICENSE
