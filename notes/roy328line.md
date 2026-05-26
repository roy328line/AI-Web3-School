---
timezone: UTC+8
---

# 0xroyluo

**GitHub ID:** roy328line

**Telegram:** @roy328328

## Self-introduction

AI x Web3 School

## Notes

<!-- Content_START -->
# 2026-05-26
<!-- DAILY_CHECKIN_2026-05-26_START -->
今日學習：深讀 Agent Identity 模組

GitHub 筆記：https://github.com/roy328line/ai-web3-school-cohort-0/blob/main/daily/2026-05-26.md

## 核心整理

**Agent Identity** 不是給 Agent 起個名字，而是讓用戶、服務和其他 Agent 能驗證：它是誰、誰控制它、能提供什麼能力、服務入口在哪裡。核心是把 Agent 從臨時會話變成可發現、可驗證、可追責的經濟參與者。

**第一性原理**：Agent 身份必須綁定控制權、能力聲明和服務入口，而不只是一個顯示名稱。三個基本要求：身份要可解析、控制權要可證明、能力要可驗證。

**Agent Profile**：包含名稱、描述、服務範圍、錢包地址、能力列表、owner 等，同時服務人和機器。更新歷史很重要，更新記錄本身就是信任信號。

**Capability**：越具體越有用，需寫明輸入類型、輸出格式、是否需要錢包權限、最長執行時間、失敗退款方式，並按風險分級（只讀/生成草稿/自動執行）。

**Service Endpoint**：安全性直接影響身份可信度，Endpoint 更新應需要 owner 簽名並保留歷史記錄。

**Registry**：用來登記、發現和更新 Agent 身份，能證明「這個身份是誰注册的」，但不能證明「這個 Agent 一定好用或安全」。

**DID / VC**：DID 表達跨平台可解析身份，VC 表達由 issuer 簽發的可驗證聲明（如能力測試通過、組織隸屬）。VC 的可信度取決於 issuer。

**A2A**：Agent 間通信協議，是通信層而非身份層。支付場景中需與 Payment Intent、Receipt、Escrow 狀態關聯。

**Ownership**：決定誰能更新 Profile、收款地址、Endpoint。高價值 Agent 不應由單個熱錢包控制，建議 operator/owner 分離。

## 核心發想

Agent Identity 把身份從「名字」提升到「可驗證的能力邊界和控制權結構」——不需要信任一個 Agent「是好的」，只需要能驗證它能做什麼、誰負責、失敗怎麼辦。DID/VC 讓 Agent 能累積跨平台可攜帶的「學歷和履歷」，是 Agentic Economy 的基礎設施。

<!-- DAILY_CHECKIN_2026-05-26_END -->
# 2026-05-18
<!-- DAILY_CHECKIN_2026-05-18_START -->
今日學習：深讀 AI x Web3 School Handbook 模組 A（LLM / Prompt / Context / Agent）+ 模組 B（Wallet / Smart Contract / Account Abstraction）

GitHub 筆記：[https://github.com/roy328line/ai-web3-school-cohort-0/blob/main/daily/2026-05-18.md](https://github.com/roy328line/ai-web3-school-cohort-0/blob/main/daily/2026-05-18.md)

\## 模組 A｜AI 基礎

\*\*LLM\*\*：概率生成模型，生成的是「概率上合理的輸出」，不是天然可信的事實。Hallucination 在 Web3 執行系統裡會從「答錯」變「做錯」，因此 Simulation 和 Human-in-the-loop 是系統基礎而非選配安全功能。

\*\*Prompt\*\*：Prompt 是軟約束，不是安全邊界。好 Prompt 四段式：任務目標 → 可用輸入 → 禁止行為 → 輸出格式。真正安全需要代碼層 allowlist + 工具調用前參數校驗 + 高風險動作強制走 human approval。Prompt Injection 是 Agent 場景的核心攻擊面。

\*\*Context\*\*：Context 五層結構：指令層 → 任務層 → 事實層 → 知識層 → 記憶層。不可信外部內容必須與系統指令層隔離，Memory 不能替代實時授權。

\*\*Agent\*\*：Agent 是被約束的執行循環，不是自主體。最危險設計是「模糊目標 + 廣泛工具 + 大額資產權限」三者並存。AI x Web3 Agent 八步架構：用戶目標 → 生成計劃 → 只讀工具執行 → 寫入工具 policy 檢查 → Simulation → 用戶確認 → Wallet 執行 → 日誌記錄。

\## 模組 B｜Web3 基礎

\*\*Wallet\*\*：連接/簽名/交易三類動作風險截然不同，UI 設計必須反映這個差異。助記詞是高危資訊，任何系統要求輸入助記詞都應默認視為危險。

\*\*Smart Contract\*\*：ABI 是機器可讀接口，不是安全說明書——告訴你能調用什麼，不保證調用是否安全。一次完整鏈上調用是 9 步流程（前端 → ABI 編碼 → 錢包確認 → RPC 廣播 → 驗證者打包 → EVM 執行 → Event → 前端回執 → 索引器更新）。

\*\*Account Abstraction\*\*：ERC-4337 讓帳戶可編程。Session Key 是 AI Agent 安全上鏈的關鍵基礎——比喻：不是「給 AI 一把主鑰匙」，而是「給 AI 一張限時限額的員工門禁卡」（最小權限原則）。

\## 核心發想

AI 不確定性（幻覺/注入/推理漂移）× Web3 不可逆性（交易上鏈不能撤回）= 核心設計張力：需要用不可靠的推理引擎驅動不可逆的執行系統。

解法：Simulation + Structured Output + Session Key + Human-in-the-loop + Audit Log

\## 明日計劃

跟進 5/19 直播：AI Agent 入門 — Hermes 從 0 到 1，並開始測試網錢包實作
<!-- DAILY_CHECKIN_2026-05-18_END -->
<!-- Content_END -->
