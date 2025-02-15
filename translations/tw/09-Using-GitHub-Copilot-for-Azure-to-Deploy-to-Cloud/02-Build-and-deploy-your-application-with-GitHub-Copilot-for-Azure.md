# 使用 GitHub Copilot for Azure 建構和部署應用程式

本模組是模組 1 的延續，提供了使用 GitHub Copilot for Azure Preview 建立和部署新網站到 Azure 的逐步指南。

它強調了一種將 GitHub Copilot for Azure 無縫整合到您的開發和部署工作流程中的方法。

## 先決條件

完成 [模組 1 - 開始使用 GitHub Copilot for Azure](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/09-Using-GitHub-Copilot-for-Azure-to-Deploy-to-Cloud/01-Getting-Started-with-GitHub-Copilot-for-Azure.md)

## 使用 GitHub Copilot for Azure Preview 建立和部署網站

1. 在本機電腦上建立一個新資料夾，以便您可以建立 GitHub 儲存庫的本機複製。
    1. 在 VS Code 中點擊 **檔案**，然後選擇 **開啟資料夾**
    1. 在 **開啟資料夾** 對話框中，點擊 **新增資料夾**，為資料夾命名，選擇它，然後點擊 **選擇資料夾**

1. VS Code 會詢問您 **是否信任此資料夾中的檔案作者？**
    1. 點擊 **是的，我信任作者**

1. 在 Visual Studio Code 中，選擇 **檢視** > **終端機**。在終端機面板中，切換到新資料夾。

1. 在狀態欄中，選擇 **Chat** (GitHub) 圖標以打開聊天面板。

1. 通過選擇面板標題欄上的加號圖標 (**+**) 開始新的聊天會話。

   ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat.png "開始新的聊天會話")

> 如果您在上個模組後關閉了 GitHub Copilot 聊天，請點擊狀態欄中的 GitHub 圖標。在您的 VS Code 屏幕的右下角，並在選項菜單中選擇 **"GitHub Copilot Chat"**。
>
> ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-2.png "開始新的聊天會話")

6. 在聊天文字方塊中，輸入以下提示。然後選擇 **傳送**（紙飛機圖示）或在鍵盤上按 Enter。

   ```prompt
   @azure 您能協助我使用 Python 建立並部署一個簡單的 Flask 網站嗎？
   ```

    > **重要**
    > 每次 GitHub Copilot for Azure 回應時，回應的確切措辭都會不同，這是由於大型語言模型生成回應的方式。

   過了一會兒，GitHub Copilot for Azure 可能會建議使用 `azd` 範本。在某些情況下會提供類似以下的答覆：

    ![Screenshot that shows the GitHub Copilot chat pane](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-3.png "Screenshot that shows a response from GitHub Copilot for Azure with instructions for using a template to create a website in Azure.")

    Just Remember that the Large Language Model will understand what you tell it.  Therefore, just have the conversation with it.

1. If the answer provides a command that begins with `azd init` in a code fence, hover over the code fence to reveal a small pop-up action menu.

    ![Screenshot that shows the GitHub Copilot chat pane](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-4.png "Screenshot that shows a pop-up menu with an option to insert a code-fenced command into the Visual Studio Code terminal.")

    Select **Insert into Terminal** to insert the command into the terminal.

    ![Screenshot that shows the GitHub Copilot chat pane](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-5.png "Screenshot that shows the Visual Studio Code terminal after insertion of a code-fenced command.")

1. Before you run the `azd init` 命令，您可能會對它如何影響您的本地計算機和 Azure 訂閱有疑問。

   使用以下提示：

   ```prompt
   @azure Before I execute azd init, what does it do?
   ```

   您可能會看到類似以下截圖的回應。

   ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-6.png "顯示 GitHub Copilot for Azure 的回應，解釋初始化命令的作用。")

1. 使用以下提示來了解更多有關 `azd` 模板的資訊：

   ```prompt
   @azure What resources are created with this template?
   ```

   您可能會看到類似以下截圖的回應。

    ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-7.png "顯示 GitHub Copilot for Azure 的回應，解釋建議模板所建立的資源。")

1. 針對模板使用的服務詢問問題，提示如下：

   ```prompt
   @azure What is the purpose of a virtual network?
   ```

   您可能會看到類似以下截圖的回應。

    ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-8.png "顯示 GitHub Copilot for Azure 的回應，解釋虛擬網絡的概念。")

1. 當您滿意時，通過在終端運行以下命令來運行 `azd init` command in the terminal. Answer its prompts. If you're unsure what to answer for a prompt, ask GitHub Copilot for Azure for help.

1. Before you can continue, you must authenticate the `azd` 工具：

    ```cmd
    azd auth login
    ```

    1. 這將打開一個瀏覽器，要求您進行 Azure 身份驗證。選擇與之前相同的憑據。

1. 當新專案初始化完成且您已完成 Azure 驗證後，使用 **azd up** 命令將應用程式部署到您的訂閱中。在終端機中，依照原始提示回覆中的說明執行該命令。

    ```
    azd up
    ```

1. `azd up` 命令會詢問有關您的訂閱、資源的部署位置等資訊。

    如果您不確定如何回答，您可以請求 GitHub Copilot for Azure 的協助。例如，您可以詢問：

    ```prompt
    @azure azd up 詢問我要將網站部署到哪個位置。我該如何回答？
    ```

    您可能會看到類似以下截圖的回應。

    ![顯示 GitHub Copilot 聊天面板的截圖](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/images/mod2-CopilotChat-9.png "顯示 GitHub Copilot for Azure 的回應，描述 Azure 位置及如何選擇。")

5. 繼續回答 `azd up`. Ask GitHub Copilot for Azure questions as needed.

    1. When asked the location select **Canada Central**.

    Depending on the `azd` template that you're deploying and the location that you selected, the template might take 20 to 40 minutes (or more) to deploy. But we can Move on to [Module 3](https://github.com/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/09-Using-GitHub-Copilot-for-Azure-to-Deploy-to-Cloud/03-Get-Answers-to-your-Questions-about-Azure-Services-and-Resources.md) while it completes

1. If `azd up` 的提示，如果出現錯誤，請向 GitHub Copilot for Azure 詢問該錯誤及如何解決。

    > **提示**
    > 若要輕鬆附加上次終端命令的結果，請使用聊天面板左下角的回形針圖標。GitHub Copilot for Azure 無法知道終端命令的結果，除非它們被複製/粘貼或通過回形針附加。
