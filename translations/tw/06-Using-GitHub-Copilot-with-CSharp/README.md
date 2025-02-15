<header>

# 使用 GitHub Copilot 與 C\#

GitHub Copilot 是首個大規模的 AI 開發工具，旨在通過提供智能的自動完成功能來徹底改變程式設計方式。在這個模組中，我們將探索如何利用 GitHub Copilot 來提高您在 C# 程式設計時的效率。

作為一名開發者，最大化生產力和簡化程式設計過程是關鍵目標。GitHub Copilot 作為您 AI 驅動的配對程序員，提供針對您程式碼的上下文感知建議。在這個模組結束時，您將學會如何在 Codespaces 中配置 GitHub Copilot，並輕鬆利用其功能生成和實現程式碼建議。

準備好迎接一個實用的實作項目吧！您將會修改一個 C# 儲存庫，使用 GitHub Copilot 建立一個 API 端點。這個練習將提供寶貴的經驗，幫助您建立一個提供 HTTP API 的 C# 網頁應用程序，並生成伪隨機的天氣預報數據。

</header>

* **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
* **學習內容**：如何使用 GitHub Copilot 建立程式碼並為您的工作添加註釋。
* **建立內容**：C# 檔案，將由 Copilot AI 生成程式碼和註釋建議。
* **先決條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
* **時間安排**：此課程可以在一小時內完成。

在這個模組結束時，您將獲得以下技能：

* 編寫提示以生成來自 GitHub Copilot 的建議
* 應用 GitHub Copilot 改進您的項目。

## 先決閱讀：

* [使用 GitHub Copilot 的提示工程介紹](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot?WT.mc_id=academic-113596-abartolo)

* [Visual Studio 的 GitHub Copilot 擴展是什麼？](https://learn.microsoft.com/en-us/visualstudio/ide/visual-studio-github-copilot-extension?view=vs-2022\&WT.mc_id=academic-113596-abartolo)

## 要求

1. 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)

