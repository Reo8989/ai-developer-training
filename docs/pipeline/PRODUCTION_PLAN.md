# PRODUCTION_PLAN.md ― 序盤コース（Day3〜）制作計画

> **このファイルは何か**：Day2 の続きから始まる序盤コース **10レッスン分**（LEVEL 3 の残り＋BOSS 1＋LEVEL 4 前半、合計330分＝約1.5〜2週分）の制作計画です。各レッスンについて、そのまま生成AIに貼れる **ミッション仕様YAML** を用意してあります。
> **誰がいつ使うか**：
> - **MooNさん**が、次に作るレッスンを決めて `PRODUCTION_GUIDE.md` §3 のループを回すとき。
> - **生成AI**が、§3 の各レッスンのミッション仕様をそのまま入力として受け取るとき。
> **仕様の正典はこのファイル。** 仕様を変えたくなったら、生成プロンプトを直すのではなく、まずこのファイルを直す。

---

# §1. 現在地と、この計画の範囲

## 1-1. 現在地（2026-08-16 時点）

| 項目 | 状態 |
|---|---|
| Day1（2026-08-15） | LESSON-00-SETUP 完了（LEVEL 2 の Mission 2-2〜2-8 相当を統合）。約90分 |
| Day2（2026-08-16） | Branch / Merge / Conflict / PR を**対話セッション内で体験**。レッスン台本ファイルは未作成。`feature/branch-practice` `feature/conflict-practice` の2ブランチと PR #3 が履歴に残っている |
| Issue #1 | 「MVP-0: Seed App v0.1 を作る」着手済み・未Close |
| LEVEL 3 の進捗 | Mission 3-3 / 3-4 / 3-5 を**操作としては体験済み**。ただし成果物（CHANGELOG.md、Conflict解決の記録）と成長ログが未作成。Mission 3-1 / 3-2 / 3-6 / 3-7 は未着手 |
| 教材アプリ | v0.3（GitHub Pages 未設定・Seed App 本体なし）。v0.4 の要件は CHANGELOG.md のブランチ運用 |

**この計画は「Day2 で体験したことを正式な成果物と記録に変換する」ところから始める。** 同じ操作を最初からやり直させない（進んでいない感覚を与えるため）。

## 1-2. 範囲と区切り

カリキュラム設計書の実際の区切りに従い、**PHASE 1 FOUNDATION の残り** を対象とする。

| 区切り | 内容 | 本計画での扱い |
|---|---|---|
| LEVEL 3 TIME MACHINE（Mission 3-1〜3-7） | 変更履歴を操る | **全7 Mission を8レッスンに分割して制作** |
| BOSS 1 RECOVERY | Mastery Gate（進行ゲート） | **制作する** |
| LEVEL 4 THE OFFICE（Mission 4-1〜4-4） | Issue → Branch → PR の一周 | **前半4 Missionを制作**（4-5〜4-7 と BOSS 2 は次バッチ） |
| LEVEL 5 IT MOVES | JavaScript | 範囲外（次々バッチ） |

**なぜ 4-4 で切るか**：Mission 4-4 まで進むと「Issue → Branch → PR → Merge の完全1周」が成立する。ここが LEVEL 4 の最初の自然な達成点であり、教材制作ワークフロー（`PRODUCTION_GUIDE.md` §3-7）と学習内容が一致する地点でもある。4-5「AIにレビューさせる」以降は、この1周ができていることが前提になる。

## 1-3. レッスン一覧（10本・合計330分）

| # | レッスンID | タイトル | 対応Mission | 形式 | 時間 | XP |
|---|---|---|---|---|---|---|
| 1 | `MISSION-03-1` | 差分(diff)を読む | 3-1 | 圧縮 | 25分 | 100 |
| 2 | `MISSION-03-2` | 履歴をさかのぼる／HEAD | 3-2 | 圧縮 | 25分 | 100 |
| 3 | `MISSION-03-3` + `MISSION-03-4` | Branchを切る／Mergeする（Day2体験の正式化＋CHANGELOG運用開始） | 3-3, 3-4 | 圧縮×2 | 45分 | 180 |
| 4 | `MISSION-03-5` | ⚠ Conflictを起こして解決する | 3-5 | **フル** | 30分 | 120 |
| 5 | `MISSION-03-6` | ⚠ AIに壊させてrevertで戻す | 3-6 | **フル** | 30分 | 120 |
| 6 | `MISSION-03-7` | 同じ操作をCLIで再現する | 3-7 | 圧縮 | 25分 | 100 |
| 7 | `BOSS-01` | RECOVERY BOSS | B1 | Boss | 60分 | 500 |
| 8 | `MISSION-04-1` | Issueで仕事を言葉にする | 4-1 | 圧縮 | 25分 | 100 |
| 9 | `MISSION-04-2` + `MISSION-04-3` | Issue TemplateとLabels／BranchとIssueの紐付け | 4-2, 4-3 | 圧縮×2 | 40分 | 160 |
| 10 | `MISSION-04-4` | Pull Requestを出す | 4-4 | 圧縮 | 25分 | 100 |

**台本ファイルは12本、openingは10本**（#3 と #9 は2 Mission を1セッションで扱うため、opening は先頭Missionのもの1本だけを送る。`PRODUCTION_GUIDE.md` §2-3）。

## 1-4. 日次への割り当て（`content/sessions/day-NN.md` の中身）

設計書に「1日◯Mission」の規定は無い（Mission は独立完結・1日30〜90分で1〜3 Mission）。以下は 1日45〜65分想定の目安であり、**実測に応じて動かしてよい**。

| Day | レッスン | 時間 | 備考 |
|---|---|---|---|
| Day 3 | #1（3-1）＋ #2（3-2） | 50分 | 手を動かす量が少ないので2本 |
| Day 4 | #3（3-3＋3-4） | 45分 | 教材アプリ **v0.4** 到達 |
| Day 5 | #4（3-5 Conflict） | 30分 | ⚠フル形式。心理的負荷が高いので単独 |
| Day 6 | #5（3-6 revert） | 30分 | ⚠フル形式。**LEVEL 3 の核心**。単独 |
| Day 7 | #6（3-7 CLI） | 25分 | 短い日。疲れていたらここで区切る |
| Day 8 | #7（BOSS 1） | 60分 | 分割可（CP1-2で1日、CP3-4で翌日） |
| Day 9 | #8（4-1）＋ #9（4-2＋4-3） | 65分 | LEVEL 4 突入 |
| Day 10 | #10（4-4） | 25分 | Issue→PR→Merge の1周が完成 |

合計 **330分／8日**。1日45分ペースなら約1.5週、60分ペースなら約1週強。

## 1-5. 制作着手の順序（制作は受講の1〜2レッスン先行で進める）

1. **先に `content/` の土台3ファイルを作る**：`content/README.md`、`content/metaphors.md`（`PRODUCTION_GUIDE.md` §5-2 の表をそのまま）、`content/level03/notional-machine-03.md`
2. **`content/level03/glossary-03.md` と `quizbank-03.md` を先に作る**（圧縮形式のレッスンがこれらを参照するため、レッスンより先に必要）
3. レッスンは #1 から順に、**2本先行**で作る（受講テストのフィードバックを #3 以降に反映できる余地を残す）
4. #4・#5（フル形式・⚠）は他より制作時間がかかる。**Day5の2日前には完成させておく**

