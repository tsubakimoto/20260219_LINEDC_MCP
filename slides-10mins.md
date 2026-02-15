---
marp: true
theme: default
paginate: true
header: 'LINEボットでMCPサーバーを活用する'
footer: '© 2026'
---

<!-- _class: lead -->
# LINEボットでMCPサーバーを活用する

## ～GitHub Codespaces開発ガイド

**対象者**: MCPに興味がある、AIエージェントの仕組みを理解したい方

---

<!-- _class: lead -->
# 第1部: MCPの理解

---

## MCPとは

### Model Context Protocol (MCP)

MCPのアーキテクチャ:
- **ホスト**: VS Code、Claude Desktopなど
- **クライアント**: ホストに組み込まれたMCP接続管理部分
- **サーバー**: ツール、リソース、プロンプトを提供

### MCPが解決する課題
AIエージェントが外部ツール・リソースに**安全かつ構造化された**アクセスを実現

---

## MCPの利点

- **開発効率向上**
  - 新しいツールの実装が簡単

- **セキュリティ**
  - 認証・認可の標準化

- **スケーラビリティ**
  - 複数の外部リソースを一括管理

- **相互運用性**
  - 様々なAIエージェントで利用可能（GitHub Copilot、Claude、Cline等）

---

<!-- _class: lead -->
# 第2部: MCPサーバー開発

---

## MCPサーバーの構成要素

### 3つの主要コンポーネント

- **ツール**
  - AIエージェントが呼び出す関数
  - 入出力がスキーマで定義

- **リソース**
  - テキストやJSONドキュメントなど
  - 参考情報の提供

- **プロンプト**
  - AIエージェントへの指示テンプレート

---

## 認証とセキュリティ

### セキュアな開発のために

- **API キー管理**
  - 環境変数を使用した安全な管理

- **OAuth認証のサポート**
  - 標準的な認証フロー

- **MCP container化による分離**
  - セキュリティ境界の確立

- **ログとオーディット**
  - 操作の追跡と監査

---

<!-- _class: lead -->
# 第3部: LINEボットでの活用

---

## MCPサーバーとLINE Botの連携パターン

### 2つの連携パターン

**パターン1**: LINEボットがMCPサーバーの登録ツールを呼び出す
- LINEメッセージをトリガーにMCPツールを実行

**パターン2**: MCPサーバー経由でAIエージェントを制御
- AIエージェントがLINE APIを通じてユーザーと対話

### メリット
- LINEのユーザーフレンドリー性とMCPの柔軟性の組み合わせ

---

<!-- _class: lead -->
# 第4部: GitHub Codespaces活用

---

## GitHub Codespaceの利点

### クラウドベースの開発環境

- **ブラウザベースの開発環境**
  - どこからでもアクセス可能

- **高速な起動**
  - インスタンス起動時間: 通常1分以内

- **チーム共有**
  - 同じ環境をチームで共有可能

- **拡張機能サポート**
  - VS Codeの拡張機能そのまま利用可能

---

## 開発環境のセットアップ

### devcontainer.json設定例

```json
{
  "name": "MCP Development",
  "image": "mcr.microsoft.com/devcontainers/javascript-node:18",
  "features": {
    "ghcr.io/devcontainers/features/docker-in-docker:2": {}
  },
  "customizations": {
    "vscode": {
      "extensions": ["dbaeumer.vscode-eslint"]
    }
  }
}
```

### 環境構築
- Node.js / Python環境
- 必要なCLIツール（git, docker等）
- 環境変数設定（.env.example）
- 依存関係のインストール（npm/pip）

---

## デプロイ先の選択肢

### 環境に応じた選択

- **ローカルホスト**
  - 開発・テスト用
  - 迅速なイテレーション

- **クラウドプラットフォーム**
  - Railway, Render, Heroku等
  - 手軽なデプロイ

- **Azure App Service**
  - 本格的な運用用
  - エンタープライズグレードの可用性

---

<!-- _class: lead -->
# 第5部: まとめ

---

## まとめ

### 本日のポイント

- **MCPの概要**
  - 構造化された安全な相互作用を実現するプロトコル

- **サーバー開発のポイント**
  - ツール、リソース、プロンプトの3つの要素
  - セキュリティと認証の重要性

- **LINEボット連携のメリット**
  - ユーザーフレンドリー性と柔軟性の両立

- **Codespacesで効率的な開発可能**
  - 環境構築の簡素化とチーム開発の効率化

---

## 参考リソース

### さらに学ぶために

- **MCP公式サイト**
  https://modelcontextprotocol.io

- **Anthropic Claude API ドキュメント**
  Claude APIの詳細な使い方

- **LINE Messaging API ドキュメント**
  LINE Bot開発の公式ガイド

- **GitHub Codespaces ドキュメント**
  開発環境のセットアップガイド

- **サンプルコード**
  GitHub リポジトリで実装例を公開

---

<!-- _class: lead -->
# ありがとうございました

## Questions?
