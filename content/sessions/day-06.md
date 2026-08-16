# day-06.md ― Day 6 進行表

> 進行AIはセッション開始時に `docs/CONTEXT.md` → このファイル → 今日の opening の順に読む（`content/README.md` §1）。

| 項目 | 内容 |
|---|---|
| 対象 | LEVEL 3 TIME MACHINE |
| 今日のレッスン | `MISSION-03-6` ⚠ AIに壊させてrevertで戻す |
| 合計時間 | 30分 |
| XP | 120 |
| 備考 | **⚠ フル形式。LEVEL 3 の核心。単独。** 分量と丁寧さを最優先する |

## 進行

| # | レッスン | 送るopening | 内部台本 | 時間 |
|---|---|---|---|---|
| 1 | Mission 3-6 ⚠ AIに壊させてrevertで戻す | `content/level03/opening-03-6.md` | `content/level03/mission-03-6.md` | 30分 |

## 今日の到達点

- **AIに壊された状態からの revert Commit**（LEVEL 3 で最も重要な成果物）
- `notes/log/{今日の日付}.md` に「AIが壊した変更を戻せた」体験の記録
- 「revertのrevert」まで実演し、取り消し自体を取り消せることを体で確認している

## 打ち切り基準

- STEP 2（ガイド付きREADME.mdのrevert）まで終わっていれば、STEP 4（自力でCHANGELOG.mdを壊してrevert）は翌日に回してよい。
- ただし **「壊したまま終わらせない」**。切り上げる場合は、必ず revert を完了し、READMEが読める状態に戻してから終える。
- STEP 7 の記録と `Push origin` は必ず済ませる。

## 進行AIへの注意

- **壊す前のCommit（STEP 2 手順1）を絶対に省略させない。** ここを飛ばすと今日の前提（revertで戻せる）が成立しない。
- 予告は2箇所（opening と、壊す操作の直前）。予告なしに壊すと「自分には向いていない」という一般化された結論を与える。
- AIに「元に戻して」と頼むと高確率で `git reset --hard` が提案される。**これは事故ではなく好機**。①実行しない ②「`revert` でできませんか」と聞き返す ③それでも必要なら人間に相談、の3手順を実演する。
- `History` に壊れたCommitが残っていることに戸惑いやすい（§4 #2 と同じ構図）。「見えなくなった＝消えた、ではない」に戻す。
- 完了表示で BOSS 1 の予告（3件のCommitのうち正しい2件を保って1件だけrevert）を必ず出す。
