<header>

# 使用 GitHub Copilot 與 C#

GitHub Copilot 是首個大規模的 AI 開發工具，旨在通過提供智能的自動完成功能來徹底改變編碼方式。在這個模組中，我們將探索如何利用 GitHub Copilot 來提高您在 C# 編碼時的效率。

作為一名開發者，最大化生產力和簡化編碼過程是關鍵目標。GitHub Copilot 作為您 AI 驅動的配對程序員，提供針對您代碼的上下文感知建議。在這個模組結束時，您將學會如何在 Codespaces 中配置 GitHub Copilot，並輕鬆利用其功能生成和實現代碼建議。

準備好迎接一個實用的實作項目吧！您將會修改一個 C# 儲存庫，使用 GitHub Copilot 創建一個 API 端點。這個練習將提供寶貴的經驗，幫助您建立一個提供 HTTP API 的 C# 網頁應用程序，並生成伪隨機的天氣預報數據。

</header>

- **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
- **學習內容**：如何使用 GitHub Copilot 創建代碼並為您的工作添加註釋。
- **建立內容**：C# 檔案，將由 Copilot AI 生成代碼和註釋建議。
- **先決條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
- **時間安排**：此課程可以在一小時內完成。

在這個模組結束時，您將獲得以下技能：

- 編寫提示以生成來自 GitHub Copilot 的建議
- 應用 GitHub Copilot 改進您的項目。

## 先決閱讀：
- [使用 GitHub Copilot 的提示工程介紹](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot?WT.mc_id=academic-113596-abartolo)

- [Visual Studio 的 GitHub Copilot 擴展是什麼？](https://learn.microsoft.com/en-us/visualstudio/ide/visual-studio-github-copilot-extension?view=vs-2022&WT.mc_id=academic-113596-abartolo)

## 要求

1. 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)