---

# §2. 全レッスン共通の前提（生成AIに毎回伝わるもの）

以下は各レッスンのミッション仕様に**書かない**（毎回同じなので、`PRODUCTION_GUIDE.md` §1-2 のプロンプトが読ませるファイル群でカバーされる）。

- 学習者：`docs/CONTEXT.md` §2 を参照（Mac / GitHub Desktop 英語UI / VS Code / github.com 日本語UI / リポジトリは **public**）
- 過去のつまずき：`docs/CONTEXT.md` §4 の5件。特に **#1 Dropbox的自動同期の誤解** は再発しやすい
- 実行環境：**`file://`・ダブルクリック起動は禁止**（CO-01）。ローカルは Live Server、公開は GitHub Pages
- `reset` は教えない（CO-18）
- 比喩は `content/metaphors.md` から取る
- 表記：GitHub Desktop＝英語ボタン名、github.com＝日本語ボタン名＋括弧で英語原名

---

# §3. レッスン別ミッション仕様（そのまま生成AIに渡せる形）

---

## #1 `MISSION-03-1` 差分(diff)を読む

| 項目 | 内容 |
|---|---|
| 学習目標 | GitHub Desktop の差分表示で「何が追加され、何が削除され、何が移動したか」を、コードを書かずに読み分けられる |
| 前提 | Day2 まで完了（Commit / Push / Branch / Merge を操作したことがある） |
| 所要時間 | 25分（100 XP） |
| 形式 | 圧縮形式 |
| 成果物 | `notes/log/` への移動Commit（リネームが diff でどう見えるかの実例）、`notes/glossary.md` に自分の言葉での「差分」定義 |

**制作時の注意点**

- **この回の教材素材は「`docs/log/2026-08-15.md` を `notes/log/` へ移動する」作業そのもの**（`PRODUCTION_GUIDE.md` §2-4 の実装ギャップ解消をここで行う）。実作業を教材にすることで、練習用のダミー変更を作らずに済む。
- リネームは GitHub Desktop 上で「削除＋追加」に見えることがある。**これがつまずきポイント**（ファイルが消えたと誤解する。CONTEXT.md §4 #2 の再発パターン）。必ず ⚠ ブロックで先に潰す。
- 「AIの変更を検証する中心スキル」であることを完了表示で明示する（LEVEL 12 の AI 出力検証、LEVEL 15 の Dry-run diff への伏線）。
- 手を動かす量が少ない回なので、**STEP 4 のミッションは「読ませる」課題**にする（過去の自分のCommitの差分を1件選んで、何が起きたかを3行で説明させる）。

```yaml
lesson_id: MISSION-03-1
mission_no: "3-1"
mission_name: "差分(diff)を読む"
level: 3
level_name: "変更履歴を操る"
codename: "TIME MACHINE"
format: compact
duration_min: 25
xp: 100
skills: ["GH"]
marks: []

goal: |
  GitHub Desktop の差分表示を読み、「何が追加され／削除され／移動したか」を
  自分の言葉で説明できるようにする。これはAIが書いた変更を検証する中心スキルである。

prerequisites: |
  Day2 まで完了。Commit / Push / Branch / Merge / PR を操作したことがある。
  ただし差分を「読む」ことを目的にした練習はまだしていない。

new_terms: ["差分（diff）", "追加行 / 削除行（+ / -）", "リネーム（ファイルの移動）"]

deliverables:
  - "docs/log/2026-08-15.md を notes/log/ へ移動したCommit"
  - "notes/glossary.md に自分の言葉で書いた「差分」の定義"

practical_material: |
  練習用のダミー変更は作らない。実際に必要な作業を素材にする：
  docs/log/2026-08-15.md を notes/log/2026-08-15.md へ移動し、
  その移動が GitHub Desktop の差分でどう見えるかを読ませる。
  移動後、docs/CONTEXT.md §3 と §8 のパス記述も notes/log/ に更新する
  （2種類の差分＝「移動」と「1行書き換え」を1セッションで見比べられる）。

forecast_required: |
  「ファイルを移動すると、GitHub Desktop の画面では『元の場所から消えた』ように見えることがあります。
  消えていません。これは予定された見え方です」を、移動操作の直前に予告する。

must_include:
  - "GitHub Desktop の Changes タブと History タブで差分を見る2つの入口"
  - "緑（追加）／赤（削除）の読み分け"
  - "1行だけ書き換えた場合、diffでは『削除1行＋追加1行』として表示されること"
  - "この技能が LEVEL 12（AIの出力を検証する）と LEVEL 15（Dry-runのdiff確認）の土台になる予告"

must_not_include:
  - "git diff の CLI コマンド（Mission 3-7 で扱う）"
  - "resetによる巻き戻し（CO-18）"
  - "file://・ダブルクリック起動（CO-01）"

past_stumbles_to_reference: [2]

metaphors:
  差分（diff）: "契約書の変更箇所に引いた赤線"

why_deep_dive: |
  なぜGitは「変更後のファイル全体」ではなく「差分」を見せるのか
  （設計思想まで書く1箇所はここ。AIに大量のコードを書かせる時代に、
  全文を読むのではなく差分だけを読む技能が中心になる理由まで踏み込む）

mission_task: |
  自分の過去のCommitを1件選び、その差分を読んで
  「何が追加され、何が削除され、なぜそうしたのか」を3行で説明させる。
  コードは1行も書かせない。

next_mission: "3-2 履歴をさかのぼる／HEAD"
```

---

## #2 `MISSION-03-2` 履歴をさかのぼる／HEAD

| 項目 | 内容 |
|---|---|
| 学習目標 | History から過去のCommitの状態を見に行き、「今どこにいるか（HEAD）」を画面上で指させる |
| 前提 | Mission 3-1 完了（差分が読める） |
| 所要時間 | 25分（100 XP） |
| 形式 | 圧縮形式 |
| 成果物 | `notes/glossary.md` への HEAD の自分の言葉での定義、成長ログ |

**制作時の注意点**

- **「見に行く」と「戻す」を絶対に混同させない。** この回は「見る」だけ。戻すのは Mission 3-6。混同すると、学習者が履歴を見に行った状態で不安になる（detached HEAD 的な体験への恐怖）。
- GitHub Desktop の History タブでは detached HEAD にならない安全な閲覧ができる。**CLI の `git checkout <hash>` は絶対に出さない**（Mission 3-7 でも出さない）。
- Mission 3-6 の revert の前提として「どのCommitが原因か特定する」感覚を作る回。BOSS 1 のチェックポイント2（原因Commitの特定と根拠）に直結することを明示する。

