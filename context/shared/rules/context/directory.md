---
title: コンテキストディレクトリルール
summary: 共有コンテキストとプロジェクト固有コンテキストの置き場所を決める。
type: rule
tags:
  - context-rule
  - directory
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/README.md
---

# コンテキストディレクトリルール

## 目的

知識、経験、ルール、判断を適切な場所に置き、将来の自分と AI エージェントが迷わず読み込めるようにする。

## ルール

- 複数プロジェクトで使える内容は `context/shared/` に置く。
- この技術知識管理システムだけに関係する内容は `context/projects/tech-knowledge/` に置く。
- 技術領域の前提は `domains/` または `domain/` に置く。
- 概念説明は `knowledge/` に置く。
- 設計や実装の実践知は `expertise/` に置く。
- 個人の経験や失敗から得た学びは `experience/` に置く。
- 再利用可能な判断基準や運用規約は `rules/` に置く。
- プロジェクト文書は `context/projects/tech-knowledge/docs/` に置く。
- プロンプトは `context/projects/tech-knowledge/prompts/` に置く。
- エージェント定義は `context/projects/tech-knowledge/agents/` に置く。
- ワークフローは `context/projects/tech-knowledge/workflows/` に置く。
- 設計判断は `context/projects/tech-knowledge/decisions/` に置く。

## 判断基準

迷った場合は、「他のプロジェクトでも使えるか」を先に判断する。使えるなら `shared`、このプロジェクトの仕様に依存するなら `projects/tech-knowledge` に置く。
