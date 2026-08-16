# content/ ― 教材コンテンツの入口（進行AIが最初に読むファイル）

> **このファイルは何か**：受講セッションを進行するAI（Claude）が、`content/` 配下のどのファイルを・どの順番で読むかを示す索引です。
> **学習者は編集しません。** 学習者の成果物は `notes/` `errors/` `CHANGELOG.md` に置かれます（`PRODUCTION_GUIDE.md` §2-1）。

---

## 1. 進行AIが読む順序（毎セッション）

| # | 読むもの | 目的 |
|---|---|---|
| 1 | `docs/CONTEXT.md`（全文） | 学習者プロフィール・**過去のつまずき §4**・教授方針 §5 |
| 2 | `content/sessions/day-{今日の番号}.md` | 今日やるレッスンの並び・時間配分・打ち切り基準 |
| 3 | `content/level{NN}/opening-{NN}-{N}.md`（今日の先頭レッスンの分） | 「送信本文」を `{{学習者名}}` だけ置換してそのまま送る |
| 4 | 学習者の回答が届いてから `content/level{NN}/mission-{NN}-{N}.md` | 内部台本。STEP 0→7 を小出しに進める |

**3 を送ったあとは黙って待つ。** 回答が届くまで解説を先出ししない。**内部台本（`mission-*.md` / `boss-*.md`）は学習者に見せない**（模範解答が書いてあるため）。

## 2. ファイルの種類

| 種類 | パス | 役割 |
|---|---|---|
| 内部台本 | `level{NN}/mission-{NN}-{N}.md` | 進行AIが読む台本。7STEP構造 |
| オープニング | `level{NN}/opening-{NN}-{N}.md` | **学習者が読む唯一の教材ファイル** |
| Boss台本 | `level{NN}/boss-{NN}.md` | 7STEPではなくチェックポイント4個 |
| 比喩レジストリ | `metaphors.md` | **全LEVEL横断の正典。** 同じ概念に2つ目の比喩を当てない |
| LEVEL用語集 | `level{NN}/glossary-{NN}.md` | 4欄定義の正典（用語ID付き） |
| 問題バンク | `level{NN}/quizbank-{NN}.md` | STEP 6 の「なぜ型」問題の正典 |
| LEVEL図 | `level{NN}/notional-machine-{NN}.md` | Mermaid図の正典 |
| 日次進行表 | `sessions/day-{NN}.md` | 1日分の進行表 |

**レジストリ4種（`metaphors.md` / `glossary-*.md` / `quizbank-*.md` / `notional-machine-*.md`）が正典。** 台本本文に同じ内容が書き下ろされている場合（フル形式のSTEP 1・STEP 3 など）は、**両方を同時に直す**こと。片方だけを直すと、次のレッスンの制作者が古い方を参照する。

## 3. 現在の収録範囲（2026-08-16 時点）

| LEVEL | 収録済み | 未着手 |
|---|---|---|
| LEVEL 3 TIME MACHINE | Mission 3-1〜3-7、BOSS-01（台本8本／opening 7本） | — |
| LEVEL 4 THE OFFICE | Mission 4-1〜4-4（台本4本／opening 3本） | 4-5・4-6・4-7・BOSS 2（次バッチ） |
| LEVEL 5 IT MOVES | — | 全9 Mission（次々バッチ） |
| sessions | Day 3〜Day 10 | Day 11 以降 |

**台本12本・opening 10本。** opening が2本少ないのは、`PRODUCTION_PLAN.md` §1-3 のとおり **#3（Mission 3-3＋3-4）と #9（Mission 4-2＋4-3）が2 Missionを1セッションで扱う**ためで、2本目のMission（3-4・4-3）はopeningを持たず、台本の STEP 0 を対話中に口頭出題する。**それ以外のレッスンは、同じDayに2本あっても必ず自分のopeningを送る**（Day 3 の 3-1／3-2、Day 9 の 4-1／4-2 がこれにあたる）。

## 4. 教材制作側が守ること

- 仕様の正典は `pipeline/PRODUCTION_PLAN.md`。仕様を変えたくなったら、台本ではなく先にそちらを直す。
- 合否基準は `pipeline/QUALITY_CHECKLIST.md`。**Aブロック（禁則）に1件でもFAILがあれば不合格。**
- 新しい比喩を作ったら、台本と**同じPRで** `metaphors.md` に追記する（未登録は CHK-C01 でFAIL）。
- 新出用語・STEP 6 の問題・Mermaid図は、台本を書いたら同じPRで各レジストリにも追記する（参照切れを作らない）。