```yaml
lesson_id: MISSION-03-2
mission_no: "3-2"
mission_name: "履歴をさかのぼる／HEAD"
level: 3
level_name: "変更履歴を操る"
codename: "TIME MACHINE"
format: compact
duration_min: 25
xp: 100
skills: ["GH"]
marks: []

goal: |
  GitHub Desktop の History から過去のCommitの中身を見に行き、
  「今自分がどのCommitの状態にいるのか（HEAD）」を画面上で指させるようにする。
  「見る」ことと「戻す」ことは別であると理解させる。

prerequisites: |
  Mission 3-1 完了（差分が読める）。

new_terms: ["History（履歴）", "HEAD", "Commitハッシュ"]

deliverables:
  - "notes/glossary.md に自分の言葉で書いた HEAD の定義"
  - "成長ログ（notes/log/YYYY-MM-DD.md）"

forecast_required: |
  「今日は過去を『見に行く』だけで、『戻す』ことはしません。戻すのは3日後のMission 3-6です」
  をopeningと本文の両方で明言する（見に行った状態で不安にならないように）。

must_include:
  - "History タブでCommitを1件クリックすると、そのCommitの差分だけが表示されること"
  - "HEAD は『今いる場所を指す矢印』であり、通常は最新Commitを指していること"
  - "Commitハッシュは長いが、先頭7文字だけで実用上は特定できること"
  - "BOSS 1 で『どのCommitが原因かを特定して根拠を書く』課題が出る予告"

must_not_include:
  - "git checkout <ハッシュ>（detached HEAD になる操作は一切教えない）"
  - "reset / rebase（CO-18）"
  - "revert の実行（Mission 3-6 の内容。名前だけ予告するのは可）"

past_stumbles_to_reference: [2]

metaphors:
  HEAD: "「現在地」のピン"
  History（履歴）: "作業日誌をページごとにめくって読み返すこと"

why_deep_dive: |
  なぜ「見る」と「戻す」を分ける必要があるのか
  （Gitは見るだけなら何も壊れない。この安心が、大胆に試せることの前提になる）

mission_task: |
  History から「Day1で設計書一式を追加したCommit」を自力で見つけさせ、
  そのCommitで何ファイルが追加されたかを答えさせる。

next_mission: "3-3 Branchを切る / 3-4 Mergeする"
```

---

## #3 `MISSION-03-3` + `MISSION-03-4` Branchを切る／Mergeする（Day2体験の正式化）

| 項目 | 内容 |
|---|---|
| 学習目標 | Day2 で操作として体験した Branch / Merge を、命名規則と成果物（`CHANGELOG.md`）を伴う「運用」として定着させる。教材アプリ v0.4 に到達する |
| 前提 | Mission 3-2 完了。Day2 で Branch / Merge / PR を1周した経験がある |
| 所要時間 | 45分（3-3：25分＋3-4：20分／合計180 XP） |
| 形式 | 圧縮形式×2（台本2本・opening 1本） |
| 成果物 | `CHANGELOG.md`（main にマージ済み）、Branch命名規則を書いた `notes/glossary.md`、Squash Merge の設定 |

**制作時の注意点**

- **Day2 でやったことを最初からやり直させない。** openingで「今日は前回やった操作を、名前をつけて『いつも同じ手順』に固める回です」と位置づける。同じ操作の反復に見せると、進んでいない感覚を与える。
- 3-3 の主眼は**命名規則**（`feature/` `fix/` `docs/`）。Day2 では `day2-practice` という場当たり的な名前を使ったので、**その名前が後から何の作業か分からないこと**を実例として使える（自分の過去のブランチ名を批評させる）。
- 3-4 の主眼は **Squash Merge に統一する理由**。LEVEL 15 で Agent の PR を読むときの可読性が根拠（01 LEVEL 4）。github.com のリポジトリ設定で Squash Merge のみを有効にする操作までやる。
- `CHANGELOG.md` は LEVEL 17 で AI 会社の成果記録として再利用される（01 LEVEL 3）。この伏線を完了表示に入れる。
- **教材アプリ v0.4 到達点。** 完了表示で「教材アプリが v0.4 になった」と明示する。
- Day2 で作った `day2-practice` `day2-conflict-practice` ブランチが残っている場合、**削除させる**（不要になったコピーは片付ける、を運用として教える）。

```yaml
lesson_id: MISSION-03-3
mission_no: "3-3"
mission_name: "Branchを切る"
level: 3
format: compact
duration_min: 25
xp: 100
skills: ["GH"]
marks: []

goal: |
  Day2 で操作として体験した Branch を、命名規則を伴う「運用」に固める。
  ブランチ名を見ただけで何の作業か分かる状態を作る。

prerequisites: |
  Mission 3-2 完了。Day2 で New Branch → Commit → Publish branch → PR → Merge を1周している。

new_terms: ["Branch命名規則（feature/ fix/ docs/）", "Current Branch", "ブランチの削除"]

deliverables:
  - "docs/changelog というブランチ（命名規則に従った初めてのブランチ）"
  - "notes/glossary.md に自分の言葉で書いた Branch の定義と命名規則"
  - "不要になった day2-practice / day2-conflict-practice ブランチの削除"

session_framing: |
  「今日は前回やった操作を、名前をつけて『いつも同じ手順』に固める回です」と位置づける。
  やり直しではないことをopeningで明言する。

must_include:
  - "自分がDay2で付けた day2-practice というブランチ名を自分で批評させる（後から何の作業か分かるか）"
  - "feature/ = 新機能、fix/ = 不具合修正、docs/ = 文書 の3つだけ覚える"
  - "Mergeが終わったブランチは削除してよい理由（コピーの内容は正本に転記済み）"

must_not_include:
  - "reset / rebase（CO-18）"
  - "git branch のCLIコマンド（Mission 3-7 で扱う）"

past_stumbles_to_reference: [1, 3]

metaphors:
  Branch: "正本はそのまま金庫に置き、下書き用にコピーを1枚取って赤ペンで書き込む"

mission_task: |
  docs/changelog という名前でブランチを切り、CHANGELOG.md を新規作成して
  v0.1〜v0.4 の変更履歴を書き、Commitさせる（Mergeは 3-4 で行う）。

next_mission: "3-4 Mergeする"
```

```yaml
lesson_id: MISSION-03-4
mission_no: "3-4"
mission_name: "Mergeする"
level: 3
format: compact
duration_min: 20
xp: 80
skills: ["GH"]
marks: []

goal: |
  ブランチの成果を main に合流させる。Squash Merge に統一する理由を理解し、
  リポジトリ設定でそれを強制する。教材アプリ v0.4 に到達する。

prerequisites: |
  Mission 3-3 完了（docs/changelog ブランチに CHANGELOG.md がCommitされている）。

new_terms: ["Merge", "Squash Merge", "Delete branch"]

deliverables:
  - "main にマージされた CHANGELOG.md（教材アプリ v0.4）"
  - "リポジトリ設定で Squash Merge のみ有効化"

must_include:
  - "github.com の Settings → General → Pull Requests で Allow squash merging のみ残す操作"
  - "Squash Merge に統一する理由：LEVEL 15 で AI Agent の PR を読むときの履歴の可読性（01 LEVEL 4）"
  - "Merge後に GitHub Desktop で main に切り替え、Pull origin でローカルにも届けること（郵送の比喩に戻す）"
  - "CHANGELOG.md は LEVEL 17 で AI会社の成果記録として再利用される予告"

must_not_include:
  - "reset / rebase（CO-18）"
  - "Merge commit / Rebase merge を選ばせる（Squashに統一する）"

past_stumbles_to_reference: [1]

metaphors:
  Merge: "下書きコピーの修正を、確認のうえ正式な原本に転記する"

why_deep_dive: |
  なぜ Squash Merge に統一するのか
  （設計思想まで書く1箇所はここ。履歴は「後から読む人（未来の自分とAI）」のためにあり、
  読みやすさのために情報を意図的に捨てる判断がある、という話まで踏み込む）

completion_note: |
  完了表示で「教材アプリ v0.4 に到達した」ことを明示する。

next_mission: "3-5 ⚠ Conflictを起こして解決する"
```

