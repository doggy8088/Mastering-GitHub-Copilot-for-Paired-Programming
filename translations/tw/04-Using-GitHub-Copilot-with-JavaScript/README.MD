<header>

# 使用 GitHub Copilot 開發 JavaScript

在這個模組中，我們將探索 GitHub Copilot 強大的功能，並了解它如何改變您的程式設計體驗。想像一下能更有效率地撰寫程式碼，事半功倍 —GitHub Copilot 透過分析您的註解和程式碼內容，將這個願景變成現實。

作為一位想提升生產力的開發者，您將深入掌握 GitHub Copilot，特別著重在 JavaScript 的應用。在完成本模組後，您將具備在 Visual Studio Code 中使用 GitHub Copilot 外掛產生有價值建議的技巧。您將增強一個 JavaScript 專案，體驗這個 AI 驅動的工具如何提供自動完成式建議，簡化您的開發流程。

掌握 GitHub Copilot 不僅止於程式碼協助 — 您還將學習如何在 Codespaces 中設定儲存庫，並運用這個 AI 工具來優化您的專案。準備好革新您的工作流程，提升程式設計技能，在這個充滿活力的學習旅程中開啟新的生產力層次！

</header>

* **適合對象**: 開發者、DevOps 工程師、軟體開發經理、測試人員
* **學習內容**: 使用 GitHub Copilot 建立程式碼並為您的工作加入註解
* **將會建立**: 由 Copilot AI 產生程式碼和註解建議的 Javascript 檔案
* **先決條件**: GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)
* **所需時間**: 本模組可在一小時內完成

完成本模組後，您將具備以下能力：

* 撰寫提示來產生 GitHub Copilot 建議
* 運用 GitHub Copilot 改進您的專案

## 前置閱讀：

* [GitHub Copilot 提示工程入門](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
* [使用 GitHub Copilot 開發 JavaScript](https://learn.microsoft.com/training/modules/introduction-copilot-javascript/?WT.mc_id=academic-113596-abartolo)

## 需求

1. 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)
2. 使用 [Codespaces 開啟此儲存庫](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-javascript?quickstart=1)

## 💪🏽 練習

**右鍵點擊以下 Codespaces 按鈕以在新標籤頁中開啟您的 Codespace**

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true\&ref=main\&repo=526682619)

在這個範本作品集中，我們有一個基於 React 的網頁應用程式，您可以輕鬆地自訂和部署，只需使用您的網頁瀏覽器。

**注意**: 請忽略 GitHub Codespace 中給出的指示。對於這個練習，請務必遵循此處的指示。

### 🛠 步驟 1: 自訂網頁應用程式

使用您自己的連結來自訂作品集。前往 `src/App.jsx` 並更新 `siteProps` 以包含您的資訊。`siteProps` 變數是一個 JavaScript 物件，包含用於自訂網站的鍵值對，它應該看起來像這樣：

```javascript
const siteProps = {
  name: "Alexandrie Grenier",
  title: "Web Designer & Content Creator",
  email: "alex@example.com",
  gitHub: "microsoft",
  instagram: "microsoft",
  linkedIn: "satyanadella",
  medium: "",
  twitter: "microsoft",
  youTube: "Code",
};
```

### 📖 步驟 2: 解釋程式碼

現在讓我們使用斜線命令來解釋程式碼的一部分。高亮以下程式碼：

```javascript
};

const primaryColor = "#4E567E";
const secondaryColor = "#D2F1E4";

const App = () => {
  return (
    <div id="main">
      <Header />
      <Home name={siteProps.name} title={siteProps.title} />
      <About />
      <Portfolio />
      <Footer {...siteProps} primaryColor={primaryColor} secondaryColor={secondaryColor} />
    </div>
  );
};
```

高亮後，按下 Ctrl + I (Windows) 或 Cmd + I (Mac) 並輸入 **/explain**。您應該會在 Copilot Chat 視窗中收到類似以下的回應：

