* **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
* **學習內容**：使用 GitHub Copilot 建立程式碼並為您的工作添加註釋。
* **將建構的內容**：由 Copilot AI 生成程式碼和註釋建議的 Python 文件。
* **先決條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
* **時間**：此模組可在一小時內完成。

在本模組結束時，您將獲得以下技能：

* 編寫提示以從 GitHub Copilot 獲取建議
* 應用 GitHub Copilot 改進您的項目。

## 先決條件閱讀：

* [使用 GitHub Copilot 進行提示工程的介紹](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
* [使用 GitHub Copilot 與 Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## 要求

1. 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)
2. 打開 [此 Codespaces 的儲存庫](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 練習

**右鍵單擊以下 Codespaces 按鈕以在新標籤中打開您的 Codespaces **

[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

該 API 已經有一個生成令牌的單一端點。讓我們通過添加一個新的端點來更新 API，使其接受文本並返回令牌列表。

### 🛠 步驟 1：添加 Pydantic 模型

轉到 `main.py` 文件，導航到提供程式碼的底部，選擇 **Ctrl + I (PC)**  或 **Cmd + I (Mac)**，並將以下內容複製到提供的 GitHub Copilot 聊天框中，以便它可以為您生成 `Pydantic` 模型：

```
Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string.
```

生成的模型應該如下所示：

```python
    class TextData(BaseModel):
        text: str
```

> \[!NOTE]
> 您可能會在編輯器中看到一些 linter 警告 (以紅色虛線下劃線識別)，這些可以忽略。這些包括過長的行或甚至不需要的新行。隨意處理它們，儘管這些不應影響您的應用程序正常運行。

### 🔎 步驟 2：生成新的端點

接下來，通過在 `main.py` 文件的最後一條路由下方添加註釋，使用 GitHub Copilot 生成一個新的端點。

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text
```

您可能會收到使用未匯入的模組或函式庫的建議。如果是這樣，您可以要求 GitHub Copilot 幫助您匯入正確的模組，方法是選擇生成的程式碼並使用 Command+I (Apple) 或 Control+I (Windows)，並添加提示以添加缺失的匯入。這個小彈出窗口稱為內聯聊天，是與 GitHub Copilot 交互的另一種方式。

### 🐍 步驟 3：解釋程式碼

確認 `generate()` 路由使用單行程式碼建立偽隨機令牌 ID，這可能難以完全理解。選取整個函式，然後在選取部分上按右鍵，選擇 Copilot 選單項目，接著選擇「解釋這段程式碼」選項。GitHub Copilot 聊天介面將在左側開啟，並提供實用的解釋，您可以用它來互動式地提出更多問題。

最後，請前往 `/docs` 端點並確認新端點有正確顯示，以驗證新端點是否正常運作。

🚀 恭喜您完成此練習！您不只使用 Copilot 產生程式碼，還以互動且有趣的方式完成了任務！您可以使用 GitHub Copilot 不只產生程式碼，還可以撰寫文件、測試應用程式等等。

### 💡 步驟 4：使用斜線命令

現在您已經使用 GitHub Copilot 產生並解釋了程式碼，讓我們探索一些執行開發者任務的其他方法。這些額外的挑戰將幫助您深入了解 GitHub Copilot 的其他功能。您將使用聊天介面進行這些額外的挑戰。如果尚未開啟，請點擊左側邊欄上的 GitHub Copilot 聊天圖示。

**產生文件**

在開啟 `main.py` 的情況下，使用聊天介面並輸入以下文字：

```
/doc 我需要為這些 API 路由撰寫文件。請幫我產生可以放入此專案 README.md 檔案的文件
```

斜線命令 `/doc` 是 GitHub Copilot 的特定功能，用於撰寫文件。如果結果看起來不錯，請將其新增到 README.md 檔案的新章節中。

**產生測試**

目前的程式碼沒有任何測試。在此挑戰中，您將使用 `/tests` 命令。在開啟 `main.py` 的情況下，使用聊天介面並輸入以下提示：

```
/tests 請幫我使用 FastAPI 測試客戶端和 Pytest 框架為 generate() 路由撰寫測試。請說明我應該將測試檔案放在哪裡、如何將 Pytest 相依性加入專案中，以及如何執行測試
```

斜線命令 `/tests` 將指導您撰寫路由的新測試，並提供所有必要資訊以供您驗證工作成果。

**工作區挑戰**

最後，您將有機會使用「代理程式」。代理程式是 Visual Studio Code 中 GitHub Copilot 的特殊功能，可讓特定內容與 GitHub Copilot 共享。在此最後的挑戰中，您將使用 `@workspace` 代理程式，它包含目前工作區的檔案以提供更多內容。您將解決一個與如何執行整個應用程式相關的問題。在這種情況下，您將增強 README.md 以提供更多跨檔案的具體細節。

對於這個最後的挑戰，您不需要開啟任何檔案。在 GitHub Copilot 聊天視窗中使用以下提示：

```
@workspace 我想提供關於如何使用 uvicorn 網頁伺服器執行此應用程式的說明，我還需要提供如何正確安裝相依套件的說明，以及 FastAPI 框架的一些特性。我將用這些來改進 README.md 檔案
```

## 法律聲明

微軟及任何貢獻者授予您在本庫中使用微軟文檔和其他內容的許可，根據 [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode) 授權，詳情見 [LICENSE](../../../05-Using-GitHub-Copilot-with-Python/LICENSE) 文件，並授予您對本庫中任何程式碼的許可，根據 [MIT License](https://opensource.org/licenses/MIT) 授權，詳情見 [LICENSE-CODE](../../../05-Using-GitHub-Copilot-with-Python/LICENSE-CODE) 文件。

微軟、Windows、Microsoft Azure 和 / 或文檔中提到的其他微軟產品和服務可能是微軟在美國和 / 或其他國家的商標或註冊商標。本項目的許可不授予您使用任何微軟名稱、標誌或商標的權利。微軟的一般商標指導方針可在 <http://go.microsoft.com/fwlink/?LinkID=254653> 查找。

隱私資訊可在 <https://privacy.microsoft.com/en-us/> 查找。

微軟及任何貢獻者保留所有其他權利，無論是根據各自的版權、專利，還是商標，無論是明示、默示還是其他方式。
