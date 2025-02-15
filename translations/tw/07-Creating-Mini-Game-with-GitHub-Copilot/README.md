* **適合對象**：開發者、DevOps 工程師、軟體開發經理、測試人員
* **學習內容**：運用 GitHub Copilot 產生程式碼並加入註解
* **建構內容**：使用 Copilot AI 協助建構 Python 檔案，包含程式碼和註解
* **前置需求**：GitHub Copilot 可免費使用，請註冊 [GitHub Copilot](https://gh.io/copilot)
* **所需時間**：約一小時

完成此模組後，您將具備以下能力：

* 熟悉使用 GitHub Codespaces 作為開發環境
* 在 Python 主控台應用程式中開發輸入和輸出程序
* 善用 GitHub Copilot 作為輔助工具

## 前置閱讀：

* [GitHub Copilot 提示工程入門](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
* [實作專案 - 使用 GitHub Copilot 和 Python 開發迷你遊戲](https://learn.microsoft.com/training/modules/challenge-project-create-mini-game-with-copilot/?WT.mc_id=academic-113596-abartolo)
* 即時課程：使用 GitHub Copilot 開發迷你遊戲主控台應用程式（影片如下）
* [![即時課程：使用 GitHub Copilot 開發迷你遊戲主控台應用程式](https://i.ytimg.com/vi/Fi_jl3G7i8Y/maxresdefault.jpg)](https://youtu.be/Fi_jl3G7i8Y?si=v56VPYfTHYBBEX11)
  （點擊上方圖片觀看課程影片）

## 需求

* 啟用您的 [GitHub Copilot 服務](https://github.com/github-copilot/signup)

## 💪🏽 實作練習

**在新分頁中開啟您的 Codespace，請右鍵點選「在 GitHub Codespaces 中開啟」按鈕**

[![在 GitHub Codespaces 中開啟](https://github.com/codespaces/badge.svg)](https://codespaces.new/microsoft/Mastering-GitHub-Copilot-for-Paired-Programming)

您已經對 GitHub Codespaces 和 GitHub Copilot 有基本認識。在這個挑戰練習中，您將使用 GitHub Copilot 開發一個 Python 迷你遊戲。

#### 測試您的 GitHub Codespace

1. 進入您的 Codespace 並在 Visual Studio Code 中建立名為 _app.py_ 的新檔案

   **注意**：若尚未安裝，您可能需要在 Visual Studio Code 中安裝 Python 擴充功能

2. 輸入以下註解：

   ```python
   # 在主控台輸出 'hello world'
   ```

3. GitHub Copilot 應該會完成程式碼如下：

   ```python
   # 在主控台輸出 'hello world'
   print('hello world')
   ```

4. 在終端機中執行應用程式，使用 _python app.py_ 指令，確認輸出結果如下：

   ```bash
   hello world
   ```

### 建立遊戲邏輯

確認 Codespaces 和 GitHub Copilot 可正常運作後，接下來依照以下規則開發 Python 迷你遊戲：

遊戲勝負判定規則：

* **石頭**贏過剪刀
* **剪刀**贏過紙
* **紙**贏過石頭

#### 遊戲互動設計

電腦作為對手會隨機選擇其中一個選項（**石頭**、**紙**或**剪刀**）。遊戲互動透過主控台（終端機）進行。

* 玩家可從三個選項中擇一：石頭、紙或剪刀，輸入無效選項時會收到警告
* 每回合玩家需輸入選項，系統會告知是獲勝、落敗或平手
* 每回合結束可選擇是否繼續遊戲
* 遊戲結束時顯示玩家分數
* 迷你遊戲需處理使用者輸入，轉換為小寫，並於輸入無效時提醒使用者

在您的 GitHub Codespaces 中，依指示設定提示，讓 GitHub Copilot 理解並協助您建構迷你遊戲。請記住，GitHub Copilot 需要透過註解來理解上下文，在開發過程中提供實用建議。

#### 驗證您的成果

1. 在主控台中使用 _python app.py_ 指令執行迷你遊戲
2. 在提示處輸入遊戲選項：_石頭_、_紙_ 或 _剪刀_
3. 迷你遊戲應顯示玩家是獲勝、落敗或平手
4. 選擇繼續遊戲
5. 在提示處輸入 _screen_
6. 迷你遊戲應提示輸入選項無效
7. 重複步驟 2 和 4 進行數回合，然後選擇結束遊戲
8. 確認遊戲結束並顯示您的得分，包含勝場次數和總回合數

恭喜您完成這個挑戰練習！您已使用 GitHub Copilot 成功開發一個 Python 主控台迷你遊戲。