---

## #4 `MISSION-03-5` ⚠ Conflictを起こして解決する

| 項目 | 内容 |
|---|---|
| 学習目標 | 自分の Branch と main で同じ行を編集し、意図的に Conflict を起こして解決する。コンフリクトマーカーを見てもパニックにならない |
| 前提 | Mission 3-4 完了（Merge の一周ができる） |
| 所要時間 | 30分（120 XP） |
| 形式 | **フル形式**（01 6.2.2 の40Mission。T+E型） |
| 成果物 | 解決済み Conflict の Merge Commit、`errors/conflict-YYYY-MM-DD.md` |

**制作時の注意点**

- **フル形式（300〜420行。`QUALITY_CHECKLIST.md` CHK-C13 の2026-08-16改訂値）。** 40Mission 一覧で T+E 型（恐怖＋エラー）に分類されている最重要地点のひとつ。分量を惜しまない。
- **CO-10 厳守**：Conflict は**学習者自身のリポジトリ内で完結**させる。「教材コンテンツの取り込み」「`upstream` からの Merge」を起点にしない。
- **予告を2箇所**（openingと、衝突を起こす操作の直前）。「これは失敗ではなく予定された演習です。必ず解決できます」を明言。
- **最大の危険はリポジトリを作り直そうとすること**（01 LEVEL 3 つまずき表）。台本の「使い方メモ」に「作り直しは絶対に提案しない」と書く。
- **Day2 で既に Conflict を1回経験している。** その事実を活かし、openingで「前回は一緒に解決しました。今日は自分ひとりで最後まで解決します」と位置づける。**短縮運用の指示**：受講テスト時、STEP 2 の誘導部分を学習者が「もう分かる」と言った場合は STEP 4 まで飛ばしてよい。ただし STEP 6（理解チェック）と STEP 7（記録）は必ずやる。**Day2 で作らなかった `errors/` の記録を作るのが、この回の実質的な目的。**
- `<<<<<<< HEAD` `=======` `>>>>>>>` の**記号を全部消す**ことを、太字で最低2回書く（消し忘れが最頻の失敗）。
- ブランチ切り替え時に VS Code の表示が古いままになる問題（Day2 で実際に注意した点）を ⚠ ブロックに入れる。

```yaml
lesson_id: MISSION-03-5
mission_no: "3-5"
mission_name: "⚠ Conflictを起こして解決する"
level: 3
level_name: "変更履歴を操る"
codename: "TIME MACHINE"
format: full
duration_min: 30
xp: 120
skills: ["GH"]
marks: ["⚠"]

goal: |
  自分のBranchとmainで同じ行を別々に編集し、Merge時に意図的にConflictを発生させて、
  自力で解決する。コンフリクトマーカーを見ても慌てないことを技能として身につける。

prerequisites: |
  Mission 3-4 完了（Branch → Commit → Merge の一周ができる）。
  Day2 でAIと一緒にConflictを1回解決した経験がある。

session_framing: |
  「前回は一緒に解決しました。今日は自分ひとりで、最後まで解決します。
  そして『どう解決したか』を記録に残します」と位置づける。

new_terms: ["Conflict（衝突）", "コンフリクトマーカー（<<<<<<< HEAD / ======= / >>>>>>>）", "Resolve（解決）"]

deliverables:
  - "解決済みConflictのMerge Commit"
  - "errors/conflict-YYYY-MM-DD.md（エラー学習フォーマットでの記録）★この回の実質的な目的"

conflict_setup: |
  CO-10 厳守。学習者自身のリポジトリ内で完結させる：
  ① docs/changelog-conflict ブランチを切り、CHANGELOG.md の同じ行を書き換えてCommit
  ② mainに戻り、同じ行を違う内容に書き換えてCommit（Pushはしない）
  ③ main上で Branch メニュー → Merge into current branch... で衝突を発生させる
  教材コンテンツの取り込みやupstreamからのMergeを起点にしてはならない。

forecast_required: |
  2箇所で予告する。
  ① opening：「今日は途中でわざと衝突を起こします。見慣れない記号が出ますが、
     これは失敗ではなく予定された演習です。必ず解決できます」
  ② 衝突を起こす操作の直前：「これから『1 conflicted file』という警告が出ます。
     これが今日の目的です。慌てなくて大丈夫です」

must_include:
  - "<<<<<<< HEAD から ======= までがmain側、======= から >>>>>>> までがブランチ側 という読み方"
  - "記号を全部消すこと（太字で最低2回。消し忘れが最頻の失敗）"
  - "どちらか一方でも、両方を組み合わせた新しい一文でもよいこと（人間が決める）"
  - "ブランチを切り替えるとVS Code上のファイル内容も切り替わるため、開きっぱなしだと古い表示のままに見えることがある"
  - "解決後、GitHub Desktop で Commit merge を押してマージを完了させること"
  - "Publish branch ではなく Push origin の表示に戻ることの確認（CONTEXT.md §4 #3 の再確認）"

must_not_include:
  - "リポジトリを作り直す・cloneし直すという選択肢（絶対に提示しない）"
  - "reset による衝突の回避（CO-18）"
  - "教材コンテンツ（content/）の取り込みによるConflict（CO-10）"
  - "rebase"

past_stumbles_to_reference: [2, 3]

metaphors:
  Conflict: "同じ契約書の同じ条項を、2人が別々に書き換えて送ってきた"

why_deep_dive: |
  なぜGitは自動でどちらかを選ばないのか
  （設計思想まで書く1箇所はここ。「機械が判断できないことは人間に返す」という
  設計判断であり、これがLEVEL 14の承認ゲートと同じ思想であることまで踏み込む）

mission_task: |
  STEP 2 でガイド付きで1回解決したあと、STEP 4 では2回目の衝突を
  学習者が自分で仕込んで自分で解決する。
  さらに errors/conflict-YYYY-MM-DD.md に「症状・原因・解決手順・次に同じことが起きたら」を書かせる。

next_mission: "3-6 ⚠ AIに壊させてrevertで戻す"
```

---

## #5 `MISSION-03-6` ⚠ AIに壊させてrevertで戻す

| 項目 | 内容 |
|---|---|
| 学習目標 | AI に教材アプリ／READMEを全面的に作り直させて意図的に壊し、`revert` で復旧する。「AIに大胆な変更をさせても戻せる」という確信を体で持つ |
| 前提 | Mission 3-5 完了 |
| 所要時間 | 30分（120 XP） |
| 形式 | **フル形式**（T型・**このLEVELの核心**） |
| 成果物 | AI に壊された状態からの revert Commit（**LEVEL 3 で最も重要な成果物**）、`notes/log/` への記録 |

