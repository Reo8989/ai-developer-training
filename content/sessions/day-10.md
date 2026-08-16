# day-10.md ― Day 10 進行表

> 進行AIはセッション開始時に `docs/CONTEXT.md` → このファイル → 今日の opening の順に読む（`content/README.md` §1）。

| 項目 | 内容 |
|---|---|
| 対象 | LEVEL 4 THE OFFICE |
| 今日のレッスン | `MISSION-04-4` Pull Requestを出す |
| 合計時間 | 25分 |
| XP | 100 |
| 備考 | **このバッチの到達点。** Issue → Branch → PR → Merge の完全1周が完成する |

## 進行

| # | レッスン | 送るopening | 内部台本 | 時間 |
|---|---|---|---|---|
| 1 | Mission 4-4 Pull Requestを出す | `content/level04/opening-04-4.md` | `content/level04/mission-04-4.md` | 25分 |

## 前提の確認（開始前）

- [ ] Mission 4-3 で切った **Issue番号付きBranchが存在し、Publish 済み**であること
  - ここが済んでいるため、**今日のボタンは `Publish branch` ではなく `Push origin`** になる。押す前にそう予告する
- [ ] 対応する Issue が Open のままであること（`Closes #番号` で閉じるのは今日）

## 今日の到達点

- 「何を・なぜ・どう確認したか」の3点が書かれた PR 1件（Squash Merge 済み）
- `Closes #番号` によって自動 Close された Issue 1件
- `Pull origin` 済みで、ローカルの main が GitHub 上の main と一致している

## 打ち切り基準

- 短い回なので分割は想定しない。ただし PR 作成まで終えて Merge を翌日に回す場合は、**PRを Draft ではなく通常のPRとして残したまま**終えてよい。
- **`Pull origin` を押さずに終えない。** ここを飛ばすと、次バッチの最初の作業が古い main の上で始まる。

## 進行AIへの注意

- **予告の訂正に注意**：このBranchは 4-3 で公開済みなので、ボタンは `Push origin`。「`Publish branch` を探しても見つからない」ことを先に伝える（§4 #3 の裏返し）。
- Merge方式は Mission 3-4 で Squash のみに設定済み。ボタンは `スカッシュしてマージする`（Squash and merge）→ `マージを確定する`（Confirm squash merge）。**設定画面は開かせない。**
- github.com の PR 説明欄は空のまま送信できてしまう。**「書き終えましたか？」と声に出して確認してから**作成ボタンを押させる（Day2 でPR本文を書かずに出した反省点）。
- Merge 後の `Pull origin` が **CONTEXT.md §4 #1（同期ではなく郵送）に戻す最後の機会**。⚠ ブロックを飛ばさない。
- 完了表示で「Issue → Branch → PR → Merge の完全1周ができた」ことを最大表示する。あわせて次バッチ（4-5 / 4-6 / 4-7 / BOSS 2）を予告し、**4-6「mainを守る」では自分がpushできなくなること、それが成功であること**に軽く触れておく。

## このバッチの終わり

Day 10 をもって、`PRODUCTION_PLAN.md` §1-3 の10レッスン（330分）が完了する。次バッチ（Mission 4-5〜4-7・BOSS 2）は未制作。**受講テストの結果を各台本の「制作メモ」と `docs/CONTEXT.md` §4 に反映してから**、次バッチの制作に入ること（`PRODUCTION_GUIDE.md` §3-6）。
