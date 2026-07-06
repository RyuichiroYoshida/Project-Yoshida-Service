---
title: コンテキストライフサイクルルール
summary: コンテキストを作成、更新、非推奨化、保管する流れを決める。
type: rule
tags:
  - context-rule
  - lifecycle
aliases: []
status: draft
created: 2026-07-07
updated: 2026-07-07
related:
  - context/shared/rules/context/metadata.md
---

# コンテキストライフサイクルルール

## 目的

コンテキストを増やすだけでなく、古い情報や未確認情報の扱いを明確にする。

## 作成

1. 置き場所を決める。
2. front matter を書く。
3. 目的、背景、本文、関連リンクを書く。
4. `status: draft` として保存する。

## 更新

1. 変更理由を本文に反映する。
2. 関連リンクを見直す。
3. `updated` を更新する。
4. 必要なら `status` を変更する。

## 有効化

- 内容が現在の判断に使える状態になったら `status: active` にする。
- まだ仮説を含む場合は `draft` のままにする。

## 非推奨化

- 新しい方針に置き換わったら `status: deprecated` にする。
- 置き換え先のファイルを `related` と本文に書く。

## 保管

- 履歴として残すだけの内容は `status: archived` にする。
- アーカイブしても、学びや背景が重要な場合は削除しない。
