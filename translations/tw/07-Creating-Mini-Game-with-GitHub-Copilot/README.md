- **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員。
- **學習內容**：利用 GitHub Copilot 來生成代碼並為您的工作添加註釋。
- **建構內容**：將生成由 Copilot AI 提供的代碼和註釋建構的 Python 檔案。
- **前置條件**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)。
- **時間**：本課程可在一小時內完成。

在這個模組結束時，您將獲得以下技能：

- 體驗 GitHub Codespaces 作為開發環境。
- 在 Python 控制台應用程式中開發輸入和輸出例程。
- 將 GitHub Copilot 作為助手使用。

## 前置閱讀：
- [使用 GitHub Copilot 的提示工程簡介](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [挑戰專案 - 使用 GitHub Copilot 和 Python 建立迷你遊戲](https://learn.microsoft.com/training/modules/challenge-project-create-mini-game-with-copilot/?WT.mc_id=academic-113596-abartolo)
- 實時學習：使用 GitHub Copilot 建立迷你遊戲控制台應用程式（視頻如下）
- [![實時學習：使用 GitHub Copilot 建立迷你遊戲控制台應用程式](https://i.ytimg.com/vi/Fi_jl3G7i8Y/maxresdefault.jpg)](https://youtu.be/Fi_jl3G7i8Y?si=v56VPYfTHYBBEX11)
  （點擊上面的圖片觀看本課的視頻）
  

## 要求

- 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)

## 💪🏽 練習

**右鍵單擊 "在 GitHub Codespaces 中打開" 按鈕以在新標籤中打開您的 Codespace**
 
[![在 GitHub Codespaces 中打開](https://github.com/codespaces/badge.svg)](https://codespaces.new/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming)

您已經對 GitHub Codespaces 和 GitHub Copilot 有了一些了解以及它們的工作原理。在這個挑戰練習中，您的目標是使用 GitHub Copilot 開發一個 Python 迷你遊戲。

#### 測試您的 GitHub Codespace

1. 訪問您的 Codespaces 並在 Visual Studio Code 中創建一個名為 *app.py* 的新檔案。

   **注意：** 如果尚未安裝，您可能需要在 Visual Studio Code 中安裝 Python 擴展。

2. 輸入以下註釋：

   ```python
   # write 'hello world' to the console
   ```
      
3. GitHub Copilot 應該會為您完成代碼並提供以下結果：

   ```python
   # write 'hello world' to the console
   print('hello world')
   ```

4. 在終端中運行應用程式，使用 *python app.py* 命令，檢查結果是否類似於以下控制台消息：

   ```bash
   hello world
   ```
   
### 創建遊戲邏輯

現在您已經驗證了 Codespaces 與 GitHub Copilot 的運作，您的下一步是根據以下規範開發 Python 迷你遊戲的邏輯：

遊戲的獲勝者由三個簡單的規則決定：

- **石頭** 打贏剪刀。
- **剪刀** 打贏紙。
- **紙** 打贏石頭。

#### 遊戲互動考量

電腦將是您的對手，可以隨機選擇其中一個元素（**石頭**、**紙**或**剪刀**）。您的遊戲互動將通過控制台（終端）進行。

- 玩家可以選擇三個選項中的一個，即石頭、紙或剪刀，並應在輸入無效選項時受到警告。
- 在每一回合中，玩家必須輸入列表中的一個選項，並被告知自己是贏了、輸了還是與對手平局。
- 在每一回合結束時，玩家可以選擇是否再次遊玩。
- 在遊戲結束時顯示玩家的得分。
- 迷你遊戲必須處理用戶輸入，將其轉換為小寫，並告知用戶選項是否無效。

在您的 GitHub Codespaces 中，按照給定的指示設置提示，以便 GitHub Copilot 可以理解並使用它們來幫助您構建迷你遊戲。請記住，GitHub Copilot 依賴於註釋來掌握上下文，並在您進行項目時提供有用的建議。

#### 驗證您的工作

1. 在控制台中運行迷你遊戲，使用 *python app.py* 命令。
2. 在提示中，輸入一個遊戲選項：*石頭*、*紙* 或 *剪刀*。
3. 迷你遊戲應告知玩家該玩家是贏了、輸了還是與對手平局。
4. 選擇繼續遊玩。
5. 在提示中，輸入 *screen*。
6. 迷你遊戲應告知玩家所輸入的選項是否無效。
7. 重複步驟 2 和 4 進行幾輪遊玩，並選擇不再繼續。
8. 檢查迷你遊戲是否終止，並顯示您的得分，告知您贏得的次數和回合數。

恭喜您完成這個挑戰練習！您已經使用 GitHub Copilot 創建了一個 Python 控制台迷你遊戲。

**免責聲明**：  
本文件是使用機器翻譯的人工智慧翻譯服務進行翻譯的。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人工翻譯。我們對於因使用本翻譯而產生的任何誤解或誤譯不承擔責任。