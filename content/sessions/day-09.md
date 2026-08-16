# day-09.md ― Day 9 進行表

> 進行AIはセッション開始時に `docs/CONTEXT.md` → このファイル → 今日の先頭レッスンの opening の順に読む（`content/README.md` §1）。

| 項目 | 内容 |
|---|---|
| 対象 | **LEVEL 4 THE OFFICE 突入** |
| 今日のレッスン | `MISSION-04-1` → （`MISSION-04-2` ＋ `MISSION-04-3`） |
| 合計時間 | 65分（25分＋40分） |
| XP | 260 |
| 備考 | **2セッション分。** 1本目（4-1）と2本目（4-2＋4-3）は別セッション扱いで、openingを**2通**送る |

## 進行

| # | レッスン | 送るopening | 内部台本 | 時間 |
|---|---|---|---|---|
| 1 | Mission 4-1 Issueで仕事を言葉にする | `content/level04/opening-04-1.md` | `content/level04/mission-04-1.md` | 25分 |
| 2 | Mission 4-2 Issue Template と Labels | `content/level04/opening-04-2.md` | `content/level04/mission-04-2.md` | 20分 |
| 3 | Mission 4-3 BranchとIssueを紐づける | **送らない**（4-2 と同一セッション） | `content/level04/mission-04-3.md` | 20分 |

4-3 に入るときは opening を再送せず、`mission-04-3.md` の STEP 0 の質問2問を**対話の中で口頭出題**する。

## 今日の到達点

- 5要素を満たす Issue 3件（Issue #1 の採点＋新規2件）
- `.github/ISSUE_TEMPLATE/task.md` が **main にMerge済み**（Branchに置いたままでは動かない）
- Labels 4つ（`bug` / `enhancement` / `docs` / `learning`）
- Issue番号付きBranch（例：`feature/2-fix-typo`）が Publish 済み ← **Day 10 の 4-4 でそのまま使う**

## 打ち切り基準

- **Mission 4-1 だけで終わってよい。** 65分は本バッチで最長の日。
- 4-2 に入ったら、**テンプレートのmainへのMergeまでは同じ日に終える**（Branchに置いたまま翌日に持ち越すと、翌日の動作確認で「作ったのに出てこない」という不要な失敗を踏む）。
- 4-3 を翌日に回す場合、Day 10 が 4-3＋4-4 になる。時間は同じく40〜45分。

## 進行AIへの注意

- 4-1：**白紙から書かせない。** 5要素のテンプレートを worked example として先に渡し、まず Day1 の Issue #1 を自分で採点させる。
- 4-1：**MVP-0（教材提供側の最小配布物。Issue #1 がこれ）と MVP-L（学習者が育てるアプリ）を区別する**（CO-02）。「MVP」単独表記は使わない。
- 4-2：`.github/ISSUE_TEMPLATE/` は**必ずVS Codeで作らせる**（Finderでは作らない。ドット始まり・大文字小文字。§4 #4 の再発ポイント）。
- 4-2：**動作確認の前にmainへMergeする手順（STEP 2 手順9〜12）を飛ばさない。** GitHubはmainのテンプレートしか読まない。
- 4-2：Labels は3〜5個で止める。「あとで増やそうか」と言い出したら「今日は増やさない」と明言してよい。
- 4-2・4-3：新しいBranchを2本切るので `Publish branch` 表示が**2回**出る（§4 #3）。どちらも押す前に予告する。
- 4-3：Issue番号は必ずIssueページを開いて目で確認させてから書かせる。
