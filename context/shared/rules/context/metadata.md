---
title: コンテキストメタデータルール
summary: YAML front matter の必須項目と値の扱いを決める。
type: rule
tags:
  - context-rule
  - metadata
aliases:
  - front matter
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/shared/rules/context/naming.md
---

# コンテキストメタデータルール

## 目的

Markdown ファイルを人間と AI エージェントの両方が安定して読み込めるようにする。

## 推奨 front matter

```yaml
---
title:
summary:
type:
tags:
aliases:
status:
created:
updated:
related:
---
```

## `type` の値

- `domain`
- `knowledge`
- `expertise`
- `experience`
- `rule`
- `project-doc`
- `prompt`
- `agent`
- `workflow`
- `decision`

## `status` の値

- `draft`: 下書き。
- `active`: 現在有効。
- `deprecated`: 置き換え予定または非推奨。
- `archived`: 履歴として残す。

記事コンテキストの読了状態は別途 `unread`、`summarized`、`reading`、`read`、`archived` を使ってよい。ただし、文書ライフサイクルの状態と混同しないように本文で意味を説明する。

## 日付

- `created` と `updated` は `YYYY-MM-DD` 形式で書く。
- 内容を更新したら `updated` も更新する。
- 不明な日付は空欄にせず、本文に `未確認` と書く。