**制作時の注意点**

- **フル形式。LEVEL 3 全体の核心。** ここが成立しないと LEVEL 15 で Agent に書き込み権限を渡す設計が崩れる。分量と丁寧さを最優先。
- **CO-18 の中心地点**：`reset` を教えない／`revert` のみ。**AI が `git reset --hard` を提案してくる場面を、教材の中で意図的に作る**（学習者が実際に AI に「戻して」と頼むと高確率で提案される）。そのときの3手順（①実行しない ②`revert` でできないか聞き返す ③それでも必要なら人間に相談）を体験として通す。
- 壊す対象は **`README.md` または `CHANGELOG.md`**（教材アプリ本体はまだ存在しない）。「AIに『READMEを全面的に書き直して、構成も変えて』と依頼する」形が現実的。
- **予告が最重要。** 予告なしに壊すと「自分には向いていない」という一般化された結論を与える（06 3.1）。openingと壊す直前の2箇所で予告。
- revert の性質「取り消した記録を新たに1つ積むので、取り消し自体を取り消せる」を必ず体験させる（revert を revert して戻す実演）。**これが「戻せるという確信」の核心**。
- BOSS 1 の直前レッスン。完了表示で BOSS 1 の内容（3件のCommitのうち1件だけをrevert）を予告する。

```yaml
lesson_id: MISSION-03-6
mission_no: "3-6"
mission_name: "⚠ AIに壊させてrevertで戻す"
level: 3
level_name: "変更履歴を操る"
codename: "TIME MACHINE"
format: full
duration_min: 30
xp: 120
skills: ["GH", "AI"]
marks: ["⚠"]

goal: |
  AIに README.md を全面的に作り直させて意図的に壊し、revert で復旧する。
  「AIに大胆な変更をさせても、必ず戻せる」という確信を体験として持たせる。
  これがLEVEL 15でAI Agentに書き込み権限を渡せることの前提になる。

prerequisites: |
  Mission 3-5 完了（Conflictを自力で解決した）。

new_terms: ["Revert", "Restore（変更の破棄）", "Reset（本教材では使わないことを学ぶ）"]

deliverables:
  - "AIに壊された状態からのrevert Commit ★LEVEL 3で最も重要な成果物"
  - "notes/log/YYYY-MM-DD.md への『AIが壊した変更を戻せた』体験の記録"

break_procedure: |
  ① 壊す前に必ずCommitする（戻れる地点を作る）
  ② AIに「README.md を全面的に書き直してください。構成も見出しも全部変えてください」と依頼する
  ③ 変更を適用してCommitする（意図的に壊れた状態を履歴に残す）
  ④ 差分を読んで「何が失われたか」を確認する（Mission 3-1 の技能を使う）
  ⑤ GitHub Desktop の History でそのCommitを右クリック →
     Revert changes in commit（このコミットの変更を取り消す）を実行
  ⑥ revert によって新しいCommitが1件積まれたことを確認する
  ⑦ さらに、その revert 自体を revert して元に戻せることを実演する

forecast_required: |
  2箇所で予告する。
  ① opening：「今日は途中で、AIにわざとファイルを壊してもらいます。
     これは予定された演習で、必ず元に戻せます。むしろ『戻す』ことが今日の学習内容です」
  ② 壊す操作の直前：「これから README.md が全く別のものになります。
     驚くと思いますが、戻せます。戻す手順はこのあと一緒にやります」

must_include:
  - "壊す前に必ずCommitする（Commitしていない変更は戻す手段がない）"
  - "revert＝訂正印を押して差し戻す（履歴が残る）／reset＝記録ごと破り捨てる（履歴が消える）の対比"
  - "revertは『取り消した』という記録を新たに1つ積む操作なので、取り消し自体を取り消せること（実演する）"
  - "AIが git reset --hard を提案してきたときの3手順：①実行しない ②revertでできないか聞き返す ③それでも必要なら人間に相談"
  - "この3手順は LEVEL 9『AIが提示するコマンドを読む』で再登場する予告"
  - "BOSS 1 の予告：3件のCommitのうち、正しい2件を保ったまま問題の1件だけをrevertする"

must_not_include:
  - "reset の使い方・実行手順（CO-18。禁止事項としての言及のみ可）"
  - "rebase"
  - "git revert のCLIコマンドを主手順にする（GUIが主。CLIは Mission 3-7）"
  - "壊す対象を教材アプリ本体にする（まだ存在しない。README.md か CHANGELOG.md を使う）"

past_stumbles_to_reference: [1, 2]

metaphors:
  Revert: "訂正印を押して差し戻す（元の記録は残る）"
  Reset: "記録ごと破り捨てる（本教材では使わない）"

why_deep_dive: |
  なぜこの教材は reset を教えないのか
  （設計思想まで書く1箇所はここ。「戻せるという確信」を作ることが目的であり、
  戻し方を知らない学習者にとって reset は「消えた」ようにしか見えないため、
  選択肢そのものを教材構造から取り除いた、という判断まで踏み込む。
  末尾の「では、いつrevertを使ってはいけないか？」も必ず書く）

mission_task: |
  STEP 2 でガイド付きで1回revertしたあと、STEP 4 では学習者が自分でAIに壊させ、
  自分でrevertして戻す。さらに「AIにgit reset --hardを提案させて、それを断る」までを1往復やる。

next_mission: "3-7 同じ操作をCLIで再現する"
```

---

## #6 `MISSION-03-7` 同じ操作をCLIで再現する

| 項目 | 内容 |
|---|---|
| 学習目標 | GUI でやってきた操作を CLI コマンドと対応づけ、AI が提示するコマンドを**読める**ようになる（暗記はしない） |
| 前提 | Mission 3-6 完了 |
| 所要時間 | 25分（100 XP） |
| 形式 | 圧縮形式 |
| 成果物 | `notes/level03-cli.md`（GUI↔CLI 対応表・自作） |

**制作時の注意点**

- **目標は「読める」であって「暗記」ではない**（01 LEVEL 3 つまずき対策）。冒頭で明言する。
- **危険なコマンドを打たせない。** 扱うのは `git status` / `git log --oneline` / `git branch` / `git diff` の**読み取り系4つ**まで。`git reset` `git checkout <hash>` `rm` は出さない（CO-18／LEVEL 9 の 9-9 で扱う）。
- 対応表は**学習者が自分で書く**（教材が完成表を渡さない）。自分で書くから記憶に残る。
- VS Code の Terminal（`Terminal` → `New Terminal`）から実行する。黒い画面への恐怖は LEVEL 0 の 0-3 で扱い済みという前提だが、**Day1・Day2 でターミナルを一度も使っていない**可能性が高いので、⚠ ブロックで「打ち間違えても何も壊れないコマンドだけを使います」と明言する。

