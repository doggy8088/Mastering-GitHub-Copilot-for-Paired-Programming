# 取得關於 Azure 服務與資源的解答

如果您不太熟悉 Azure 及其在應用程式中的應用方式，您可以向 GitHub Copilot for Azure Preview 尋求協助。將此實驗室視為一本「自己決定冒險」小說。探索以下多個提示，並根據您認為需要 @azure 擴充功能所執行的功能來嘗試建立自己的提示。

## 最佳實務

使用助手可以透過回答問題、執行任務和產生程式碼來提升開發者的生產力。然而，請謹記以下重要規則：

- 檢查所有 AI 產生的回應。在根據這些回應採取行動之前，驗證其正確性、適用性和潛在結果（例如成本和安全性）。
- 切勿將應用程式的密鑰或憑證儲存在原始程式碼中。
- 在提問時，切勿在問題或程式碼中提交應用程式的密鑰或憑證。

當您使用基於大型語言模型的任何工具時，請使用良好的提示工程技術以獲得最佳結果。以下提示來自文章 [為 Microsoft Copilot 在 Azure 中撰寫有效提示](https://learn.microsoft.com/azure/copilot/write-effective-prompts)，該文章提供了在 Azure 背景下進行提示工程的建議。

- 清晰具體
- 設定期望
- 添加有關您情境的上下文
- 拆分您的請求
- 自定義您的程式碼
- 使用 Azure 專有術語
- 使用反饋循環

## 使用 GitHub Copilot for Azure 瞭解 Azure 服務

在此練習中，我們將使用 GitHub Copilot for Azure Preview 瞭解如何在應用程式中使用 Azure，我們將從開放式問題或請求開始。然後，添加具體的服務和技術細節以獲得更好的結果。嘗試以下示例提示。

## 瞭解 Azure 上的系統架構

1. "@azure 如何在 Azure 中建立高可用性架構？"
1. "@azure 解釋 Azure Well-Architected Framework。"
1. "@azure Azure 有哪些類型的應用託管解決方案？"
1. "@azure 幫助我協調和自動化我的數據處理工作流程。"
1. "@azure 如何將 SignalR 與 Azure Application Gateway 和 Azure API Management 集成？"
1. "@azure 您推薦多少單位？"
1. "@azure 使用 Terraform 有哪些好處和應用？"

## 瞭解 Azure 上的 AI

8. "@azure 我想建構一個 AI 應用程式。我可以使用哪些服務？"

## 瞭解 Azure 上的網站和應用託管

9. "@azure 哪個 Azure 服務最適合託管可擴展的網頁應用？"
1. "@azure 我應該使用哪個服務來建立網站？"
1. "@azure 如何使用 Azure 建構可擴展的網頁應用？"
1. "@azure 在什麼情境下 Azure Functions 比 Web Apps 更好？"

## 瞭解 Azure 上的容器

- "@azure Azure 支持哪些類型的容器化應用？"
- "@azure 在 Azure 中管理容器的選擇有哪些？"
- "@azure 何時應使用 Azure Kubernetes Service 而不是 Azure Container Apps？"
- "@azure Azure Container Apps 和 AKS 之間有什麼區別？"
- "@azure 為什麼我會選擇 Azure Container Apps 而不是 AKS？"

### 瞭解如何為您的應用使用 Azure 服務

|服務或技術|學習提示示例|
|---|---|
|Azure AI Search|<ul><li>"@azure Azure AI Search 是什麼，我為什麼要使用它？"</li><li>"@azure Azure AI Search 的定價是如何運作的？"</li><li>"@azure Azure AI Search 如何與 Azure OpenAI 集成？"</li><li>"@azure Azure AI Search 如何與 Azure Machine Learning 集成？"</li><li>"@azure 何時應使用混合搜索或向量搜索，而不是 Azure AI Search 中的語義排名？"</li><li>"@azure Azure AI Search 是向量數據庫嗎？Azure AI Search 如何確保向量搜索結果的準確性和相關性？"</li><li>"@azure 您對 Azure AI Search 中高規模多租戶應用的支持是什麼？"</li><li>"@azure Azure AI Search 中的集成向量化功能是什麼？我可以從哪些數據源提取數據並使用集成向量化？"</li><li>"@azure Azure AI Search 中的 AI 增強是什麼？AI 增強是如何工作的？使用 AI 增強有哪些好處？"</li><li>"@azure Azure AI Search 中的語義排名器是什麼？它與向量搜索有何不同？"</li><li>"@azure Azure AI Search 的最佳推薦程式碼示例或解決方案加速器有哪些？"</li><li>"@azure 使用 Azure AI Search 的企業有哪些實際案例？"</li></ul>|
|Azure API Management|<ul><li>"@azure Azure API Management 的好處和應用是什麼？"</li></ul>|
|Azure App Service|<ul><li>"@azure 我如何在 Azure 中部署網頁應用？"</li><li>"@azure 我如何建立 App Service 應用並使用 CLI 將程式碼部署到暫存環境？"</li><li>"@azure 建立一個腳本來部署將在 Python 中運行的網頁應用。"</li><li>"@azure Azure 有哪些數據庫選項可用於網頁應用？"</li><li>"@azure Azure 有哪些無伺服器選項可用於網頁應用？"</li><li>"@azure 建立一個最大化 Azure App Service 的指南。"</li></ul>|
|Azure Cache for Redis|<ul><li>"@azure 演示如何在 Azure 中配置 Redis 緩存以實現高可用性和災難恢復。"</li></ul>|
|Azure Container Apps|<ul><li>"@azure Azure Container Apps 服務是什麼？"</li><li>"@azure 告訴我容器應用和容器應用環境之間的區別。"</li></ul>|
|Azure Cosmos DB|<ul><li>"@azure 為什麼我會選擇 Azure Cosmos DB 而不是 Azure SQL？"</li><li>"@azure 我想使用 Azure Cosmos DB 來存儲我的數據。"</li><li>"@azure 為什麼我會選擇 Azure Cosmos DB 帳戶而不是 SQL 數據庫？"</li></ul>|
|Azure Data Factory|<ul><li>"@azure 我如何使用 Azure Data Factory 建立數據管道？"</li></ul>|
|Azure Developer CLI (`azd`)|<ul><li>"@azure 您是否有 Azure 的示例部署模型？SaaS、PaaS 等等。"</li><li>"@azure 我應該為我的應用選擇什麼樣的基礎設施？"</li><li>"@azure 我如何設置我的 Azure 環境？"</li><li>"@azure Azure Resource Manager 模板是什麼，我該如何使用它們？"</li><li>"@azure 我如何使用 Azure Developer CLI 管理環境？"</li><li>"@azure Azure Developer CLI 是什麼？"</li><li>"@azure Bicep 和 ARM 模板之間有什麼區別？"</li><li>"@azure 我如何確保我的環境具有最佳的安全模式？"</li><li>"@azure 我如何使用 CI/CD 管道進行部署？"</li></ul>|
|Azure Functions|<ul><li>"@azure 我如何建立一個新的 Azure 函數？"</li><li>"@azure Azure Functions 和 Azure Logic Apps 之間有什麼區別？"</li><li>"@azure 建立一個將 Azure Logic Apps 與 Azure Functions 集成的指南。"</li><li>"@azure 我想在 Node.js 中建立一個 Azure 函數。"</li></ul>|
|Azure Key Vault|<ul><li>"@azure 解釋我為什麼以及如何使用 Azure 密鑰保管庫。"</li></ul>|
|Azure Kubernetes Service (AKS)|<ul><li>"@azure 我如何獲取 AKS 叢集中的所有節點狀態？"</li><li>"@azure 設置我的 AKS 叢集上下文的命令是什麼？"</li></ul>|
|Azure Machine Learning|<ul><li>"@azure 生成一個 PowerShell 腳本來建立一個新的 Azure Machine Learning 工作區。"</li><li>"@azure Azure AI 服務和 Azure Machine Learning 之間有什麼區別？"</li></ul>|
|Azure Monitor|<ul><li>"@azure 建立一個使用 Azure Logic Apps 自動化對 Azure Monitor 警報響應的指南。"</li></ul>|
|Azure Virtual Network|<ul><li>"@azure 我如何平衡進入應用的網絡流量？"</li></ul>|
|Azure OpenAI Service|<ul><li>"@azure Azure OpenAI 提供哪些服務？"</li><li>"@azure GPT-4o mini 在哪裡可用？"</li><li>"@azure 集成 Azure OpenAI 的先決條件是什麼？"</li><li>"@azure 建立一個建立和使用 Azure OpenAI 資源的指南。"</li><li>"@azure 有哪些可用的 Azure OpenAI 模型類型？"</li></ul>|
|Azure SDK|<ul><li>"@azure 我可以在瀏覽器中使用 Azure SDK 嗎？"</li><li>"@azure C# 存儲 SDK 是否支持分塊 blob 上傳和下載？"</li></ul>|
|Azure SignalR Service|<ul><li>"@azure 我如何在多個伺服器上託管和擴展 SignalR？"</li><li>"@azure 我如何在 .NET 中進行實時通信？"</li><li>"@azure 我如何將實時更新推送到客戶端？"</li><li>"@azure 我如何在客戶端之間同步數據？"</li><li>"@azure 我如何將數據流式傳輸到客戶端？"</li><li>"@azure 我如何管理和擴展 WebSocket 連接？"</li><li>"@azure 我如何託管和擴展 Socket.IO？"</li><li>"@azure 我需要做什麼來配置我的 SignalR 程式碼以與 Azure SignalR Service 一起使用？"</li><li>"@azure 評估我對 SignalR 的使用。是否遵循最佳安全實踐？"</li><li>"@azure 我如何對 SignalR 進行壓力測試？"</li><li>"@azure 我如何配置 Azure SignalR Service 中的網絡？"</li><li>"@azure 我如何配置 Azure Web PubSub 事件處理程序？"</li>|
|Azure SQL|<ul><li>"@azure 建立一個 Terraform 配置以部署 Azure SQL 數據庫。"</li><li>"@azure 設計一個將本地 SQL Server 數據庫遷移到 Azure SQL Managed Instance 的策略。"</li></ul>|
|Azure Static Web Apps|<ul><li>"@azure 靜態網頁應用是否支持靜態 IP 地址？"</li></ul>|
|Azure Storage|<ul><li>"@azure 為什麼我會使用 blob 存儲？"</li><li>"@azure 我如何在 React 中從存儲 blob 中提取數據？"</li><li>"@azure 概述使用私有端點和 Azure Private Link 來保護 Azure Blob Storage 的步驟。"</li><li>"@azure 生成一個 Azure CLI 腳本來建立一個新的存儲帳戶。"</li><li>"@azure 給我程式碼以使用 CLI 建立新的存儲帳戶。"</li><li>"@azure 您能幫我選擇合適的 Azure 存儲解決方案嗎？"</li></ul>|
|Azure Web PubSub|<ul><li>"@azure 我如何使用 Web PubSub 進行身份驗證？"</li><li>"@azure 我需要做什麼才能在 Azure 上託管我的 Socket.IO 應用？"</li><li>"@azure 我如何對 Web PubSub 進行壓力測試？"</li></ul>|
