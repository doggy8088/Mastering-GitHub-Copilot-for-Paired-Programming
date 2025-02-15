# 開始使用 GitHub Copilot for Azure

解鎖更高效的工作流程，提升您在 Azure Preview 上的生產力。這份快速入門指南將帶您了解所有必要知識，從準備前置條件到在 Visual Studio Code 中安裝 GitHub Copilot for Azure 擴展。到最後，您將能夠編寫您的第一個提示，充分利用 Azure 平台的潛力。

![GitHub Copilot for Azure](../../../09-Using-GitHub-Copilot-for-Azure-to-Deploy-to-Cloud/images/intro.gif "GitHub Copilot for Azure")
 
</header>

- **這個指南適合誰**：開發人員、運維人員（ITPRO）和 AI 工程師。
- **您將學到什麼**：開始使用 GitHub Copilot for Azure 的設置步驟。
- **您將構建什麼**：您將自信地設置您的 AI 啟用工作區。
 
## 前置閱讀：
- [什麼是 GitHub Copilot for Azure Preview？](https://learn.microsoft.com/azure/developer/github-copilot-azure/introduction)
 
## 👉 前置條件

要完成此實驗室中的步驟，請確保您具備：

1. 一個 Azure 帳戶和對 Azure 訂閱的訪問權限。詳細設置方法請參見 [Azure 帳戶的定價頁面。](https://azure.microsoft.com/pricing/purchase-options/azure-account)

1. 一個 GitHub 帳戶。設置帳戶的步驟可以在這裡找到：[在 GitHub 上創建帳戶](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
  
1. GitHub Copilot 訂閱。啟用 GitHub Copilot 的詳細信息可以在這裡找到：[GitHub Copilot 快速入門](https://docs.github.com/en/copilot/quickstart)

1. Visual Studio Code。下載和安裝的詳細信息請參見 [設置 Visual Studio Code。](https://code.visualstudio.com/docs/setup/setup-overview)

1. GitHub Copilot 擴展和 GitHub Copilot Chat 擴展。安裝此擴展的說明請參見 [在 VS Code 中設置 GitHub Copilot。](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
 
## 💪🏽 練習
 
### 🛠 步驟 1：對 GitHub 進行身份驗證並登錄 GitHub Copilot 聊天，以啟用 Azure Preview 的 Copilot

**右鍵單擊以下 Codespaces 按鈕以在新標籤中打開您的 Codespace**

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming)

1. 打開 VS Code 後，在右側，點擊 **"使用 GitHub.com 帳戶登錄"**。

    1. Visual Studio Code 將彈出一條消息，詢問 **"擴展 'GitHub Copilot Chat' 想要使用 GitHub 登錄。"** 點擊 **允許**。

    1. 您需要授權 Visual Studio Code 以繼續用戶登錄。點擊 **繼續** 按鈕。

    1. 通過點擊 **授權 Visual-Studio-Code** 按鈕來完成授權。

    1. 將彈出一條消息詢問是否打開 VS Code。點擊 **打開**。您將返回到 VS Code，並且將通過 GitHub 驗證，並將訪問 **GitHub Copilot**。

1. 在 Visual Studio Code 中，選擇 **擴展** 圖標。

1. 驗證您是否已安裝以下擴展。
    1. **Azure Tools**
    1. **GitHub Copilot**
    1. **GitHub Copilot Chat**
    1. **GitHub Copilot for Azure**
    1. **.NET Install**
    1. **Python**
   
1. 如果缺少任何一個，請從市場安裝它。

### ✍️ 步驟 2：編寫您的第一個提示

1. 現在擴展已安裝，您已正確驗證，並且擴展正常運行。

1. 在活動欄上，如果 **Ask Copilot** 面板關閉，請選擇 **聊天** 圖標。

1. 在聊天面板底部的文本區域中，輸入以下提示：

```prompt
@azure Do I have any resources currently running?
```
> 在下一部分中，您將被要求多次授權應用程序和服務。這是為了保護您，並且只會進行一次。我們正在授權 **GitHub**、**VS Code** 和 **Azure** 信任提供的憑據的提示。

1. 您可能會在 GitHub Copilot Chat 面板中收到一條消息，指出 "您需要登錄您的 Microsoft 帳戶以使用 GitHub Copilot for Azure (@Azure)"。

    1. 如果您收到，請點擊 **"已經有帳戶？登錄"** 行中的鏈接。
    1. Visual Studio Code 將彈出一條消息，詢問 **"擴展 'GitHub Copilot for Azure' 想要使用 Microsoft 登錄。"** 點擊 **允許**。
    1. 使用現有會話中的憑據登錄，或使用實驗室說明的資源標籤中找到的憑據。與 Azure 訂閱相同的憑據。
    1. 關閉標籤頁。不要關閉瀏覽器。
    1. 返回到 VS Code。Visual Studio Code 將彈出一條消息，詢問 **"擴展 'GitHub Copilot for Azure' 想要訪問 GitHub Copilot Chat 提供的語言模型。"** 點擊 **允許**。
    1. Visual Studio Code 將彈出另一條消息，詢問 **"擴展 'GitHub Copilot for Azure' 想要使用 GitHub 登錄。"** 再次點擊 **允許**。
        1. 您需要授權 Visual Studio Code 以繼續用戶登錄。點擊 **繼續** 按鈕。
        1. 通過點擊 **授權 Visual-Studio-Code** 按鈕來完成授權。
        1. 將彈出一條消息詢問是否打開 VS Code。點擊 **打開**。您將返回到 VS Code，並且將通過 GitHub 驗證，並將訪問 **GitHub Copilot**。

1. Copilot for Azure 擴展將查詢 Azure 資源圖，為您提供資源查詢並提供答案。此時應該顯示 **您當前在所有訂閱中沒有任何正在運行的資源。**

### 結論

恭喜您，通過這個練習，您已經設置了 VS Code 以使用 GitHub Copilot for Azure，並詢問它告知您在 Azure 訂閱中運行的任何資源。

**免責聲明**：
本文件是使用基於機器的人工智能翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人類翻譯。我們對因使用本翻譯而產生的任何誤解或誤譯不承擔責任。