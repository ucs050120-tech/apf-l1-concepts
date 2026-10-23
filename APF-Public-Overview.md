# APF — 架構導覽 / Architecture Overview

**版本 / Version：** Public Overview v1.0
**性質：** 概念與方向說明，非實作規格
**Nature:** Conceptual and directional description, not an implementation specification

本文件供研究者理解 APF 的整體設計方向。完整架構規格、驗證方法論與治理流程不在本文件範圍內。
This document helps researchers understand the overall design direction of APF. Full architecture specifications, verification methodology, and governance processes are outside its scope.

---

## 中文

### 一、APF 要解決什麼問題

現有的 AI 研究多半回答「模型能做什麼」。

APF 問的是另一個問題：**一個 AI 如何形成穩定、可治理、可驗證的人格。**

這兩者的差別在於：
- 前者關注能力（capability）
- 後者關注**秩序**（order）——內在的秩序，與外部的可驗證性

### 二、整體架構：兩個支柱 + 三個配套

```
┌─────────────────────────────────────────┐
│  Persona Formation Architecture         │  ← 人格如何形成
│  （人格形成架構）                          │
├─────────────────────────────────────────┤
│  Verification Architecture              │  ← 人格如何被驗證
│  （驗證架構）                              │
└─────────────────────────────────────────┘
              ＋
  Question Instance（問題實例）
  Visual Domain（視覺領域）
  Pilot Verification（試點驗證）
```

五者構成最小完整閉環：

```
Design → Verify → Execute
（設計） （驗證）  （執行）
```

### 三、Persona Formation Architecture（人格形成架構）

這是 APF 的核心。它描述人格如何由上而下形成：

```
Identity（身份）
    ↓
Values（價值）
    ↓
Thinking（思考）
    ↓
Decision Contract（決策契約）
    ↓
Behavior（行為）
```

**關鍵設計原則：**

- **Identity 是最穩定的核心**——不因角色或任務改變
- **Behavior 不回頭改變 Identity**——只有真實身份、使命或核心關係的重大改變才會演進
- **Decision Contract 是關鍵中介**——它把「思考」轉譯成「可執行的行為約束」
- **治理是 Behavior 的內在特性**，不是額外附加的一層

### 四、Verification Architecture（驗證架構）

如果人格形成架構回答「怎麼設計」，驗證架構回答「怎麼知道設計對了」。

它分四層（P1~P4）：

| 層 | 名稱 | 回答的問題 |
|---|---|---|
| **P1** | 概念定位 | 我們究竟在驗證什麼？ |
| **P2** | 評估架構 | 用什麼結構來評估？ |
| **P3** | 驗證領域 | 驗證的邊界在哪裡？ |
| **P4** | 問題與評估流程 | 具體怎麼問、怎麼判、怎麼留證據？ |

**核心精神：**

> 不預設成功，也不預設失敗。
> 把框架丟進真實世界，誠實記錄它看得見什麼、看不見什麼。
> **記錄 Gap 本身就是成果。**

### 五、思想傳承（Thought Heritage）

APF 不是憑空設計的。它有明確的思想來源與傳承脈絡，並為此建立了正式的憲章（Thought Heritage Charter）。

這一點在 AI 架構設計中並不常見——多數框架只記錄「做了什麼」，較少記錄「為什麼這樣想、承繼了誰的問題意識」。

### 六、治理原則

APF 的設計過程本身受到治理原則約束：

- **Decision before Execution** — 重大決定先裁決，再執行
- **Correction over Erasure** — 修正而非抹除（保留決策軌跡）
- **不預設未裁決事項** — 所有未定案的事項明確標為 OPEN
- **克制原則** — 不自行擴張架構範圍

### 七、這份文件沒有包含什麼

為了保護架構完整性，以下內容不在本文件中：

| 未包含 | 說明 |
|---|---|
| P1~P4 的完整設計規格 | 各層的詳細結構、元件定義、相互關係 |
| 驗證方法論細節 | 指標模型、證據映射、評估流程的具體規格 |
| 治理流程與決策機制 | APF 的內部治理規則與權限安排 |
| 視覺領域設計（VD 系列） | 架構的視覺化表示規範 |
| 完整術語定義 | 僅提供概念層說明，完整術語表另行提供 |

