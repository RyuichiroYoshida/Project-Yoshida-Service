---
title: "ADR 0001: コンテキストを Markdown で管理する"
summary: 初期 MVP ではコンテキスト保存形式として Markdown と Git を採用する。
type: decision
tags:
  - adr
  - markdown
  - context
aliases:
  - use markdown context
status: active
created: 2026-07-07
updated: 2026-07-07
related:
  - context/projects/tech-knowledge/docs/requirements.md
  - context/shared/rules/context/metadata.md
---

# ADR 0001: コンテキストを Markdown で管理する

## 背景

このプロジェクトでは、技術記事、要約、自分のメモ、知識カード、設計判断を長期的に再利用できる形で保存したい。

初期段階では、複雑な DB、RAG、ナレッジグラフよりも、読み書きしやすく Git で管理できる形式を優先する。

## 決定

初期 MVP では、コンテキストを Markdown ファイルとして保存する。各ファイルには YAML front matter を付け、Git で履歴管理する。

## 理由

- 人間が直接読める。
- AI エージェントが読み込みやすい。
- Git で差分と履歴を追える。
- 小さく始められる。
- 将来、DB、検索、RAG、外部ツールへ移行しやすい。

## 検討した代替案

- DB に直接保存する: 初期 MVP には実装量が大きい。
- Notion で管理する: 手軽だが、AI エージェントや Git との連携を標準化しにくい。
- Obsidian 専用形式にする: Markdown 互換はあるが、特定ツール前提に寄りすぎる。
- いきなり RAG を構築する: 価値検証前の過剰実装になる。

## 影響

- 初期実装は Markdown ファイルの作成・更新を中心にできる。
- front matter と命名規則を守らないと後から検索しにくくなる。
- 将来 DB 化する場合も、Markdown を元データまたはエクスポート形式として扱える。

## ステータス

採用。
