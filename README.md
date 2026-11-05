# ACT — Agent Crafting Table

ACT 的公開發布、使用說明與問題回報入口。執行核心為 ARC（Agent Runtime Core）。

## 目前發布狀態

已分別提供 **Revit 2023 與 Revit 2024 / Windows x64 編譯 Preview**，均非穩定版。請依 Revit 年度選擇，不能跨年替換 DLL，首次試用請用可丟棄測試模型。

### [下載 ACT 2023 Preview 0.1.0-preview.20261105](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261105)

下載 `ACT-Revit-2023-Compiled-Preview-20261105.zip` 與同名 `.sha256`，解壓縮後依序執行 `Verify-ACT-2023.cmd`、`Install-ACT-2023.cmd`。已對真正 2023 API 編譯（0 錯誤、0 警告），83 項離線回歸通過；**2023 主程式載入、內嵌圖台與模型操作尚未驗收**。保留 `scriptPreviewReady=false`，先做安裝／載入／唯讀驗收，不直接投入正式模型批量作業。一般安裝不需 SDK、Visual Studio 或另裝 Node，完整步驟見 Release 的 `README_INSTALL.zh-TW.txt`。

### [下載 ACT 2024 Preview 0.1.0-preview.20261104](https://github.com/NightFox-Inari/ACT-Releases/releases/tag/v0.1.0-preview.20261104)

下載 Release 中的 `ACT-Revit-2024-Compiled-Preview-20261104.zip` 及 `.sha256`，解壓縮後先執行 `Verify-ACT-2024.cmd`，再執行 `Install-ACT-2024.cmd`。**GitHub 的 Source code ZIP 不是安裝包。** 保存模型與圖台草稿，正常關閉所有 Revit 後安裝；不需 Visual Studio、.NET SDK 或另裝 Node。

內嵌圖台需要 Microsoft Edge WebView2 Evergreen Runtime；本包未附其安裝器。既有 ACT 服務佔用 8993 時會安全停止安裝，不會結束其他 Node 程序。完整步驟與還原方式見包內 `README_INSTALL.zh-TW.txt`。

- [人與 AI 共用說明書（草稿）](ACT_公開使用說明_草稿.zh-TW.md)
- [本版驗證範圍與限制](RELEASE_STATUS.zh-TW.md)

- [下載與版本紀錄](https://github.com/NightFox-Inari/ACT-Releases/releases)
- [問題回報](https://github.com/NightFox-Inari/ACT-Releases/issues/new/choose)
- [更新與資料保護原則](UPDATE_POLICY.zh-TW.md)
- [使用與支援](SUPPORT.md)
- [安全問題回報](SECURITY.md)

## 更新操作

公開版以手動下載、核對及安裝為主。2024 公開包維持原版；2023 Preview 帶版本查詢／官方發布頁入口，**自動下載、簽章驗證與自動安裝尚未啟用**。後續 2024 介面候選尚未公開。 本 Preview DLL 未做發行者數位簽章，SHA256 只證明完整性；收件人須核對官方發布來源並自行決定是否載入。關閉相關 Revit 後才替換 ARC DLL；圖台先保存草稿再重啟。更新不修改模型、不帶入 AI 權限、不重置個人經驗或設計方案。

## 回報前

公開 Issue 任何人都能讀取。請只附去識別的錯誤摘要、版本、Revit 年度及重現步驟；不要上傳 RVT／DWG、公司圖紙、完整路徑、使用者名稱、帳號 token、grant 或原始 IPC 紀錄。ACT 不會自動把模型或診斷送到此處。

此公開庫僅供發布及支援；私人開發來源另行管理。公開下載不等於開源授權，第三方授權隨各發布包附上。