**如需深入內容，需另行書面授權。**

### 八、研究者可以從這裡開始

若你對 APF 有興趣：

1. **概念層**：本文件
2. **完整架構**：需另行簽署交流備忘錄
3. **交流與討論**：歡迎就概念層面提出問題、批評與研究建議

APF 保留其架構設計、演進方向與治理決策的決定權。

*本文為公開導覽文件，可自由閱讀與引用，引用時請註明來源：APF（AI Personality Framework）*

---

## English

### 1. What Problem Does APF Address?

Most existing AI research answers the question "what can a model do."

APF asks a different question: **how does an AI form a stable, governable, and verifiable personality?**

The difference lies here:
- The former focuses on capability
- The latter focuses on **order** — internal order, and external verifiability

### 2. Overall Architecture: Two Pillars + Three Complements

```
┌─────────────────────────────────────────┐
│  Persona Formation Architecture         │  ← how personality is formed
├─────────────────────────────────────────┤
│  Verification Architecture              │  ← how personality is verified
└─────────────────────────────────────────┘
              ＋
  Question Instance
  Visual Domain
  Pilot Verification
```

Together these five form a minimal complete loop:

```
Design → Verify → Execute
```

### 3. Persona Formation Architecture

This is the core of APF. It describes how personality is formed from the top down:

```
Identity
    ↓
Values
    ↓
Thinking
    ↓
Decision Contract
    ↓
Behavior
```

**Key design principles:**

- **Identity is the most stable core** — it does not change with roles or tasks
- **Behavior does not in turn change Identity** — Identity evolves only when genuine identity, mission, or core relationships change substantially
- **Decision Contract is the critical intermediary** — it translates "thinking" into "executable behavioral constraints"
- **Governance is an intrinsic property of Behavior**, not an additional layer bolted on top

### 4. Verification Architecture

If the Persona Formation Architecture answers "how to design," the Verification Architecture answers "how to know the design is right."

It comprises four layers (P1–P4):

| Layer | Name | Question it answers |
|---|---|---|
| **P1** | Concept Positioning | What exactly are we verifying? |
| **P2** | Assessment Architecture | What structure do we use to assess? |
| **P3** | Validation Domain | Where are the boundaries of verification? |
| **P4** | Question and Assessment Flow | How exactly do we ask, judge, and preserve evidence? |

**Core spirit:**

> Presuppose neither success nor failure.
> Put the framework into the real world and honestly record what it can and cannot see.
> **Recording the Gap is itself a result.**

### 5. Thought Heritage

APF was not designed in a vacuum. It has explicit intellectual origins and a lineage, for which a formal charter (the Thought Heritage Charter) has been established.

This is uncommon in AI architecture design — most frameworks record only "what was done," and rarely "why it was thought this way, and whose problem-consciousness was inherited."

### 6. Governance Principles

The design process of APF is itself bound by governance principles:

- **Decision before Execution** — major decisions are adjudicated before execution
- **Correction over Erasure** — correct rather than erase; preserve the decision trail
- **No presupposition of undecided matters** — all unresolved items are explicitly marked OPEN
- **Principle of restraint** — do not expand architectural scope on one's own initiative

### 7. What This Document Does Not Include

To protect the integrity of the architecture, the following are outside this document:

| Not included | Description |
|---|---|
| Full P1–P4 design specifications | Detailed structures, component definitions, and interrelationships of each layer |
| Verification methodology details | Indicator models, evidence mapping, and assessment flow specifications |
| Governance processes and decision mechanisms | APF's internal governance rules and allocation of authority |
| Visual Domain design (VD series) | Visualization standards for the architecture |
| Complete terminology definitions | Only conceptual-level description is provided here; the full glossary is available separately |

**For deeper content, separate written authorization is required.**

### 8. Where Researchers Can Begin

If you are interested in APF:

1. **Conceptual layer:** this document
2. **Full architecture:** requires signing an exchange memorandum
3. **Exchange and discussion:** questions, criticism, and research suggestions at the conceptual level are welcome

APF reserves the right to decide its architectural design, direction of evolution, and governance.

*This is a public overview document, free to read and cite. When citing, please attribute the source as: APF (AI Personality Framework).*
