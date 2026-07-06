---
title: 技術知識管理システムロードマップ
summary: 小さな MVP から将来拡張へ進むための段階的な計画。
type: project-doc
tags:
  - tech-knowledge
  - roadmap
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/projects/tech-knowledge/docs/requirements.md
---

# 技術知識管理システムロードマップ

## Phase 0: コンテキスト管理の土台

- `context/` ディレクトリ構造を作成する。
- 共有ルールを作成する。
- プロジェクト文書を作成する。
- サンプル記事とサンプル知識カードを作成する。
- 初期プロンプトを作成する。

## Phase 1: 最小の記録フロー

- 記事 URL を記録する。
- 記事メタデータを Markdown に保存する。
- 読了状態を管理する。
- 自分のメモを追加する。

## Phase 2: AI 要約

- 記事本文または抜粋から短い要約を生成する。
- 要約と自分のメモを分けて保存する。
- 関連タグと関連概念を抽出する。

## Phase 3: 知識カード化

- 記事から再利用可能な概念を抽出する。
- 1 概念 1 ファイルの知識カードに分解する。
- 関連リンクを追加する。

## Phase 4: レビューと再利用

- 日次または週次サマリーを生成する。
- 読んだ記事よりも、学んだ内容を中心に振り返る。
- AI エージェントが読み込めるコンテキストとして整備する。

## 将来拡張候補

- Discord daily notification
- RSS/API article ingestion
- Qiita/Zenn/Hacker News integration
- Notion or Obsidian export
- full-text search
- embedding search
- RAG
- knowledge graph
- browser extension
- AI agent automation
- weekly/monthly learning review
