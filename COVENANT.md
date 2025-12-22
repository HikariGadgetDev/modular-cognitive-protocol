# MCP — Architectural Covenant (Soft Version)
# MCP — 設計誓約（ソフト版）

This document describes the **design principles and operational assumptions** of MCP  
in a concise and non-exhaustive form.

本ドキュメントは、MCP における **設計原則および運用上の前提条件**を、  
簡潔かつ網羅しすぎない形で記述したものです。

It exists to clarify intent, prevent misunderstandings, and support safe collaboration.  
This document is **descriptive**, not doctrinal.

本書は、設計意図を明確にし、誤解を防ぎ、安全な協業を支援するために存在します。  
これは思想の押し付けや規範の宣言ではありません。

This document can be read as the farewell note of one infrastructure engineer
who has seen too many systems break.

---

## Purpose
## 目的

MCP is designed to support **long-term operation of AI and automation systems**  
in environments where external specifications are unstable or outside the developer’s control.

MCP は、外部仕様が不安定、あるいは開発者の制御外にある環境において、  
**AI および自動化システムを長期運用すること**を目的として設計されています。

Typical examples include:  
代表的な対象例は以下のとおりです。

- Web platforms with frequent specification changes  
  頻繁に仕様変更が発生する Web プラットフォーム
- External APIs and browser-driven environments  
  外部 API やブラウザ操作を伴う環境
- Automated testing and data-collection systems  
  自動テストやデータ収集システム

---

## Core Principles
## 基本原則

### 1. Explicit Boundaries
### 1. 明示的な境界

- Responsibilities are clearly separated by module and layer  
  責務はモジュールおよびレイヤ単位で明確に分離されます
- Cross-layer access is avoided  
  レイヤを跨いだ直接アクセスは避けられます
- Public APIs represent **intentional boundaries**, not convenience  
  公開 API は利便性ではなく、**意図された境界**を表します

### 2. Contract-First Design
### 2. 契約優先設計

- Interfaces and data structures are treated as contracts  
  インターフェースやデータ構造は契約として扱われます
- Once published, contracts are intentionally kept stable  
  一度公開された契約は、意図的に安定性が保たれます
- Changes to contracts are managed explicitly and infrequently  
  契約の変更は明示的かつ限定的に管理されます

### 3. Failure as an Assumption
### 3. 失敗を前提とする設計

- Failures are expected and classified  
  失敗は想定され、分類されます
- Recovery paths are designed in advance  
  回復経路は事前に設計されます
- Silent or implicit failures are avoided  
  暗黙的・無言の失敗は避けられます

### 4. Adapter-Based Integration
### 4. Adapter による統合

- External systems are integrated via adapters  
  外部システムは Adapter を介して統合されます
- Domain logic is protected from external inconsistencies  
  ドメインロジックは外部の不整合から保護されます
- Adapters may change freely without breaking contracts  
  Adapter は契約を壊すことなく自由に変更可能です

### 5. Test-Guided Safety
### 5. テストによる安全性の担保

- Tests are used to verify contractual assumptions  
  テストは契約上の前提を検証するために使用されます
- Critical guarantees are enforced before changes progress  
  重要な保証は変更の進行前に検証されます
- Tests support structure validation, not blind confidence  
  テストは安心感ではなく、構造検証のためのものです

---

## What This Covenant Is Not
## 本誓約が対象としないもの

- A full specification of internal implementation  
  内部実装の完全な仕様書ではありません
- A restriction on technology choices  
  技術選択を制限するものではありません
- A guarantee of feature completeness  
  機能の完全性を保証するものではありません
- A replacement for legal or contractual agreements  
  法的・契約的合意の代替ではありません

---

## Scope of Disclosure
## 公開範囲について

This repository intentionally exposes:  
本リポジトリでは、以下のみを意図的に公開しています。

- Public API boundaries  
  公開 API の境界
- High-level design intent  
  高レベルの設計意図
- Safety and operational assumptions  
  安全性および運用上の前提

Internal implementation details and operational modules  
are shared only under appropriate agreements.

内部実装や運用モジュールは、  
適切な契約関係のもとでのみ共有されます。

---

## Appendix: Design Responsibility (Non-Normative)
## 付録：設計責任について（非規範）

設計とは、  
その判断が失敗したときに  
**自分が呼び戻される前提で行うもの**です。

将来の保守負債を発生させる設計判断を行いながら、  
その負債を引き受けない立場で設計を行うことは、  
本プロジェクトの設計思想とは相容れません。

本節は義務や規則を定めるものではなく、  
設計判断における責任の所在を明確にするための  
**価値観および姿勢の共有**を目的としています。

---

## Closing Note
## 補足

This covenant exists to support **predictable collaboration**,  
not to impose ideology.

本誓約は、**予測可能な協業**を支援するためのものであり、  
特定の思想や方法論を強制するものではありません。

Design decisions are evaluated by their ability to:  
設計判断は、以下の観点で評価されます。

- Survive change  
  変化に耐えられるか
- Recover from failure  
  失敗から回復できるか
- Remain understandable over time  
  時間が経っても理解可能であるか
