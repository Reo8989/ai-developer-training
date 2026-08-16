# day-04.md ― Day 4 進行表

> 進行AIはセッション開始時に `docs/CONTEXT.md` → このファイル → 今日の先頭レッスンの opening の順に読む（`content/README.md` §1）。

| 項目 | 内容 |
|---|---|
| 対象 | LEVEL 3 TIME MACHINE |
| 今日のレッスン | `MISSION-03-3` ＋ `MISSION-03-4`（**2 Missionで1セッション**） |
| 合計時間 | 45分（25分＋20分） |
| XP | 180 |
| 備考 | **教材アプリ v0.4 到達日。** openingは先頭の 3-3 のもの1通だけ送る |

## 進行

| # | レッスン | 送るopening | 内部台本 | 時間 |
|---|---|---|---|---|
| 1 | Mission 3-3 Branchを切る | `content/level03/opening-03-3.md` | `content/level03/mission-03-3.md` | 25分 |
| 2 | Mission 3-4 Mergeする | **送らない**（同一セッション） | `content/level03/mission-03-4.md` | 20分 |

2本目に入るときは opening を再送せず、`mission-03-4.md` の STEP 0 の質問2問を**対話の中で口頭出題**する。

## 今日の到達点

- `CHANGELOG.md`（v0.1〜v0.4）が main にMerge済み ＝ **教材アプリ v0.4**
- リポジトリ設定が Squash Merge のみ有効
- `day2-practice` / `day2-conflict-practice` ブランチが削除済み
- `notes/glossary.md` に Branch命名規則が自分の言葉で書かれている

## 打ち切り基準

- **Mission 3-3 だけで終わってよい。** その場合 `CHANGELOG.md` は `docs/changelog` ブランチにPublishされた状態で止まり、Mergeは翌日に回す。
- 3-3 の STEP 7 の記録は、3-4 に進まない場合でも必ず済ませる。
- 3-3・3-4 を同日に終えた場合、成長ログは1回にまとめて両方を記録してよい。

## 進行AIへの注意

- **やり直しに見せない。** 「今日は前回やった操作を、名前をつけて『いつも同じ手順』に固める回です」と冒頭で位置づける。Day2 で通った手順の細かい再説明はしない。
- `docs/changelog` は初めて公開するブランチなので、ボタンが `Publish branch` になる（`docs/CONTEXT.md` §4 #3）。**押す前に予告する。**
- Merge後の `Pull origin` を飛ばさせない（§4 #1「同期ではなく郵送」）。
