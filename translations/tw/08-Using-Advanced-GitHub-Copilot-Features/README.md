- **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
- **學習內容**：使用進階的 GitHub Copilot 功能來測試、記錄和處理代碼。
- **建構內容**：一個新的 HTTP API 路由，並附上文檔和測試以驗證其正確性。
- **前置條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
- **所需時間**：此模組可在一小時內完成。

在這個模組結束時，你將掌握以下技能：

- 使用進階的 GitHub Copilot 功能，如內嵌聊天、斜線命令和代理。
- 與 GitHub Copilot 進行更深入的項目互動，並提出相關問題。

## 前置閱讀：
- [使用 GitHub Copilot 進行提示工程的介紹](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [使用進階的 GitHub Copilot 功能](https://learn.microsoft.com/training/modules/advanced-github-copilot/?WT.mc_id=academic-113596-abartolo)

## 要求

1. 啟用你的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)
1. 打開 [這個 Codespaces 倉庫](https://codespaces.new/MicrosoftDocs/mslearn-advanced-copilot)

## 💪🏽 練習

**右鍵點擊以下 Codespaces 按鈕，在新標籤頁中打開你的 Codespace**

[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

目前的 API 尚未公開 country/{country}，這需要實作以列出城市。該路由應僅允許 GET HTTP 請求，並以 JSON 格式回應，提供該國、城市和指定月份的歷史高低資訊。

與任何實作一樣，這項新增功能應至少包含一個測試函數，以便與 pytest 運行器和測試框架一起使用。

### 🛠 步驟 1：新增路由
在我們的第一次練習中，我們將在 API 中創建一個新路由。前往 main.py 文件，並使用內嵌聊天，輸入以下命令 `ctrl` + `i`（在 Windows 上）或 `cmd` + `i`（在 Mac 上），請求 GitHub Copilot 幫助你創建一個新的 API，以顯示某個國家的城市。

在內嵌聊天中使用以下提示：

```
Create a new route that exposes the cities of a country.
```

這個提示應該會給你類似這樣的結果：

```python
# Create a new route that exposes the cities of a country:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())

```

> [!NOTE]
> 測試你的新路由並不斷調整你的提示，直到結果符合預期。

### 🔎 步驟 2：創建測試
現在你已經創建了一個新路由，讓我們為這個使用西班牙作為國家的路由創建一個測試。記得選擇你的代碼，並請求 Copilot Chat 幫助你進行這個我們剛創建的 API 測試。

使用以下提示與 GitHub Copilot Chat：

```
/tests help me to create a new test for this route that uses Spain as the country.
```

![Copilot Chat 圖像示例](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-advanced-copilot/main/images/ideascopilot.png)

一旦 Copilot 幫助你創建了測試，請嘗試執行它。如果運行結果不如預期，隨時可以與 Copilot 在聊天中分享這些細節。例如：

```
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```

這應該會給你另一個解決方案。繼續嘗試，直到達到所需結果。

### 🐍 步驟 3：使用代理撰寫項目
在這一步中，我們將使用代理（工作區）來撰寫有關如何運行此項目的文檔。在 GitHub Copilot Chat 中，我們將嘗試以下提示：

`> @workspace help me to use an agent to write the project documentation on how to run it .`

Finally, verify the new endpoint is working by trying it out by going to the `/docs` 端點並確認該端點顯示出來。

### 💡 步驟 4：使用斜線命令

現在你已經使用 GitHub Copilot 生成和解釋代碼，你也可以探索一些其他替代方法來執行開發者任務。這些額外的挑戰將幫助你更深入地了解 GitHub Copilot 的其他功能，除了你已經知道的功能。對於這些額外的挑戰，你將使用聊天界面。如果你還沒有打開它，請點擊左側邊欄的 GitHub Copilot Chat 圖標。

🚀 恭喜你，通過這次練習，你已經使用了 GitHub Copilot 的多種不同功能，這將使你能夠更好地處理不同的項目。你互動地使用了一些功能來撰寫測試、文檔，並了解更多有關現有代碼的信息。

## 法律聲明

微軟及任何貢獻者授予你在此倉庫中使用微軟文檔及其他內容的許可，依據 [創用 CC 姓名標示 4.0 國際公共許可證](https://creativecommons.org/licenses/by/4.0/legalcode)，詳情見 [LICENSE](../../../08-Using-Advanced-GitHub-Copilot-Features/LICENSE) 文件，並授予你在該倉庫中使用任何代碼的許可，依據 [MIT 許可證](https://opensource.org/licenses/MIT)，詳情見 [LICENSE-CODE](../../../08-Using-Advanced-GitHub-Copilot-Features/LICENSE-CODE) 文件。

微軟、Windows、Microsoft Azure 及/或其他在文檔中提及的微軟產品和服務，可能是微軟在美國及/或其他國家的商標或註冊商標。本項目的許可不授予你使用任何微軟名稱、標誌或商標的權利。微軟的一般商標指導方針可以在 http://go.microsoft.com/fwlink/?LinkID=254653 找到。

隱私信息可以在 https://privacy.microsoft.com/en-us/ 查找。

微軟及任何貢獻者保留所有其他權利，無論是根據其各自的版權、專利或商標，無論是隱含的、禁止反言的或其他方式。

**免責聲明**：  
本文件是使用基於機器的人工智慧翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人工翻譯。我們對因使用本翻譯而產生的任何誤解或誤讀不承擔責任。