```yaml
lesson_id: MISSION-03-7
mission_no: "3-7"
mission_name: "同じ操作をCLIで再現する"
level: 3
format: compact
duration_min: 25
xp: 100
skills: ["GH", "DEV"]
marks: []

goal: |
  GUIでやってきた操作をCLIコマンドと対応づけ、AIが提示するコマンドを「読める」ようにする。
  暗記は目的ではない。

prerequisites: |
  Mission 3-6 完了（revert で復旧できた）。

new_terms: ["Terminal", "git status", "git log --oneline"]

deliverables:
  - "notes/level03-cli.md（GUI操作とCLIコマンドの対応表・学習者が自分で書く）"

allowed_commands: |
  読み取り系4つだけを扱う：git status / git log --oneline / git branch / git diff
  これ以外のコマンドは打たせない。

forecast_required: |
  「今日打つのは、打ち間違えても何も壊れないコマンドだけです。
  『見るだけ』のコマンドなので安心してください」を最初に明言する。

must_include:
  - "VS Code の Terminal メニュー → New Terminal から開くこと"
  - "目標は『読める』ことであり暗記ではないと冒頭で明言"
  - "対応表は教材が渡さず、学習者が自分で書くこと"
  - "AIが提示するコマンドを読めることが、LEVEL 9『AIが提示するコマンドを読む』の土台になる予告"

must_not_include:
  - "git reset / git checkout <ハッシュ> / rm / git push --force（CO-18 および LEVEL 9 の 9-9 の内容）"
  - "git add / git commit を主手順にする（GUIが主。存在の紹介まで）"
  - "rebase"

past_stumbles_to_reference: []

metaphors: {}

mission_task: |
  notes/level03-cli.md に、GUI操作4つ（変更の確認／履歴を見る／ブランチ一覧／差分を見る）と
  対応するCLIコマンドの表を、学習者自身の言葉で書かせる。

next_mission: "BOSS 1 RECOVERY"
```

---

## #7 `BOSS-01` RECOVERY BOSS

| 項目 | 内容 |
|---|---|
| 学習目標 | 壊れた状態のリポジトリから、正しい変更を保ったまま問題の1件だけを特定して復旧する。**LEVEL 4 への進行ゲート** |
| 前提 | Mission 3-1〜3-7 完了 |
| 所要時間 | 60分（500 XP。CP単位で複数日に分割可） |
| 形式 | **Boss形式**（7STEPではない。チェックポイント4個） |
| 成果物 | 復旧後のリポジトリ、`notes/recovery.md`（復旧手順の文書化） |
| 評価する能力軸 | **軸C（復旧力）Lv2**（この Boss 以外に C Lv2 を与える経路はない） |

**制作時の注意点**

- **`TEMPLATE_lesson.md` §4 の Boss差分に従う。** 7STEP を使わない。チェックポイント4個（各15〜20分）。
- **CO-09 厳守**：B1 はアプリ画面を使わない。**Markdown 教材＋GitHub 上での実施**、判定は AI レビュー＋自己申告。
- **CO-29 厳守**：自動判定に使ってよいのは「ファイルの存在」「revert Commit の有無」「`reset --hard` を使っていないこと（履歴が壊れていないこと）」などの**事実**のみ。原因特定の根拠は AI レビュー（ルーブリック）。
- **「壊れたリポジトリ」の調達方法**：設計書の `broken-repo-samples`（06 B-3）はまだ存在しない。**v1 では、進行AIがその場で学習者のリポジトリに3件のCommitを作って壊す方式で代替する**（`PRODUCTION_GUIDE.md` §6 判断12）。Boss台本に「壊し方の手順（進行AI用・学習者には見せない）」を付録として同梱する。
  - 壊し方の3件：①`CHANGELOG.md` に正しい追記（残すべき） ②`README.md` の見出し構造を破壊し、`notes/level03-cli.md` を削除（これが問題の1件） ③`notes/glossary.md` に正しい追記（残すべき）
  - **②を真ん中のCommitにする**（最新Commitを消せば済む、という安易な解法を封じる）
- **Boss は不合格でも進行を止めない設計ではない。Boss だけが進行ゲート**（01 1.1）。ただし再挑戦は何度でも可であることを明示する。
- 完了表示で「軸C（復旧力）Lv2 到達」を提示する（CO-04 の1対1対応に従う）。

```yaml
lesson_id: BOSS-01
boss_no: "B1"
boss_name: "RECOVERY BOSS"
level_after: 3
format: boss
duration_min: 60
xp: 500
capability_axis: "C（復旧力）Lv2"
provision: "Markdown教材＋GitHub上で実施。アプリ画面は使わない（CO-09）"

goal: |
  壊れた状態のリポジトリから、正しい2件の変更を保ったまま、
  問題を起こしている1件だけを特定してrevertし、動く状態に復旧する。

task_statement: |
  あなたのリポジトリに、AIに依頼した結果として3件のCommitが積まれています。
  そのうち2件は正しく、1件だけが問題を起こしています。
  正しい2件を保ったまま、問題の1件だけを取り消し、動く状態に復旧してください。

broken_state_setup: |
  ★進行AI用（学習者には見せない）。その場で学習者のリポジトリに3件のCommitを作る：
  Commit A（正しい）: CHANGELOG.md に v0.4 の記述を追記
  Commit B（問題）  : README.md の見出し構造を破壊し、notes/level03-cli.md を削除
  Commit C（正しい）: notes/glossary.md に用語を1件追記
  順序は A → B → C とし、問題のCommitを真ん中に置く
  （最新Commitを取り消せば済む、という安易な解法を封じるため）。

checkpoints:
  - cp: 1
    content: "3件のCommitがそれぞれ何をしたかを、差分から説明する"
    minutes: 15
  - cp: 2
    content: "どのCommitが原因かを特定し、その根拠を文章で書く"
    minutes: 15
  - cp: 3
    content: "正しい2件の変更を保ったまま復旧する"
    minutes: 20
  - cp: 4
    content: "復旧手順を notes/recovery.md に記録する"
    minutes: 10

completion_criteria:
  - "3件のCommitの内容を差分から説明できた"
  - "原因のCommitを特定し、根拠を文章で示せた"
  - "正しい2件の変更（CHANGELOG.md の追記・notes/glossary.md の追記）が失われていない"
  - "README.md が読める状態に戻り、notes/level03-cli.md が復活している"
  - "復旧手順が notes/recovery.md に文書化されている"

judgement:
  auto:
    - "notes/recovery.md が存在する"
    - "revert Commit が履歴に存在する"
    - "CHANGELOG.md と notes/glossary.md の追記が残っている"
    - "notes/level03-cli.md が存在する"
    - "履歴が壊れていない（reset --hard が使われていない）"
  ai_review:
    - "原因特定の根拠が、差分の事実に基づいているか（推測だけになっていないか）"
    - "復旧手順の記録が、次に同じことが起きたときに再現できる粒度か"
  self_report:
    - "何分かかったか"
    - "どこで一番迷ったか"

must_include:
  - "Bossは進行ゲートであること。ただし再挑戦は何度でも可であることを明示"
  - "時間切れになったらCP単位で日をまたいでよいこと"
  - "AIに解かせてはいけないこと（AIは質問には答えるが、手順を代行しない）"

must_not_include:
  - "reset の使用（CO-18。使ったら不合格になることを明記）"
  - "アプリのBoss画面・LEVELマップ画面への依存（CO-09）"
  - "コード内容の静的解析に依存する自動判定条件（CO-29）"

completion_display: |
  「あなたは今、履歴から問題箇所を特定して戻せるようになりました」
  軸C（復旧力）Lv2 到達 / Stage 2 達成・Stage 3 着手 / +500 XP
  次：LEVEL 4 THE OFFICE。Mission 4-1「Issueで仕事を言葉にする」
```