```
這段 JavaScript 程式碼是用 React 撰寫的，React 是一個流行的用於構建使用者介面的庫。這段程式碼定義了一個名為 App 的函數元件。App 元件是您的應用程式的根元件。它是所有其他元件(Header、Home、About、Portfolio、Footer)被調用和渲染的地方。App 元件返回一個 JSX(JavaScript XML)結構，看起來類似於 HTML。這個 JSX 結構定義了 App 元件應該在螢幕上渲染的內容。在 JSX 中，有一個 id 為 "main" 的 div。在這個 div 中，有幾個元件被渲染：Header、Home、About、Portfolio 和 Footer。Home 元件被傳遞了兩個 props：name 和 title，這兩個都是 siteProps 物件的屬性。Footer 元件被傳遞了幾個 props。...siteProps 語法使用 JavaScript 展開運算符將 siteProps 的所有屬性作為單獨的 props 傳遞。除了 siteProps，還傳遞了兩個 props：primaryColor 和 secondaryColor。這些在檔案的頂部定義為常數。記住，React 中的 props(屬性的簡稱)是元件之間如何通信的。如果您將元件視為函數，那麼 props 就是這些函數的參數。它們從父元件(在這種情況下是 App)傳遞到子元件(Header、Home、About、Portfolio、Footer)。
```

讓我們深入一點。注意 Copilot Chat 現在提供了一個後續問題建議供您詢問。點擊 GitHub Copilot 在視窗底部提供的建議問題，通常以 "What is the purpose..." 開頭，並查看提供的答案。例如，如果 GitHub Copilot 提供的問題如下：

What is the purpose of using props in React components?

您應該會得到類似以下的答案：

```
React 中的 props(屬性的簡稱)用於從一個元件傳遞資料到另一個元件，就像函數參數一樣。它們是唯讀的，有助於使元件可重用和動態化。例如，在您的程式碼中，Home 元件被傳遞了 name 和 title 作為 props。這意味著 Home 元件可以使用這些值來顯示動態內容。Footer 元件也被傳遞了幾個 props，包括 siteProps 的所有屬性以及 primaryColor 和 secondaryColor 常數。這裡有一個類比：將元件視為自訂的 HTML 元素，將 props 視為該元素的屬性。就像您可以將不同的屬性傳遞給 HTML 元素(例如 <img src="image.jpg" alt="An image">)，您可以將不同的 props 傳遞給 React 元件(例如 <Home name="John" title="Developer" />)。這使您的元件更加靈活和可重用。例如，您可以使用相同的 Home 元件與不同的 props 來顯示不同的內容。
```

您是否注意到在 Copilot Chat 視窗中點擊建議問題後，它使用了類似以下的命令來詢問問題：

```
@workspace /explain What is the purpose of using props in React components?
```

@workspace 代理與 Copilot 一樣，填補了缺失的細節，幫助人們在忽略或未完全描述所見內容時。當被提示時，Copilot 採取不同的方法。它不會立即回應，而是首先分步檢查工作區中的檔案和資料夾：

1. 它檢查檔案 / 資料夾的名稱以查看哪些可能相關。
2. 它閱讀檔案的內容，有時是全部，有時是部分，因為記憶體限制。
3. 它從收集的資訊中建立上下文。
4. 它回應，使用提示的上下文和它收集的資訊。

### 🔎 步驟 3: 使用提示為社交媒體圖示添加動畫

動畫可以使社交媒體部分更加引人注目。請求 Copilot 的幫助來為圖示添加動畫。跳到檔案末尾，並在 `src/styles.css` 檔案中寫下以下提示：

```css
/* add an amazing animation to the social icons */
```

Copilot 的建議應該類似於以下內容：

```css
img.socialIcon:hover {
  animation: bounce 0.5s;
  animation-iteration-count: infinite;
}

@keyframes bounce {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
```

### 🚀 步驟 4: 瞭解如何運行應用程式

點擊左側邊欄的聊天圖示以開啟 GitHub Copilot 聊天，並使用輸入區域詢問以下問題：

```
@workspace I want to understand how can I run this React application
```

提示使用 `@workspace`，這是 GitHub Copilot 聊天的一個特殊功能，允許您包含更多上下文以獲得更完整的答案。嘗試使用聊天面板進行其他查詢，以獲得更互動的工作流程。

### 結論

您的網站應該已經在您的 Codespace 中運行，並且更改將自動重新加載到頁面上。要查看它們，將滑鼠懸停在頁腳中的一個社交媒體圖示上以查看效果！

**注意**: 如果懸停效果不起作用，請刷新 Codespace 瀏覽器視窗。

恭喜您，通過這個練習，您已經使用 GitHub Copilot 生成程式碼，並且以互動和有趣的方式完成了它！您可以使用 GitHub Copilot 不僅生成程式碼，還可以撰寫文檔、測試應用程式等等。
