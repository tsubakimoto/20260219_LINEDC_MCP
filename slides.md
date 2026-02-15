---
marp: true
theme: default
paginate: true
header: 'LINEボットでMCPサーバーを活用する'
footer: '© 2026'
---

<!-- _class: lead -->
<!-- _paginate: false -->

# LINEボットでMCPサーバーを活用する

## GitHub Codespaces開発ガイド

**対象者**: MCPに興味がある、AIエージェントの仕組みを理解したい方

---

<!-- _class: lead -->

# 第1部: MCPの理解

---

## MCPとは

**Model Context Protocol (MCP)** - AIエージェントと外部ツール・リソースを接続するプロトコル

### MCPのアーキテクチャ

- **ホスト**: VS Code、Claude Desktopなど
- **クライアント**: ホストに組み込まれたMCP接続管理部分
- **サーバー**: ツール、リソース、プロンプトを提供

### MCPが解決する課題

AIエージェントが外部ツール・リソースに**安全かつ構造化されたアクセス**を実現

---

## MCPの利点

### 開発効率向上
新しいツールの実装が簡単

### セキュリティ
認証・認可の標準化

### スケーラビリティ
複数の外部リソースを一括管理

### 相互運用性
様々なAIエージェントで利用可能（GitHub Copilot、Claude、Cline等）

---

<!-- _class: lead -->

# 第2部: MCPサーバー開発

---

## MCPサーバーの構成要素

### ツール
AIエージェントが呼び出す関数（入出力がスキーマで定義）

### リソース
テキストやJSONドキュメントなど（参考情報の提供）

### プロンプト
AIエージェントへの指示テンプレート

---

## 認証とセキュリティ

### API キー管理
環境変数による安全な管理

### OAuth認証のサポート
外部サービスとの安全な連携

### MCP container化による分離
セキュリティ境界の明確化

### ログとオーディット
アクセス記録と監査証跡

---

<!-- _class: lead -->

# 第3部: LINEボットでの活用

---

## MCPサーバーとLINE Botの連携パターン

### パターン1
LINEボットがMCPサーバーの登録ツールを呼び出す

### パターン2
MCPサーバー経由でAIエージェントを制御

### データフロー
```
ユーザー → LINE Bot → MCPサーバー → AIエージェント → 外部ツール
```

**メリット**: LINEのユーザーフレンドリー性とMCPの組み合わせ

---

<!-- _class: lead -->

# 第4部: GitHub Codespaces活用

---

## GitHub Codespaceの利点

### ブラウザベースの開発環境
どこからでもアクセス可能

### インスタンス起動時間
通常1分以内で準備完了

### 同じ環境をチームで共有可能
再現性の高い開発環境

### VS Codeの拡張機能そのまま利用可能
既存のワークフローを維持

---

## 開発環境のセットアップ

### devcontainer.json設定例

```json
{
  "name": "MCP Development",
  "image": "mcr.microsoft.com/devcontainers/typescript-node:20",
  "features": {
    "ghcr.io/devcontainers/features/docker-in-docker": {}
  }
}
```

### 環境変数設定
- `.env.example` でテンプレート提供
- 必要なAPI キーの定義

### 依存関係のインストール
- `npm install` / `pip install`

---

## デプロイ先の選択肢

### ローカルホスト
開発・テスト用途

### クラウドプラットフォーム
- Railway
- Render
- Heroku

### Azure App Service
本格的な運用用（エンタープライズ対応）

**ポイント**: 環境構築の簡素化、チーム開発・学習効率の向上

---

<!-- _class: lead -->

# 第5部: まとめ

---

## まとめ

### MCPの概要
AIエージェントと外部ツールを安全に接続するプロトコル

### サーバー開発のポイント
最小限で動作するサンプルから始める

### LINEボット連携のメリット
ユーザーフレンドリーなインターフェースとAIの組み合わせ

### Codespacesで効率的な開発可能
初心者からエキスパートまで対応可能な開発環境

---

## 参考リソース

### 公式ドキュメント
- [MCP公式サイト](https://modelcontextprotocol.io)
- [Anthropic Claude API ドキュメント](https://docs.anthropic.com)
- [LINE Messaging API ドキュメント](https://developers.line.biz/ja/docs/messaging-api/)
- [GitHub Codespaces ドキュメント](https://docs.github.com/ja/codespaces)

### サンプルコード
GitHub リポジトリへのリンク

---

<!-- _class: lead -->
<!-- _paginate: false -->

# Thank You!

質問やフィードバックをお待ちしています