2. 熟悉 [這個包含 Codespaces 的儲存庫](https://github.com/github/dotnet-codespaces)

## 💪🏽 練習

**右鍵點擊以下 Codespaces 按鈕以在新標籤頁中打開您的 Codespace**

[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/github/dotnet-codespaces)

"**GitHub Codespaces ♥️ .NET 8**" 儲存庫使用最小化 API 建構了一個天氣 API，開啟 Swagger 以便您可以調用和測試 API，並使用 Blazor 和 .NET 8 在網頁應用中顯示數據。

我們將回顧通過添加一個新的端點來更新天氣後端應用的步驟，該端點請求特定位置並返回該位置的天氣預報。

### 🗒️ 步驟 1：熟悉 "GitHub Codespaces ♥️ .NET 8" 儲存庫

當您在 Codespaces 中打開儲存庫時，您將看到一個新的瀏覽器窗口，裡面有一個功能完整的 Codespace。這個儲存庫中的所有內容都包含在這一個 Codespace 中。例如，在瀏覽器面板中，我們可以看到後端和前端項目的主要程式碼。

![新的 Codespace，儲存庫中的所有內容運行中](../../../06-Using-GitHub-Copilot-with-CSharp/005OpenRepoInCodeSpaces.png)

為了運行後端項目，請轉到 "運行和調試" 面板，並選擇 "後端" 項目。

![在後端項目中打開 program.cs](../../../06-Using-GitHub-Copilot-with-CSharp/006RunBackEndProject.png)

開始調試所選項目。天氣 API 項目，我們的後端項目現在將在 8080 端口運行。我們可以從 _端口_ 面板複製已發布的網址。

![從端口面板複製應用網址](../../../06-Using-GitHub-Copilot-with-CSharp/007ProjectRunningOpenInNewTab.png)

後端應用程序發布了一個名為 `weatherforecast` 的端點，用於生成隨機的預報數據。要測試當前運行的應用程序，您可以將 `/weatherforecast` 添加到已發布的網址中。最終網址應該類似於這個：

```bash
https://< your url>.app.github.dev/weatherforecast
```

在瀏覽器中運行的應用程序應該是這樣的。

![測試運行的應用程序。](../../../06-Using-GitHub-Copilot-with-CSharp/008TestRunningApi.png)

現在讓我們在應用程式中新增一個中斷點，以便偵錯每次對 API 的呼叫。前往 `Program.cs` 檔案，該檔案位於 BackEnd 專案中。檔案路徑為 `SampleApp\BackEnd\Program.cs`。

在第 24 行新增中斷點（按下 F9）並重新整理瀏覽器中的網址以測試端點。瀏覽器此時不會顯示天氣預報，而在 Visual Studio 編輯器中我們可以看到程式執行在第 24 行暫停。

![偵錯執行中的應用程式](../../../06-Using-GitHub-Copilot-with-CSharp/009DebugBackEndDemo.png)

按下 F10 我們可以逐步偵錯直到第 32 行，在那裡我們可以看到產生的值。應用程式應該已經為接下來的 5 天產生了範例天氣值。變數 `forecast` 包含這些值的陣列。

![偵錯執行中的應用程式](../../../06-Using-GitHub-Copilot-with-CSharp/010DebugForecastValue.png)

您現在可以停止偵錯了。

恭喜！現在您已準備好使用 GitHub Copilot 為應用程式新增更多功能。

### 🗒️ 步驟 2：熟悉 GitHub Copilot 斜線命令

當我們開始處理程式碼時，通常需要重構一些程式碼，或獲取更多上下文和解釋。使用 GitHub Copilot 聊天功能，我們可以進行 AI 驅動的對話來完成這些任務。

開啟 BackEnd 專案中的 `Program.cs` 檔案。檔案路徑為 `SampleApp\BackEnd\Program.cs`。

現在讓我們使用 GitHub Copilot 的斜線命令來理解一段程式碼。選擇第 22-35 行，按下 `CTRL + I` 開啟內嵌聊天，輸入 `/explain`。

![使用斜杠命令解釋一段程式碼](../../../06-Using-GitHub-Copilot-with-CSharp/011SlashCommandExplain.gif)

在聊天面板中，GitHub Copilot 將生成所選程式碼的詳細解釋。摘要版本將是這樣的：

```
The selected C# code is part of an ASP.NET Core application using the minimal API feature. It defines a GET endpoint at "/weatherforecast" that generates an array of WeatherForecast objects. Each object is created with a date, a random temperature, and a random summary. The endpoint is named "GetWeatherForecast" and has OpenAPI support for standardized API structure documentation.
```

**斜線命令**是您可以在聊天中使用的特殊命令，用於對程式碼執行特定操作。例如，您可以使用：

* `/doc` 來新增文件註解
* `/explain` 來解釋程式碼
* `/fix` 來提出修復所選程式碼問題的建議
* `/generate` 來產生程式碼以回答您的問題

讓我們使用 `/tests` 命令來為程式碼產生測試。選擇第 39-42 行，按下 `CTRL + I` 開啟內嵌聊天，輸入 `/tests`（或選擇 /tests 斜線命令）來為此記錄產生新的測試集。

![Use slash command to generate tests for the selected piece of code](../../../06-Using-GitHub-Copilot-with-CSharp/012SlashCmdTests.gif)

此時，GitHub Copilot 將建議一個新類別。您需要先按下 [建立] 來建立新檔案。

一個新的 `ProgramTests.cs` 類別已被建立並加入專案中。這些測試使用 XUnit，但您也可以使用類似 `/tests 使用 MSTests 進行單元測試` 的命令來使用其他單元測試函式庫產生測試。

_**重要**：我們不會在這個專案中使用測試檔案。您必須刪除已產生的測試檔案才能繼續。_

最後，讓我們使用 `/doc` 來為程式碼產生自動文件。選擇第 39-42 行，按下 `CTRL + I` 開啟內嵌聊天，輸入 `/doc`（或選擇該命令）來為此記錄產生文件。

![Use slash command to generate the documentation for a piece of code](../../../06-Using-GitHub-Copilot-with-CSharp/013SlashCmdDoc.gif)

內嵌聊天、聊天面板和斜線命令是支援我們使用 GitHub Copilot 開發體驗的絕佳工具。現在我們已準備好為這個應用程式新增更多功能。

### 🗒️ Step 3: Generate a new Record that includes the city name

Go to the `Program.cs` file in the BackEnd project. The file is in the following path `SampleApp\BackEnd\Program.cs`。

![在後端項目中打開 program.cs](../../../06-Using-GitHub-Copilot-with-CSharp/011OpenBackEndProject.png)

導航到文件末尾，並要求 Copilot 生成一個新記錄，包含城市名稱。

```csharp
// create a new internal record named WeatherForecastByCity that request the following parameters: City, Date, TemperatureC, Summary
```

生成的程式碼應該類似於這個：

```csharp
// create a new internal record named WeatherForecastByCity that request the following parameters: City, Date, TemperatureC, Summary
internal record WeatherForecastByCity(string City, DateOnly Date, int TemperatureC, string? Summary)
{
    public int TemperatureF => 32 + (int)(TemperatureC / 0.5556);
}
```

您可以在接下來的動畫中查看提示的運作：

![在後端項目中打開 program.cs](../../../06-Using-GitHub-Copilot-with-CSharp/014AddNewRecord.gif)

### 🔎 步驟 4：生成一個新的端點以獲取城市的天氣預報

現在讓我們生成一個新的 API 端點，類似於 `/weatherforecast`，同時也包含城市名稱。新的 API 端點名稱將是 **`/weatherforecastbycity`**。

_**重要**： 您必須將程式碼放在 '.WithOpenApi ();' 行之後，這從第 36 行開始。還要記得在每一行新建議的程式碼中按 TAB，直到整個端點定義完成。_

接下來，通過添加註釋來使用 GitHub Copilot 生成一個新端點：

```csharp
// Create a new endpoint named /WeatherForecastByCity/{city}, that accepts a city name in the urls as a paremeter and generates a random forecast for that city
```

在接下來的示例中，我們在前一個端點之後添加了一些額外的空行，然後 GitHub Copilot 生成了新的端點。一旦端點的核心程式碼生成後，GitHub Copilot 也建議了端點的名稱 (第 49 行) 和 OpenAPI 規範 (第 50 行)。記得按 \[TAB] 接受這些建議。

![Copilot 幽靈建議的新端點](../../../06-Using-GitHub-Copilot-with-CSharp/020GeneratedCode.gif)

_**重要**： 此提示生成多行 C# 程式碼。強烈建議檢查和審核生成的程式碼，以確保其按預期工作。_

生成的程式碼應類似於這個：

```csharp
// Create a new endpoint named /WeatherForecastByCity/{city}, that accepts a city name in the urls as a paremeter and generates a random forecast for that city
app.MapGet("/WeatherForecastByCity/{city}", (string city) =>
{
    var forecast = new WeatherForecastByCity
    (
        city,
        DateOnly.FromDateTime(DateTime.Now),
        Random.Shared.Next(-20, 55),
        summaries[Random.Shared.Next(summaries.Length)]
    );
    return forecast;
})
.WithName("GetWeatherForecastByCity")
.WithOpenApi();
```

### 🐍 步驟 5：測試新端點。

最後，通過從運行和調試面板啟動項目來驗證新端點是否正常運行。
選擇運行和調試，然後選擇後端項目。

![打開運行和調試面板並選擇後端項目](../../../06-Using-GitHub-Copilot-with-CSharp/030RunAndDebugTheBackEndProject.png)

現在按運行，項目應該會建構並運行。項目運行後，我們可以使用您的 Codespace 網址和原始端點測試原始網址：

```bash
https://< your code space url >.app.github.dev/WeatherForecast
```

新的端點也將準備好進行測試。這裡有一些不同城市的示例網址：

```bash
https://< your code space url >.app.github.dev/WeatherForecastByCity/Toronto

https://< your code space url >.app.github.dev/WeatherForecastByCity/Madrid

https://< your code space url >.app.github.dev/WeatherForecastByCity/<AnyCityName>
```

兩個測試運行應該是這樣的：

![打開運行和調試面板並選擇後端項目](../../../06-Using-GitHub-Copilot-with-CSharp/032TestAndDebugUsingUrls.png)

🚀 恭喜您，通過這個練習，您不僅使用 GitHub Copilot 生成了程式碼，還以互動和有趣的方式完成了它！您可以使用 GitHub Copilot 不僅生成程式碼，還撰寫文檔、測試應用程序等。

## 法律聲明

微軟及任何貢獻者授予您在此儲存庫中使用微軟文檔及其他內容的許可，根據 [創用 CC 姓名標示 4.0 國際公共授權](https://creativecommons.org/licenses/by/4.0/legalcode)，詳情請參見 [LICENSE](../../../06-Using-GitHub-Copilot-with-CSharp/LICENSE) 文件，並授予您對儲存庫中任何程式碼的許可，根據 [MIT 許可證](https://opensource.org/licenses/MIT)，詳情請參見 [LICENSE-CODE](../../../06-Using-GitHub-Copilot-with-CSharp/LICENSE-CODE) 文件。

微軟、Windows、Microsoft Azure 和 / 或其他微軟產品及服務在文檔中提及的名稱可能是微軟在美國和 / 或其他國家的商標或註冊商標。
本項目的許可不授予您使用任何微軟名稱、標誌或商標的權利。
微軟的一般商標指南可在 <http://go.microsoft.com/fwlink/?LinkID=254653> 上找到。

隱私資訊可在 <https://privacy.microsoft.com/en-us/> 查找。

微軟及任何貢獻者保留所有其他權利，無論是根據其各自的版權、專利或商標，無論是隱含的、禁反言的還是其他方式。
