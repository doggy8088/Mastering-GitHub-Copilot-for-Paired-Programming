<header>

# GitHub Codespaces 介紹

歡迎來到 GitHub Codespaces 的世界 — 您的雲端程式設計入口。在這個模組中，我們將探索即時、雲端託管的開發環境所帶來的變革力量，這些環境重新定義了您對程式設計的看法。GitHub Codespaces 提供無縫的整合體驗，配備了您有效程式設計所需的所有基本語言、工具和實用程式。

在這段學習旅程中，您將了解完整的 Codespaces 生命週期，並獲得自訂設置以符合您的特定偏好和需求的見解。為了加強您的理解，模組的最後將進行一個實作練習，讓您能夠在 GitHub Codespaces 環境中直接應用您的技能。

想像一下，一個完全配置的開發設置，隨時可用，並可從任何有網路連接的電腦訪問。GitHub Codespaces 使您能夠擁抱協作和靈活程式設計的新時代。讓我們一起深入探索，釋放雲端開發的全部潛力吧！

</header>

* **適合誰**：開發人員、DevOps 工程師、工程經理、產品經理。
* **您將學到什麼**：如何建立一個 codespace，從 codespace 推送程式碼，選擇自定義映像，並自定義 codespace。
* **您將建構什麼**：包含 devcontainer.json 文件的 codespace、自定義和個性化設置。
* **先決條件**：您需要了解以下內容：
  * 使用 Visual Studio Code，[Visual Studio Code 文檔](https://code.visualstudio.com/docs)。
  * 理解 GitHub 的使用或完成先前模組 [GitHub 介紹](https://github.com/WirelessLife/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/01-Introduction-to-GitHub/README.md?WT.mc_id=academic-113596-abartolo)。
* **時間**：這門課程可以在一小時內完成。

在本模組結束時，您將能夠：

1. 描述 GitHub Codespaces。
2. 解釋 GitHub Codespace 的生命週期以及如何執行每一步。
3. 定義您可以使用 GitHub Codespaces 個性化的不同自定義設置。

## 先決條件閱讀：

* [使用 GitHub Codespaces 程式設計](https://learn.microsoft.com/training/modules/code-with-github-codespaces/?WT.mc_id=academic-113596-abartolo)
* 什麼是 GitHub Codespaces？(下面的影片播放列表)
* [![什麼是 Codespaces](https://img.youtube.com/vi/ozuDPmcC1io/0.jpg)](https://www.youtube.com/watch?v=ozuDPmcC1io\&list=PLmsFUfdnGr3wTl-NCblzcrEv2lFSX975-)

### 如何開始這門課程

<!-- 要開始課程，請在 JavaScript 中運行：
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'code-with-codespaces',
  owner: '@me',
  name: 'skills-code-with-codespaces',
  description: '我的克隆庫',
  visibility: 'public',
}).toString()
-->

[![開始課程](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills\&template_name=code-with-codespaces\&owner=%40me\&name=skills-code-with-codespaces\&description=My+clone+repository\&visibility=public)

1. 右鍵單擊 **開始課程** 並在新標籤中打開連結。
2. 在新標籤中，大多數提示將自動為您填寫。
   * 對於擁有者，選擇您的個人帳戶或一個組織來託管儲存庫。
   * 我們建議建立一個公共儲存庫，因為私有儲存庫將 [使用 Actions 分鐘](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions?WT.mc_id=academic-113596-abartolo)。
   * 向下滾動並單擊表單底部的 **Create repository** 按鈕。
3. 在您的新庫建立後，等待大約 20 秒，然後刷新頁面。按照新庫的 README 中的逐步說明操作。

<footer>

<!--
  <<< 作者備註：頁腳 >>>
  添加獲取支持的連結、GitHub 狀態頁、行為準則、許可證連結。
-->

---

獲得幫助：[在我們的討論區上發文](https://github.com/orgs/skills/discussions/categories/introduction-to-github)  •  [查看 GitHub 狀態頁](https://www.githubstatus.com/)
