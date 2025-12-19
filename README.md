# MCP — Modular Cognitive Protocol

> **MCP is for engineers who maintain automation systems after the first success.**

MCP は、**不安定で変化の激しい Web 環境において、AI や自動化システムを安全に長期運用するための基盤設計**です。

動画サイト、SNS、外部 API、ブラウザ操作など、仕様変更・失敗・例外が日常的に発生する領域を前提に、  
MCP は **「動いたかどうか」よりも「壊れたあとに直せるか」** を重視します。

MCP は特定用途向けの便利ツールではありません。  
動画ダウンロード、スクレイピング、OSINT 収集、動画メタデータ解析、E2E テスト自動化、  
AI エージェント／VTuber 系システムなど、

**外部環境に強く依存する処理を、共通の設計ルールで長期運用するための実戦基盤**です。

---

## Why MCP

外部依存のシステムは、成功よりも失敗が支配します。

- サイト構造の変更、rate limit、CAPTCHA 追加  
- API の仕様変更、取得失敗、フォーマット追加  
- UI 変更、セレクタ破損、タイムアウト  
- 情報源の消失、認証方式の変更、統合先の不安定化  

MCP は、これらを「異常」ではなく「通常状態」とみなし、  
**壊れやすい現実世界を、長期運用できる構造へ押し戻す**ための設計基盤です。

---

## What MCP is

MCP は次の前提に基づいて設計されています。

- **外部仕様は必ず壊れる**
- **処理の境界と責任を明確に分離する**
- **契約（入力・出力・意味）を固定する**
- **失敗を分類し、回復可能な構造を作る**

**MCP は、契約（Contract）を固定し、失敗と変更を内部に閉じ込める設計基盤です。**
成功／失敗の揺らぎをアプリケーションの外へ漏らさず、**構造と契約によって運用可能性を守ること**を目的とします。

---

## What MCP is NOT

MCP は以下を目的としたものではありません。

- 不正アクセスや侵入行為  
- 認証回避・権限制御の破壊  
- DRM や暗号化の解除  
- 利用規約を意図的に回避する行為  
- 個人情報・秘匿情報の不正取得  

**技術的に可能なことを推奨・自動化する基盤ではありません。**  
何を取得するか、どう利用するか、法的・契約的に許されるかは **利用者側の責任**です。

---

## Use Cases

MCP が扱うのは、一般的に業務・研究で行われている技術領域です。

- 公開情報の取得・整理（OSINT）  
- Web ページや API からのデータ取得  
- 動画・メディアの解析やメタデータ生成  
- ブラウザ操作や E2E テスト自動化  
- AI エージェント／自動処理システムの基盤設計  

用途ではなく、**壊れた後も運用できる構造**に焦点を当てます。

---

## Public API

```python
from mcp import DownloadEngine, DownloadConfig, BrowserDriver
```

公開 API は **契約として安定させることを前提**としています。  
内部実装は、修復・改善・再設計を前提に変更されます。

> **These APIs define the _only_ stable surface.**  
> **Everything else is intentionally unstable.**

---

## Repository Policy

本リポジトリは、以下のみを意図的に公開しています。

- 設計方針  
- 公開 API の境界  
- 契約および運用ポリシー  

実装コード、テストスイート、運用モジュールは**契約関係に基づく場合にのみ開示**されます。

> This repository is not an open-source distribution.

---

## Status

⚠️ **Experimental / Design validation phase**

MCP は実環境での運用を通じて設計を検証しています。  
完成品ではなく、壊れやすい現実世界を前提に構造を継続的に改善する基盤です。

**MCP assumes breakage, maintenance, and long-term ownership.**

---

**Built for the real world, where things break.**
