# ACT — Agent Crafting Table

ACT 的公開發布、使用說明與問題回報入口。執行核心為 ARC（Agent Runtime Core）。

## 目前發布狀態

已分別提供 **Revit 2023 與 Revit 2024 / Windows x64 編譯 Preview**，均非穩定版。請依 Revit 年度選擇，不能跨年替換 DLL，首次試用請用可丟棄測試模型。

### [下載 ACT 2023 簽章更新 Preview 0.1.0-preview.20261106.1](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261106.1)

下載 **ACT-Revit-2023-Compiled-Preview-20261106-Updater.zip** 與同名 **.sha256**。保存模型及 ACT 草稿，正常關閉全部 Revit，完整解壓後先執行 **Verify-ACT-2023.cmd**，再執行 **Install-ACT-2023.cmd**。GitHub 的 Source code ZIP 不是安裝包。

本版保留原 2023 面板，只補齊簽章檢查、下載核對、人類保存確認、關閉等待、備份／安裝與受控重試。**舊 2023 只有版本提示，第一次須手動安裝本包，之後才有真正的更新能力。** 已對真正 API 23 編譯（0 錯誤、0 警告），年度互拒、精確助手、公鑰、公開包及隔離套件流程核對通過；**2023 載入、內嵌圖台、真按鈕更新與模型作業仍待實機驗收**。hostValidated=false、scriptPreviewReady=false 保留，不直接用於正式模型批量作業。一般安裝不需開發環境或另裝 Node；詳包內 README_INSTALL.zh-TW.txt。舊 [2023 Preview 11/05](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261105) 保持原樣。

### [下載 ACT 2024 更新恢復 Preview 0.1.0-preview.20261105.3](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261105.3)

下載 Release 中的 `ACT-Revit-2024-Compiled-Preview-20261105-M1.zip` 及 `.sha256`，解壓縮後先執行 `Verify-ACT-2024.cmd`，再執行 `Install-ACT-2024.cmd`。**GitHub 的 Source code ZIP 不是安裝包。** 保存模型與圖台草稿，正常關閉所有 Revit 後安裝；不需 Visual Studio、.NET SDK 或另裝 Node。

內嵌圖台需要 Microsoft Edge WebView2 Evergreen Runtime；本包未附其安裝器。既有 ACT 服務佔用 8993 時會安全停止安裝，不會結束其他 Node 程序。完整步驟與還原方式見包內 `README_INSTALL.zh-TW.txt`。

- [人與 AI 共用說明書（草稿）](ACT_公開使用說明_草稿.zh-TW.md)
- [本版驗證範圍與限制](RELEASE_STATUS.zh-TW.md)

- [下載與版本紀錄](https://github.com/NightFox-Inari/ACT-Releases/releases)
- [問題回報](https://github.com/NightFox-Inari/ACT-Releases/issues/new/choose)
- [更新與資料保護原則](UPDATE_POLICY.zh-TW.md)
- [使用與支援](SUPPORT.md)
- [安全問題回報](SECURITY.md)

## 更新操作

2023 與 2024 均提供 RSA-3072 / SHA256 簽章更新 Preview：固定官方頻道核對版本、年度、有效期限與序號，再下載、驗證完整包。由人確認已保存模型及圖台，正常關閉所有 Revit 後才由獨立助手備份、安裝；不強制關閉 Revit，也不是無人值守更新。

**舊版只查版本的入口需要先人工安裝一次新版。** 首次安裝用各年度 Release 完整 ZIP。2023 新入口為 11/06 版本，舊 11/05 的 metadata-only 包保持原樣。舊 [2024 Preview 11/04](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261104) 也保留原樣。

`.3` 新增更新失配診斷、同一精確助手的新程序重試、可信完成／回復判讀，以及長摘要捲動框與較小選單。維護端已完成一筆 **原 B `.2` 按鈕查詢／下載 → 人類保存確認 → 原助手安裝 `.3` → 重開版本與載入能力核對**，程式與舊版備份校驗一致，實際 Revit 使用的指定圖台／經驗資料域也與本次備份一致。這是單機 Revit 2024 的一次正向驗收，不能外推全部使用者資料位置。

**完整 M1 尚未結案**：新版助手的故障重試、未存／忙碌／雙實例阻擋、完整恢復與乾淨電腦仍待驗。曾出現原生缺少參考對話框縮得過小，後續重開成功，原因未明，未宣稱已修復。2023 不繼承此更新驗收，亦非穩定版。

固定 [Preview 簽章頻道](updates/preview-rsa-v1.json) 序號 3 同時保留 2024 `.3` 與新增 2023 `.20261106.1`，先依年度選擇資產；過期、離線、校驗不符或未知本機版本會阻擋下載安裝。Stable 簽章頻道尚未發布。套件專用簽章與 Windows Authenticode／Revit 發行者簽章不同，收件人仍須核對官方來源及人類安全提示。更新不修改模型、不帶入 AI 權限、不重置個人經驗或設計方案。

## 回報前

公開 Issue 任何人都能讀取。請只附去識別的錯誤摘要、版本、Revit 年度及重現步驟；不要上傳 RVT／DWG、公司圖紙、完整路徑、使用者名稱、帳號 token、grant 或原始 IPC 紀錄。ACT 不會自動把模型或診斷送到此處。

此公開庫僅供發布及支援；私人開發來源另行管理。公開下載不等於開源授權，第三方授權隨各發布包附上。