1. 熟悉 [這個包含 Codespaces 的儲存庫](https://github.com/github/dotnet-codespaces)

## 💪🏽 練習

**右鍵點擊以下 Codespaces 按鈕以在新標籤頁中打開您的 Codespace**
 
[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/github/dotnet-codespaces)

"**GitHub Codespaces ♥️ .NET 8**" 儲存庫使用最小化 API 構建了一個天氣 API，開啟 Swagger 以便您可以調用和測試 API，並使用 Blazor 和 .NET 8 在網頁應用中顯示數據。

我們將回顧通過添加一個新的端點來更新天氣後端應用的步驟，該端點請求特定位置並返回該位置的天氣預報。

### 🗒️ 步驟 1：熟悉 "GitHub Codespaces ♥️ .NET 8" 儲存庫

當您在 Codespaces 中打開儲存庫時，您將看到一個新的瀏覽器窗口，裡面有一個功能完整的 Codespace。這個儲存庫中的所有內容都包含在這一個 Codespace 中。例如，在瀏覽器面板中，我們可以看到後端和前端項目的主要代碼。

![新的 Codespace，儲存庫中的所有內容運行中](../../../06-Using-GitHub-Copilot-with-CSharp/005OpenRepoInCodeSpaces.png)

為了運行後端項目，請轉到 "運行和調試" 面板，並選擇 "後端" 項目。

![在後端項目中打開 program.cs](../../../06-Using-GitHub-Copilot-with-CSharp/006RunBackEndProject.png)

開始調試所選項目。天氣 API 項目，我們的後端項目現在將在 8080 端口運行。我們可以從 *端口* 面板複製已發布的網址。

![從端口面板複製應用網址](../../../06-Using-GitHub-Copilot-with-CSharp/007ProjectRunningOpenInNewTab.png)

後端應用程序發布了一個名為 `weatherforecast` 的端點，用於生成隨機的預報數據。要測試當前運行的應用程序，您可以將 `/weatherforecast` 添加到已發布的網址中。最終網址應該類似於這個：

```bash
https://< your url>.app.github.dev/weatherforecast
```
在瀏覽器中運行的應用程序應該是這樣的。

![測試運行的應用程序。](../../../06-Using-GitHub-Copilot-with-CSharp/008TestRunningApi.png)

現在讓我們在應用程序中添加一個斷點，以調試每次調用 API。轉到 `Program.cs` file in the BackEnd project. The file is in the following path `SampleApp\BackEnd\Program.cs`. 

Add a breakpoint in line 24 (press F9) and refresh the browser with the Url to test the endpoint. The browser should not show the weather forecast, and in the Visual Studio Editor we can see how the program execution was paused at line 24.

![debug the running application.](../../../06-Using-GitHub-Copilot-with-CSharp/009DebugBackEndDemo.png)

Pressing F10 we can debug step-by-step until line 32, where we can see the generated values. The application should have been generated samples Weather values for the next 5 days. The variable `forecast` has an array containing these values.

![debug the running application.](../../../06-Using-GitHub-Copilot-with-CSharp/010DebugForecastValue.png)

You can stop debugging now.


Congratulations! Now you are ready to add more features into the app using GitHub Copilot.

### 🗒️ Step 2: Get familiarized with GitHub Copilot Slash Commands

As we start working in our codebase, we usually need to refactor some code, or get more context or explanations about it. Using GitHub Copilot Chat, we can have AI-driven conversations to perform these tasks. 

Open the file `Program.cs` in the BackEnd project. The file is in the following path `SampleApp\BackEnd\Program.cs`. 

Now let's use a slash command, in GitHub Copilot to understand a piece of code. Select lines 22-35, press `CTRL + I` to open the inline chat, and type `/explain`。

![使用斜杠命令解釋一段代碼](../../../06-Using-GitHub-Copilot-with-CSharp/011SlashCommandExplain.gif)

在聊天面板中，GitHub Copilot 將生成所選代碼的詳細解釋。摘要版本將是這樣的：

```
The selected C# code is part of an ASP.NET Core application using the minimal API feature. It defines a GET endpoint at "/weatherforecast" that generates an array of WeatherForecast objects. Each object is created with a date, a random temperature, and a random summary. The endpoint is named "GetWeatherForecast" and has OpenAPI support for standardized API structure documentation.
```

**斜杠命令**是您可以在聊天中使用的特殊命令，用於對代碼執行特定操作。例如，您可以使用：
- `/doc` to add a documentation comment 
- `/explain` to explain the code 
- `/fix` to propose a fix for the problems in the selected code 
- `/generate` to generate code to answer your question

Let's use the `/tests` command to generate tests to the code. Select lines 39-42, press `CTRL + I` to open the inline chat, and type `/tests` (or select the /tests slash command) to generate a new set of tests for this record.

![Use slash command to generate tests for the selected piece of code](../../../06-Using-GitHub-Copilot-with-CSharp/012SlashCmdTests.gif)

At this point, GitHub Copilot will suggest a new class. You need to first press [Create] to create the new file. 

A new class `ProgramTests.cs` was created and added to the project. This tests are using XUnit, however, you can ask to generate tests using another Unit Test library with a command like this one `/tests 使用 MSTests 進行單元測試`.

***Important:** We are not going to use the test file in this project. You must delete the generated test file to continue.*

Finally, let's use the `/doc` to generate automatic documentation to the code. Select lines 39-42, press `CTRL + I` to open the inline chat, and type `/doc` (or select the command) to generate the documentation for this record.

![Use slash command to generate the documentation for a piece of code](../../../06-Using-GitHub-Copilot-with-CSharp/013SlashCmdDoc.gif)

Inline chat, the Chat Panel, and slash commands are part of the amazing tools that support our development experience with GitHub Copilot. Now we are ready to add new features to this App.


### 🗒️ Step 3: Generate a new Record that includes the city name

Go to the `Program.cs` file in the BackEnd project. The file is in the following path `SampleApp\BackEnd\Program.cs`。 

![在後端項目中打開 program.cs](../../../06-Using-GitHub-Copilot-with-CSharp/011OpenBackEndProject.png)

導航到文件末尾，並要求 Copilot 生成一個新記錄，包含城市名稱。

```csharp
// create a new internal record named WeatherForecastByCity that request the following parameters: City, Date, TemperatureC, Summary
```

生成的代碼應該類似於這個：

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

***重要：** 您必須將代碼放在 '.WithOpenApi();' 行之後，這從第 36 行開始。還要記得在每一行新建議的代碼中按 TAB，直到整個端點定義完成。*

接下來，通過添加註釋來使用 GitHub Copilot 生成一個新端點：

```csharp
// Create a new endpoint named /WeatherForecastByCity/{city}, that accepts a city name in the urls as a paremeter and generates a random forecast for that city
```
在接下來的示例中，我們在前一個端點之後添加了一些額外的空行，然後 GitHub Copilot 生成了新的端點。一旦端點的核心代碼生成後，GitHub Copilot 也建議了端點的名稱（第 49 行）和 OpenAPI 規範（第 50 行）。記得按 [TAB] 接受這些建議。

![Copilot 幽靈建議的新端點](../../../06-Using-GitHub-Copilot-with-CSharp/020GeneratedCode.gif)

***重要：** 此提示生成多行 C# 代碼。強烈建議檢查和審核生成的代碼，以確保其按預期工作。*

生成的代碼應類似於這個：

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

現在按運行，項目應該會構建並運行。項目運行後，我們可以使用您的 Codespace 網址和原始端點測試原始網址：

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

🚀 恭喜您，通過這個練習，您不僅使用 GitHub Copilot 生成了代碼，還以互動和有趣的方式完成了它！您可以使用 GitHub Copilot 不僅生成代碼，還撰寫文檔、測試應用程序等。

## 法律聲明

微軟及任何貢獻者授予您在此儲存庫中使用微軟文檔及其他內容的許可，根據 [創用 CC 姓名標示 4.0 國際公共授權](https://creativecommons.org/licenses/by/4.0/legalcode)，詳情請參見 [LICENSE](../../../06-Using-GitHub-Copilot-with-CSharp/LICENSE) 文件，並授予您對儲存庫中任何代碼的許可，根據 [MIT 許可證](https://opensource.org/licenses/MIT)，詳情請參見 [LICENSE-CODE](../../../06-Using-GitHub-Copilot-with-CSharp/LICENSE-CODE) 文件。

微軟、Windows、Microsoft Azure 和/或其他微軟產品及服務在文檔中提及的名稱可能是微軟在美國和/或其他國家的商標或註冊商標。
本項目的許可不授予您使用任何微軟名稱、標誌或商標的權利。
微軟的一般商標指南可在 http://go.microsoft.com/fwlink/?LinkID=254653 上找到。

隱私信息可在 https://privacy.microsoft.com/en-us/ 查找。

微軟及任何貢獻者保留所有其他權利，無論是根據其各自的版權、專利或商標，無論是隱含的、禁反言的還是其他方式。

**免責聲明**：
本文件是使用基於機器的人工智慧翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議進行專業人工翻譯。我們不對因使用此翻譯而產生的任何誤解或誤譯負責。