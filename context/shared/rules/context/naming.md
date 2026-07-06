---
title: コンテキスト命名ルール
summary: ファイル名、タイトル、タグの付け方を決める。
type: rule
tags:
  - context-rule
  - naming
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/shared/rules/context/metadata.md
---

# コンテキスト命名ルール

## 目的

ファイル名とタグを安定させ、検索と AI 読み込みをしやすくする。

## ファイル名

- ファイル名は原則として英小文字の `kebab-case` にする。
- 日本語の本文タイトルは `title` と H1 に書く。
- ADR は `0001-use-markdown-context.md` のように連番を付ける。
- プロンプトは目的が分かる動詞から始める。
- サンプルやテンプレートには `sample` または `template` を含める。

## タイトル

- `title` は日本語で具体的に書く。
- コード名、API 名、サービス名は正式表記を使う。
- タイトルだけで対象が分かるようにする。

## タグ

- タグは英小文字の `kebab-case` を基本にする。
- 似た意味のタグを増やしすぎない。
- 技術領域、用途、状態を表すタグを優先する。