---

## #8 `MISSION-04-1` Issueで仕事を言葉にする

| 項目 | 内容 |
|---|---|
| 学習目標 | Issue を5要素（目的／現状／期待する結果／制約／完了条件）で書ける。**Issue を書く力＝AI に指示を出す力**の同型性を体験する |
| 前提 | BOSS 1 突破 |
| 所要時間 | 25分（100 XP） |
| 形式 | 圧縮形式 |
| 成果物 | 5要素を満たす Issue 3件 |

**制作時の注意点**

- **本カリキュラムの隠れた中核。** 「Issue の5要素」＝「STEP 5 の AI への質問8項目」＝「LEVEL 15 で Agent に渡す指示」が同型であることを、この回で明示的に接続する。
- **白紙から書かせない**（01 LEVEL 4 つまずき対策）。5要素のテンプレートを worked example として先に渡す。
- **既存の Issue #1 を素材にできる**：Day1 で作った Issue #1「MVP-0: Seed App v0.1 を作る」は、既に5要素の簡易版で書かれている（`lesson_00_setup.md` STEP 2-9）。**自分が書いた Issue を自分で採点させる**のが最良の導入。
- **CO-02 注意**：`MVP-0`（教材提供側の最小配布物）と `MVP-L`（学習者が育てるアプリ）を区別して書く。Issue #1 は MVP-0 の話。
- **CO-30 は 4-7 の内容**（初期Issue同梱）だが、4-1 でも「テンプレートリポジトリに初期Issueがある」ことに軽く触れてよい。

```yaml
lesson_id: MISSION-04-1
mission_no: "4-1"
mission_name: "Issueで仕事を言葉にする"
level: 4
level_name: "GitHubでチーム開発"
codename: "THE OFFICE"
format: compact
duration_min: 25
xp: 100
skills: ["GH"]
marks: []

goal: |
  Issueを5要素（目的／現状／期待する結果／制約／完了条件）で書けるようにする。
  「Issueを書く力＝AIに指示を出す力」の同型性を体験させる。

prerequisites: |
  BOSS 1 突破。LEVEL 3 完了。

new_terms: ["Issueの5要素", "完了条件（Definition of Done）", "制約"]

deliverables:
  - "5要素を満たすIssue 3件（GitHub上）"

practical_material: |
  Day1で作ったIssue #1「MVP-0: Seed App v0.1 を作る」を素材にする。
  すでに5要素の簡易版で書かれているので、自分が書いたIssueを自分で採点させる導入が使える。

must_include:
  - "5要素のテンプレートを先に渡す（白紙から書かせない。worked example）"
  - "Issueの5要素 = STEP 5 のAIへの質問8項目 = LEVEL 15 でAgentに渡す指示、の同型性"
  - "「完了条件」が最も書きにくく最も重要であること（何をもって終わりとするか）"
  - "1人開発でもIssueを書く理由：未来の自分とAIに見せるため"
  - "MVP-0（教材提供側が作る最小配布物）と MVP-L（学習者が育てるアプリ）の区別（CO-02）"

must_not_include:
  - "Issue Template の作成（Mission 4-2 の内容）"
  - "Branch との紐付け（Mission 4-3 の内容）"
  - "「MVP」の無限定な使用（CO-02）"

past_stumbles_to_reference: []

metaphors:
  Issue: "付箋にタスクを1つ書いて、みんなが見えるボードに貼る／業務依頼票"

why_deep_dive: |
  なぜ「完了条件」を先に書くのか
  （設計思想まで書く1箇所はここ。完了条件を書けない依頼は、
  人間にもAIにも渡せない。これがLEVEL 15でAgentに仕事を渡せるかどうかを分ける、という話まで）

mission_task: |
  「学習アプリを改善する」Issueを、5要素を満たす形で自力で2件書かせる
  （Issue #1 の採点と合わせて計3件）。

next_mission: "4-2 Issue Template と Labels"
```

---

## #9 `MISSION-04-2` + `MISSION-04-3` Issue TemplateとLabels／BranchとIssueの紐付け

| 項目 | 内容 |
|---|---|
| 学習目標 | 5要素の型をテンプレートとして固定し、Issue と Branch を番号で紐づける |
| 前提 | Mission 4-1 完了 |
| 所要時間 | 40分（4-2：20分＋4-3：20分／合計160 XP） |
| 形式 | 圧縮形式×2（台本2本・opening 1本） |
| 成果物 | `.github/ISSUE_TEMPLATE/`、Labels、Issue番号に対応した Branch |

**制作時の注意点**

- 4-2：`.github/ISSUE_TEMPLATE/` の**ディレクトリ名の正確さ**がつまずきポイント（ドット始まり・大文字小文字）。VS Code で作らせる（Finder では作らない。`lesson_00_setup.md` STEP 2-3 と同じ理由）。⚠ ブロック必須。
- 4-2：Labels は**増やしすぎない**。3〜5個（`bug` `enhancement` `docs` `learning`）に絞る。Projects の3列（Todo / Doing / Done）制限と同じ思想（高度な機能を使わせない）。
- 4-3：`Closes #12` と書くと Merge 時に Issue が自動でCloseされる記法を扱う。**自動Closeは便利だが、Issue の完了条件を満たしていないのに閉じてしまう危険**があることも同時に教える（Day2 で「Issue #1 を今日Closeしない」判断をした経験に接続できる）。
- 4-3：Branch 名に Issue 番号を入れる規則（`feature/12-xxx`）を、Mission 3-3 で決めた命名規則の**拡張**として提示する（新しいルールではなく、既存ルールに1要素足すだけ）。

```yaml
lesson_id: MISSION-04-2
mission_no: "4-2"
mission_name: "Issue Template と Labels"
level: 4
format: compact
duration_min: 20
xp: 80
skills: ["GH"]
marks: []

goal: |
  Mission 4-1 で身につけた5要素を、Issue Template として固定する。
  以降のIssueは必ずこの型を使うようにする。

prerequisites: |
  Mission 4-1 完了（5要素のIssueを3件書いた）。

new_terms: ["Issue Template", "Labels", ".github/ ディレクトリ"]

deliverables:
  - ".github/ISSUE_TEMPLATE/task.md（5要素の型）"
  - "Labels 3〜5個（bug / enhancement / docs / learning）"

must_include:
  - ".github/ISSUE_TEMPLATE/ は VS Code で作る（Finderでは作らない。ドット始まりのため）"
  - "Labels は3〜5個に絞る（増やしすぎると分類が機能しなくなる）"
  - "テンプレートを作ると、次のIssue作成時に自動で本文が入ることの確認"

must_not_include:
  - "Issue Forms（YAML形式）の高度な機能"
  - "Milestone の設定（今回は扱わない）"

past_stumbles_to_reference: [4]

metaphors:
  Labels: "付箋の色分け"

mission_task: |
  作ったテンプレートを使って、実際にIssueを1件新規作成させる
  （テンプレートが自動で挿入されることを目で確認させる）。

next_mission: "4-3 BranchとIssueを紐づける"
```

