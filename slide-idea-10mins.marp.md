---
marp: true
paginate: true
title: LINEボットでMCPサーバーを活用する〜GitHub Codespaces開発ガイド
description: slide-idea-10minsの内容をMarp形式で整備
---

# LINEボットでMCPサーバーを活用する〜GitHub Codespaces開発ガイド
- 対象: MCPに興味がある / AIエージェントの仕組みを理解したい

---

## MCPとは
- Model Context Protocol (MCP) の概要
- アーキテクチャ: ホスト / クライアント / サーバー
- 解決する課題: 外部ツール・リソースへの安全で構造化されたアクセス

---

## MCPの利点
- 開発効率: 新しいツールを簡潔に実装
- セキュリティ: 認証・認可の標準化
- スケーラビリティ: 複数リソースの一元管理
- 相互運用性: Copilot, Claude, Cline などで利用可能

---

## MCPサーバーの構成要素
- ツール: スキーマ付きの関数呼び出し
- リソース: テキストやJSONなどの参照情報
- プロンプト: エージェント向けテンプレート

---

## 認証とセキュリティ
- APIキー管理とローテーション
- OAuth対応
- コンテナ分離による隔離
- ログ / オーディット

---

## LINE Bot連携パターン
- パターン1: LINEボットから登録ツールを直接呼び出し
- パターン2: MCP経由でAIエージェントを制御
- データフロー図の提示

---

## GitHub Codespacesの利点
- ブラウザベースで即起動
- 共有しやすい統一環境
- VS Code拡張をそのまま利用
- 1分以内の起動目安

---

## 開発環境のセットアップ
- devcontainer.json例: Node.js / Python + CLIツール
- .env.exampleで環境変数を管理
- npm / pipで依存関係を導入

---

## デプロイ先の選択肢
- ローカルホスト（開発）
- Railway / Render / Heroku 等
- Azure App Service（運用）

---

## まとめ
- MCP概要とサーバー開発の要点
- LINEボット連携のメリット
- Codespacesで効率的に開発

---

## 参考リソース
- MCP公式: https://modelcontextprotocol.io
- Anthropic Claude API ドキュメント
- LINE Messaging API ドキュメント
- GitHub Codespaces ドキュメント
- サンプルコード（GitHubリポジトリ）
