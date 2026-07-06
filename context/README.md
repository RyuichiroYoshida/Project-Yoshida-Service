---
title: コンテキスト管理ルート
summary: 共有コンテキストとプロジェクト固有コンテキストの入口。
type: project-doc
tags:
  - context
  - bootstrap
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - docs/context-bootstrap.md
---

# コンテキスト管理ルート

このディレクトリは、技術記事、学習内容、設計判断、AI エージェント向けの前提知識を Markdown として蓄積する場所です。

## 基本方針

- 本文は日本語で書く。
- コード、API 名、外部サービス名、ファイル名、コマンド名は英語表記を維持する。
- 1 ファイルには 1 つの概念、ルール、判断、またはテンプレートだけを書く。
- 共有できる知識と、このプロジェクト固有の知識を分ける。
- 将来の自分と AI エージェントが読み直せる粒度で書く。

## ディレクトリ構造

```text
context/
├── shared/
│   ├── domains/
│   ├── knowledge/
│   ├── expertise/
│   ├── experience/
│   └── rules/
└── projects/
    └── tech-knowledge/
        ├── context/
        │   ├── domain/
        │   ├── rules/
        │   ├── knowledge/
        │   └── expertise/
        ├── docs/
        ├── prompts/
        ├── agents/
        ├── workflows/
        └── decisions/
```

## AI コンテキスト読み込み順

1. `context/shared/rules/`
2. `context/shared/knowledge/`
3. `context/shared/expertise/`
4. `context/shared/experience/`
5. `context/projects/tech-knowledge/context/`
6. `context/projects/tech-knowledge/docs/`
7. `context/projects/tech-knowledge/workflows/`
8. `context/projects/tech-knowledge/agents/`
9. タスク固有ファイル

## 初期状態

この初期セットでは、実装コードは追加せず、コンテキスト管理の土台となる Markdown テンプレートだけを作成する。
