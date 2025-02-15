# 開始使用 GitHub Copilot for Azure

解除更高效的工作流程，提升您在 Azure Preview 上的生產力。這份快速入門指南將帶您了解所有必要資訊，從準備前置條件到在 Visual Studio Code 中安裝 GitHub Copilot for Azure 擴充功能。最後，您將能夠編寫您的第一個提示，充分運用 Azure 平台的潛力。

![GitHub Copilot for Azure](../../../09-Using-GitHub-Copilot-for-Azure-to-Deploy-to-Cloud/images/intro.gif "GitHub Copilot for Azure")

</header>

* **適用對象**：開發人員、資訊技術專業人員和 AI 工程師
* **學習目標**：設定 GitHub Copilot for Azure 的起始步驟
* **實作內容**：設定您的 AI 輔助工作環境

## 前置閱讀：

* [什麼是 GitHub Copilot for Azure Preview？](https://learn.microsoft.com/azure/developer/github-copilot-azure/introduction)

## 👉 前置條件

要完成此實作練習，請確保您具備：

1. Azure 帳戶和訂閱權限。詳細設定方式請參考 [Azure 帳戶的定價頁面](https://azure.microsoft.com/pricing/purchase-options/azure-account)

2. GitHub 帳戶。設定帳戶的步驟可以在此處找到：[在 GitHub 上建立帳戶](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)

3. GitHub Copilot 訂閱。啟用 GitHub Copilot 的詳細資訊可以在此處找到：[GitHub Copilot 快速入門](https://docs.github.com/en/copilot/quickstart)

4. Visual Studio Code。下載和安裝的詳細資訊請參考 [設定 Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)

5. GitHub Copilot 擴充功能和 GitHub Copilot Chat 擴充功能。安裝此擴充功能的說明請參考 [在 VS Code 中設定 GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)

## 💪🏽 練習

### 🛠 步驟 1：對 GitHub 進行身份驗證並登入 GitHub Copilot 聊天，以啟用 Azure Preview 的 Copilot

**在新分頁中開啟您的 Codespace，請按右鍵點擊下方的 Codespaces 按鈕**

[![在 GitHub Codespaces 中開啟](https://github.com/codespaces/badge.svg)](https://codespaces.new/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming)

1. 開啟 VS Code 後，在右側點擊 **「使用 GitHub.com 帳戶登入」**。

   1. Visual Studio Code 將顯示訊息：**「擴充功能 'GitHub Copilot Chat' 想要使用 GitHub 登入」**。點擊 **允許**。

   2. 您需要授權 Visual Studio Code 以繼續使用者登入。點擊 **繼續** 按鈕。

   3. 點擊 **授權 Visual-Studio-Code** 按鈕完成授權。

   4. 系統將詢問是否開啟 VS Code。點擊 **開啟**。您將返回 VS Code，並通過 GitHub 驗證取得 **GitHub Copilot** 存取權限。

2. 在 Visual Studio Code 中，選擇 **擴充功能** 圖示。

3. 確認您已安裝以下擴充功能：
   1. **Azure Tools**
   2. **GitHub Copilot**
   3. **GitHub Copilot Chat**
   4. **GitHub Copilot for Azure**
   5. **.NET Install**
   6. **Python**

4. 如果缺少任何一個，請從市集安裝。

### ✍️ 步驟 2：編寫您的第一個提示

1. 現在擴充功能已安裝，您已正確驗證，且擴充功能正常運作。

2. 在活動列上，如果 **Ask Copilot** 面板已關閉，請選擇 **聊天** 圖示。

3. 在聊天面板底部的文字區域中，輸入以下提示：

```prompt
@azure 我目前是否有任何資源正在執行？
```

> 在接下來的部分中，您將被要求多次授權應用程式和服務。這是為了保護您的安全，且只需執行一次。我們正在授權 **GitHub**、**VS Code** 和 **Azure** 信任所提供的憑證。

1. 您可能會在 GitHub Copilot Chat 面板中收到訊息：「您需要登入您的 Microsoft 帳戶以使用 GitHub Copilot for Azure (@Azure)」。

   1. 若收到此訊息，請點擊 **「已有帳戶？登入」** 中的連結。
   2. Visual Studio Code 將顯示訊息：**「擴充功能 'GitHub Copilot for Azure' 想要使用 Microsoft 登入」**。點擊 **允許**。
   3. 使用現有工作階段的憑證登入，或使用實作說明中的資源分頁提供的憑證。與 Azure 訂閱相同的憑證。
   4. 關閉分頁。請勿關閉瀏覽器。
   5. 返回 VS Code。Visual Studio Code 將顯示訊息：**「擴充功能 'GitHub Copilot for Azure' 想要存取 GitHub Copilot Chat 提供的語言模型」**。點擊 **允許**。
   6. Visual Studio Code 將顯示另一則訊息：**「擴充功能 'GitHub Copilot for Azure' 想要使用 GitHub 登入」**。再次點擊 **允許**。
      1. 您需要授權 Visual Studio Code 以繼續使用者登入。點擊 **繼續** 按鈕。
      2. 點擊 **授權 Visual-Studio-Code** 按鈕完成授權。
      3. 系統將詢問是否開啟 VS Code。點擊 **開啟**。您將返回 VS Code，並通過 GitHub 驗證取得 **GitHub Copilot** 存取權限。

2. Copilot for Azure 擴充功能將查詢 Azure 資源圖，為您提供資源查詢並回應。此時應該顯示 **您目前在所有訂閱中沒有任何執行中的資源。**

### 結論

恭喜您，透過這個練習，您已經設定 VS Code 以使用 GitHub Copilot for Azure，並成功查詢 Azure 訂閱中執行的資源狀態。
