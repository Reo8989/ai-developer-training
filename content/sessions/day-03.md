# day-03.md ― Day 3 進行表

> 進行AIはセッション開始時に `docs/CONTEXT.md` → このファイル → 今日の先頭レッスンの opening の順に読む（`content/README.md` §1）。
> 時間は目安。**実測に応じて動かしてよい**（`PRODUCTION_PLAN.md` §1-4）。

| 項目 | 内容 |
|---|---|
| 対象 | LEVEL 3 TIME MACHINE |
| 今日のレッスン | `MISSION-03-1` → `MISSION-03-2` |
| 合計時間 | 50分（25分＋25分） |
| XP | 200 |
| 備考 | 手を動かす量が少ないので2本。**この2本は別レッスン＝別セッション扱い。openingは2通とも送る** |

## 進行

| # | レッスン | 送るopening | 内部台本 | 時間 |
|---|---|---|---|---|
| 1 | Mission 3-1 差分(diff)を読む | `content/level03/opening-03-1.md` | `content/level03/mission-03-1.md` | 25分 |
| 2 | Mission 3-2 履歴をさかのぼる／HEAD | `content/level03/opening-03-2.md` | `content/level03/mission-03-2.md` | 25分 |

1本目の STEP 7（記録）を終えてから、休憩を挟んで2本目の opening を送る。

## 今日の到達点

- `docs/log/2026-08-15.md` が `notes/log/` へ移動している（`docs/CONTEXT.md` §3・§8 のパス記述も更新済み）
- `notes/glossary.md` に「差分」「HEAD」が自分の言葉で書かれている
- `notes/log/{今日の日付}.md` に成長ログ（8項目）が2件分

## 打ち切り基準

- **Mission 3-1 だけで終わってよい。** 返信が短くなる・「とりあえず」が増えたら、2本目に入らずSTEP 7で締める。
- 1本目の途中で切り上げる場合も、**STEP 7 の記録だけは必ず済ませる**（記録なしで終わらせない）。
- 3-2 を翌日に回した場合、Day 4 以降を1日ずつ後ろへずらす（Dayとレッスンの対応は固定ではない）。

## 進行AIへの注意

- Mission 3-1 でファイル移動が「削除＋追加」に見える。**「消えた」と誤解させない**（`docs/CONTEXT.md` §4 #2 の再発ポイント）。リポジトリの作り直しは絶対に提案しない。
- Mission 3-2 は「見に行くだけ」の回。**戻す操作（revert）の手順は一切出さない**（Mission 3-6 の内容）。`git checkout <ハッシュ>` は本教材では扱わない。
