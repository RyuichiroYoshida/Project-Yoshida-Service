---
title: 技術知識管理システム要件
summary: MVP で扱う範囲と、初期段階では扱わない範囲を定義する。
type: project-doc
tags:
  - tech-knowledge
  - requirements
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/projects/tech-knowledge/docs/overview.md
  - context/projects/tech-knowledge/docs/roadmap.md
---

# 技術知識管理システム要件

## MVP スコープ

最初の MVP は小さく保ち、次の機能に集中する。

1. 記事 URL を登録する。
2. タイトル、URL、メタデータを保存する。
3. AI で短い要約を生成する。
4. 自分のメモを追加する。
5. タグを付ける。
6. 読了状態を管理する。
7. 日次または週次サマリーを生成する。
8. 結果を再利用可能な Markdown コンテキストとして保存する。

## 初期段階でやらないこと

- browser extension
- 複雑な Web dashboard
- full RAG system
- vector database
- advanced knowledge graph
- multi-agent automation

## 記事モデル

記事は URL だけで保存せず、少なくとも次の情報を扱う。

```yaml
title:
url:
source:
published_at:
read_at:
status:
tags:
summary:
learned:
related_concepts:
related_projects:
priority:
```

## 推奨する記事ステータス

- `unread`
- `summarized`
- `reading`
- `read`
- `archived`

## 開発方針

- Markdown でコンテキストを保存する。
- Git で履歴を管理する。
- 最初は simple CLI または script を優先する。
- API や UI は後から追加する。
- AI 要約には必ず人間のメモを追加できるようにする。
- AI 要約よりも、自分の学びのメモを重視する。
