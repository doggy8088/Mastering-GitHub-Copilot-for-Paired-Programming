- **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
- **學習內容**：使用 GitHub Copilot 創建代碼並為您的工作添加註釋。
- **將構建的內容**：由 Copilot AI 生成代碼和註釋建議的 Python 文件。
- **先決條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
- **時間**：此模組可在一小時內完成。

在本模組結束時，您將獲得以下技能：

- 編寫提示以從 GitHub Copilot 獲取建議
- 應用 GitHub Copilot 改進您的項目。

## 先決條件閱讀：
- [使用 GitHub Copilot 進行提示工程的介紹](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [使用 GitHub Copilot 與 Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## 要求

1. 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)
1. 打開 [此代碼空間的庫](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 練習

**右鍵單擊以下代碼空間按鈕以在新標籤中打開您的代碼空間**

[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

該 API 已經有一個生成令牌的單一端點。讓我們通過添加一個新的端點來更新 API，使其接受文本並返回令牌列表。

### 🛠 步驟 1：添加 Pydantic 模型

轉到 `main.py` 文件，導航到提供代碼的底部，選擇 **Ctrl + I (PC)** 或 **Cmd + I (Mac)**，並將以下內容複製到提供的 GitHub Copilot 聊天框中，以便它可以為您生成 `Pydantic` 模型：

```
Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string.
```

生成的模型應該如下所示：

```python
    class TextData(BaseModel):
        text: str
```

> [!NOTE]
> 您可能會在編輯器中看到一些 linter 警告（以紅色虛線下劃線識別），這些可以忽略。這些包括過長的行或甚至不需要的新行。隨意處理它們，儘管這些不應影響您的應用程序正常運行。

### 🔎 步驟 2：生成新的端點

接下來，通過在 `main.py` 文件的最後一條路由下方添加註釋，使用 GitHub Copilot 生成一個新的端點。

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text 
```

您可能會收到使用未導入的模塊或庫的建議。如果是這樣，您可以要求 GitHub Copilot 幫助您導入正確的模塊，方法是選擇生成的代碼並使用 Command+I (Apple) 或 Control+I (Windows)，並添加提示以添加缺失的導入。這個小彈出窗口稱為內聯聊天，是與 GitHub Copilot 交互的另一種方式。

### 🐍 步驟 3：解釋代碼

確認 `generate()` route creates a pseudo-random token ID using a single line that might be difficult to fully understand. Select the whole function, and then right click on the selection, then select the Copilot menu item, and then the _"Explain This"_ option. The GitHub Copilot chat interface will open to the left and provide you a useful explanation which you can use to interactively ask more questions.

Finally, verify the new endpoint is working by trying it out by going to the `/docs` 端點並確保該端點顯示出來。

🚀 恭喜您，通過這個練習，您不僅使用 Copilot 生成了代碼，還以互動和有趣的方式完成了它！您可以使用 GitHub Copilot 不僅生成代碼，還可以撰寫文檔、測試應用程序等等。

### 💡 步驟 4：使用斜杠命令

現在您已經使用 GitHub Copilot 生成並解釋了代碼，您還可以探索一些其他替代方法來執行開發者任務。這些額外的挑戰將幫助您深入了解其他 GitHub Copilot 功能，除了您已經知道的功能。對於這些額外的挑戰，您將使用聊天界面。如果您尚未打開它，請單擊左側邊欄上的 GitHub Copilot 聊天圖標。

**生成文檔**

在 `main.py` 打開的情況下，使用聊天界面並輸入以下文本：

```
/doc I need to document the routes for these API Routes. Help me produce documentation I can put in the README.md file of this project
```

斜杠命令 `/doc` part of the prompt is called a _"slash command"_ and it is a specific feature of GitHub Copilot that allows you to write documentation. If the results look good, add them to a new section of your README.md file.


**Generate tests**
 
The current code doesn't have any tests. For this challenge, you will use the `/tests`。在 `main.py` 打開的情況下，使用聊天界面並輸入以下提示：

```
/tests help me write a test for the generate() route using the FastAPI test client and the Pytest framework. Help me understand where I should put the test file, how to add the Pytest dependency to my project, and how to run the tests
```

斜杠命令 `/tests` slash command will guide you through on writing a new test for your route and give you everything you need so that you can verify your work.

**Workspace challenge**
 
Finally, you will get a chance to use an _agent_. Agents are a special feature of GitHub Copilot in Visual Studio Code that allow specific context to be shared with GitHub Copilot. For this final challenge, you will use the `@workspace` agent which includes files from the current worspace to provide more context. You will solve a problem which is related to how to run the whole application. In this case, you will enhance the README.md for more specifics that span multiple files. Using `@workspace` 幫助提供更多上下文，而無需打開多個文件。

對於這個最後的挑戰，您不需要有任何打開的文件。在 GitHub Copilot 聊天窗口中使用以下提示：

```
@workspace I want to provide instructions on how to run this application using the uvicorn webserver, I also need to provide instructions on how to install the dependencies properly and what are some characteristics of the FastAPI framework. I will use this to improve the README.md file
```

結果應該是對 FastAPI 的非常好的解釋，包括如何運行應用程序以及如何安裝依賴項。回應的最上方可能包含所有用於確定需要使用哪些文件以提供 GitHub Copilot 正確上下文的參考。

## 法律聲明

微軟及任何貢獻者授予您在本庫中使用微軟文檔和其他內容的許可，根據 [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode) 授權，詳情見 [LICENSE](../../../05-Using-GitHub-Copilot-with-Python/LICENSE) 文件，並授予您對本庫中任何代碼的許可，根據 [MIT License](https://opensource.org/licenses/MIT) 授權，詳情見 [LICENSE-CODE](../../../05-Using-GitHub-Copilot-with-Python/LICENSE-CODE) 文件。

微軟、Windows、Microsoft Azure 和/或文檔中提到的其他微軟產品和服務可能是微軟在美國和/或其他國家的商標或註冊商標。本項目的許可不授予您使用任何微軟名稱、標誌或商標的權利。微軟的一般商標指導方針可在 http://go.microsoft.com/fwlink/?LinkID=254653 查找。

隱私信息可在 https://privacy.microsoft.com/en-us/ 查找。

微軟及任何貢獻者保留所有其他權利，無論是根據各自的版權、專利，還是商標，無論是明示、默示還是其他方式。

**免責聲明**：  
本文件是使用基於機器的人工智慧翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議進行專業的人類翻譯。我們對因使用此翻譯而產生的任何誤解或誤釋不承擔責任。