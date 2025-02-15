<header>

# GitHub Copilot 介紹

在這個學習模組中，我們將探討使用 GitHub Copilot 的好處，這是首個專為大規模運行而設計的 AI 開發工具。Copilot 通過協助執行測試、重構、解釋和建議代碼等任務來增強您的編碼體驗。

GitHub Copilot 是一個由 AI 驅動的編碼助手，幫助您更快且更輕鬆地編寫代碼，從而釋放出更多的時間和精力來解決問題和進行協作。

在模組結束時，您將不僅能夠清楚表達 GitHub Copilot 是什麼及其優勢，還能理解它對個人和企業的可用性。深入了解 GitHub Copilot 的未來，並通過實踐練習掌握如何在 Visual Studio Code 中使用它。

通過利用 Copilot，開發人員已能夠提高生產力並加速軟件開發。如需更多見解，請查看 GitHub 博客文章《研究：量化 GitHub Copilot 對開發者生產力和幸福感的影響》。([Quantifying GitHub Copilot’s Impact on Developer Productivity and Happiness.](https://github.blog/2022-09-07-research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness))

注意：雖然本模組使用 [Codespaces](https://github.com/codespaces)，但您也可以在各種其他環境中使用 GitHub Copilot，包括在本地使用 Visual Studio Code。

</header>

- **適合對象**：開發人員、DevOps 工程師、軟件開發經理、測試人員。
- **您將學到的內容**：如何將 Copilot 安裝到 Codespace 中，接受代碼建議，接受註解建議。
- **您將構建的內容**：將由 Copilot AI 生成代碼和註解建議的 Javascript 文件。
- **先決條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
- **時間安排**：本課程可在一小時內完成。

在本模組結束時，您將能夠：

- 解釋 GitHub Copilot 是什麼以及它提供的優勢。
- 理解 GitHub Copilot 對個人和企業的可用性。
- 討論 GitHub Copilot 的未來。
- 學習如何開始使用 GitHub Copilot 及一些常見配置。
- 使用實踐練習在 Visual Studio Code 中開發 GitHub Copilot。

## 先決閱讀：
- [GitHub Copilot 介紹](https://learn.microsoft.com/en-us/training/modules/introduction-to-github-copilot/?WT.mc_id=academic-113596-abartolo)
- GitHub Copilot 是什麼？（以下視頻播放列表）
- [![GitHub Copilot 是什麼](https://img.youtube.com/vi/QG1E0SCqqW8/0.jpg)](https://learn.microsoft.com/shows/introduction-to-github-copilot/what-is-github-copilot-1-of-6/?WT.mc_id=academic-113596-abartolo)

### 如何開始這門課程

<!-- 要開始課程，請在 JavaScript 中運行：
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'copilot-codespaces-vscode',
  owner: '@me',
  name: 'skills-copilot-codespaces-vscode',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=copilot-codespaces-vscode&owner=%40me&name=skills-copilot-codespaces-vscode&description=My+clone+repository&visibility=public)

1. 右鍵單擊 **開始課程** 並在新標籤頁中打開鏈接。
2. 在新標籤頁中，大多數提示將自動為您填寫。
   - 對於擁有者，選擇您的個人帳戶或組織來託管該存儲庫。
   - 我們建議創建一個公共存儲庫，因為私有存儲庫將 [使用 Actions 分鐘](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions)。
   - 向下滾動並單擊表單底部的 **創建存儲庫** 按鈕。
3. 新存儲庫創建後，等待約 20 秒，然後刷新頁面。按照新存儲庫的 README 中的逐步指示操作。

<footer>

<!--
  <<< 作者備註：頁腳 >>>
  添加獲取支持的鏈接，GitHub 狀態頁面，行為準則，許可證鏈接。
-->

---

獲取幫助：[在我們的討論區發帖](https://github.com/orgs/skills/discussions/categories/code-with-copilot) • [查看 GitHub 狀態頁面](https://www.githubstatus.com/)

**免責聲明**：
本文件是使用機器翻譯的人工智慧翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人類翻譯。我們對因使用此翻譯而產生的任何誤解或誤釋不承擔責任。