```yaml
lesson_id: MISSION-04-3
mission_no: "4-3"
mission_name: "BranchとIssueを紐づける"
level: 4
format: compact
duration_min: 20
xp: 80
skills: ["GH"]
marks: []

goal: |
  Issue番号をBranch名に入れ、Commit/PRからIssueを参照できるようにする。
  「どの作業がどの依頼に対応するか」が後から辿れる状態を作る。

prerequisites: |
  Mission 4-2 完了（Issue Template と Labels がある）。

new_terms: ["Issue参照（#番号）", "自動クローズ記法（Closes #番号）", "Issue番号付きBranch名"]

deliverables:
  - "Issue番号に対応したBranch（例：feature/12-add-progress-days）"

must_include:
  - "Mission 3-3 で決めた命名規則（feature/ fix/ docs/）にIssue番号を足すだけであること"
  - "PR本文やCommit messageに #12 と書くとIssueに自動でリンクされること"
  - "Closes #12 と書くとMerge時にIssueが自動でCloseされること"
  - "★自動Closeの危険：完了条件を満たしていないのにIssueが閉じてしまう。
     Day2 で『Issue #1 は今日Closeしない』と判断したのと同じ考え方を再確認する"

must_not_include:
  - "Pull Request の作成手順（Mission 4-4 の内容）"
  - "Branch protection（Mission 4-6 の内容）"

past_stumbles_to_reference: []

metaphors: {}

mission_task: |
  Mission 4-1 で書いた自分のIssueのうち1件を選び、
  対応するBranchを命名規則どおりに切らせる。

next_mission: "4-4 Pull Requestを出す"
```

---

## #10 `MISSION-04-4` Pull Requestを出す

| 項目 | 内容 |
|---|---|
| 学習目標 | Issue → Branch → PR → Merge の完全1周を、記録の質を意識して実行する |
| 前提 | Mission 4-3 完了 |
| 所要時間 | 25分（100 XP） |
| 形式 | 圧縮形式 |
| 成果物 | 「何を・なぜ・どう確認したか」を書いた PR 1件（Merge済み）、Close された Issue 1件 |

**制作時の注意点**

- **このバッチの到達点。** 完了表示で「Issue → Branch → PR → Merge の完全1周ができた」ことを最大表示する。
- Day2 で PR は作成済みだが、**PR 本文を書いていない**。この回の主眼は「PR 本文に何を書くか」（何を・なぜ・どう確認したか の3点）。
- **Squash Merge** は Mission 3-4 で設定済み。ここでは設定を再度いじらせない。
- Merge 後の `Pull origin` を忘れると、次の作業が古い main の上で始まる。**CONTEXT.md §4 #1（郵送の比喩）に戻す最後の機会**として ⚠ ブロックを置く。
- 完了表示で、次バッチ（4-5 AIにレビューさせる／4-6 mainを守る／4-7 学習バックログ／BOSS 2）を予告する。特に **4-6 は「自分が push できなくなる」ことを成功体験として予告する必要がある**（フル形式・E型）ため、ここで軽く伏線を張っておくとよい。

```yaml
lesson_id: MISSION-04-4
mission_no: "4-4"
mission_name: "Pull Requestを出す"
level: 4
format: compact
duration_min: 25
xp: 100
skills: ["GH"]
marks: []

goal: |
  Issue → Branch → PR → Merge の完全1周を、記録の質を意識して実行する。
  PR本文に「何を・なぜ・どう確認したか」を書けるようにする。

prerequisites: |
  Mission 4-3 完了（Issue番号付きBranchで作業中）。

new_terms: ["Pull Request 本文の3点（何を・なぜ・どう確認したか）", "Review", "Draft PR"]

deliverables:
  - "PR本文の3点が書かれたPR 1件（Merge済み）"
  - "CloseされたIssue 1件"

must_include:
  - "PR本文の3点：何を変えたか／なぜその判断をしたか／どうやって正しさを確認したか"
  - "Day2 ではPRを作ったが本文を書かなかったこと。今回はそこを埋める回であること"
  - "Squash Merge は Mission 3-4 で設定済み。設定は触らない"
  - "Merge後に GitHub Desktop で main に切り替え、Pull origin する（忘れると次の作業が古いmainの上で始まる）"
  - "1人開発でもPRを出す理由：未来の自分とAIに見せるため＋LEVEL 15でAIが使う仕組みの練習"

must_not_include:
  - "AIにレビューさせる手順（Mission 4-5 の内容）"
  - "Branch protection の設定（Mission 4-6 の内容）"
  - "reset（CO-18）"

past_stumbles_to_reference: [1, 3]

metaphors:
  Pull Request: "「この内容を正本に反映していいですか」と提出する回覧書"
  Review: "上司の検収・品質確認"

mission_task: |
  Mission 4-3 で切ったBranchで実際に変更を1つ加え、
  PR本文の3点を自分で書いてPRを作成し、Mergeまで行わせる。

completion_display: |
  「あなたは今、Issue → Branch → PR → Merge の完全な1周ができるようになりました」
  この流れは、LEVEL 15 で AI Agent が同じ道を通ることになる仕組みそのものです。
  次バッチの予告：4-5 AIにレビューさせる／4-6 mainを守る（自分がpushできなくなります。
  それが成功です）／4-7 学習バックログ／BOSS 2 GITHUB

next_mission: "4-5 AIにレビューさせる（次バッチ）"
```

---

# §4. このバッチの外側（次に作るもの）

| 順序 | 内容 | 備考 |
|---|---|---|
| 次バッチ1 | Mission 4-5「AIにレビューさせる」（30分・圧縮） | 自分とAIのレビューを比較。`notes/level04-review.md` |
| 次バッチ2 | Mission 4-6「🛡 mainを守る」（25分・**フル形式**） | E型。自分がpushできなくなることを**成功体験として予告**する必要がある |
| 次バッチ3 | Mission 4-7「🧩 学習バックログを作る」（20分・圧縮） | **CO-30**：初期Issue同梱を前提に書く。Projectsは3列に限定 |
| 次バッチ4 | BOSS 2 GITHUB（90分・Boss形式） | 軸B（指示力）Lv2。**PHASE 1 完了地点**。CO-09によりアプリ画面を使わない |
| 次々バッチ | LEVEL 5 IT MOVES（9 Mission） | **5-6 / 5-7 / 5-8 / 5-9 の4本がフル形式**。LEVEL 5 はほぼ全Missionが高リスク指定。制作工数が跳ね上がる点に注意 |

**LEVEL 5 に入る前に決めておくべきこと**

- Seed App（Issue #1・MVP-0）の実体。LEVEL 5 の Mission 5-9 は「教材アプリ v1.0 が動く」ことがゴールであり、それまでに `progress.html` が存在している必要がある
- Live Server 拡張の導入（CO-01。本来 LEVEL 1 の最終Missionだが、LEVEL 1 を飛ばしているため LEVEL 5 に入る前に補う必要がある）
- GitHub Pages の公開設定（Mission 2-8 相当。`lesson_00_setup.md` で意図的に見送っている）
