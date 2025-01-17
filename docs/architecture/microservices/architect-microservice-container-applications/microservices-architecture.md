---
title: 微服務架構
description: .NET 微服務：容器化 .NET 應用程式的架構 | 微服務架構的 30.000 英呎視圖。
ms.date: 09/20/2018
ms.openlocfilehash: d1c58d218be9e5f8c0ae8ae732f9bdd06674a2c2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834390"
---
# <a name="microservices-architecture"></a>微服務架構

如名稱所指，微服務架構是將伺服器應用程式建置為一組小型服務的方法。 這表示微服務架構主要是導向至後端 (儘管此方法也會用於前端)。 每個服務會在自己的處理序中執行，並使用 HTTP/HTTPS、WebSocket 或 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) 等通訊協定與其他處理序通訊。 每個微服務都會在特定內容界限內實作特定端對端領域或商務功能，而且每個微服務都必須自主開發並可獨立部署。 最後，每個微服務都應該擁有其相關的領域資料模型和領域邏輯 (主權和非集中式資料管理)，而且可以根據不同的資料儲存技術 (SQL、NoSQL) 及不同的程式設計語言。

微服務的大小應該為何？ 開發微服務時，大小不應該是重點。 相反地，重點應該是建立鬆散結合的服務，以便每個服務都能自主開發、部署及擴充。 當然，識別及設計微服務時，只要與其他微服務沒有太多直接相依性，都應該嘗試使其越小越好。 比微服務大小更重要的是，它必須有內部凝聚力，而且獨立於其他服務。

為什麼選擇微服務架構？ 簡單來說，它提供長期靈活度。 微服務可讓您建立以許多可獨立部署之服務為基礎的應用程式，而且每個服務會有細微且自主的生命週期，藉此提高複雜、大型且可高度擴充之系統的管理能力。

另一個優點是微服務可以獨立擴充。 您不需要具有必須以單位擴充的單一整合型應用程式，您可以改為擴充特定微服務。 這樣一來，您就可以只調整需要更多處理能力或網路頻寬的功能區域來支援需求，而不是擴充不需要調整的其他應用程式區域。 由於需要較少的硬體，因此會為您節省成本。

![這兩種部署方法之間差異的圖表。](./media/microservices-architecture/monolith-deployment-vs-microservice-approach.png)

**圖 4-6**： 整合型部署與微服務方法

如圖4-6 所示，在傳統的整合型方法中，應用程式會在多個伺服器/VM 中複製整個應用程式來進行調整。 在微服務方法中，會以較小的服務隔離功能，因此每個服務都可以獨立調整。 微服務方法可讓您針對每個微服務進行 agile 變更和快速反復專案，因為您可以變更複雜、大型且可擴充的應用程式的特定小型區域。

架構更細緻的微服務架構應用程式可進行持續整合與持續傳遞實務。 它也會加速將新功能傳遞到應用程式中。 應用程式的更細緻組合也可讓您隔離執行及測試微服務，以及自主發展微服務，同時確保這些服務之間有清楚的合約。 只要您未變更介面或合約，您就可以變更任何微服務的內部實作或新增功能，而不會中斷其他微服務。

以下是使用微服務架構系統成功進入生產環境的重點：

- 服務和基礎結構的監視和健康情況檢查。

- 服務 (也就是雲端和協調器) 的可擴充基礎結構。

- 多個層級的安全性設計和實作：驗證、授權、秘密管理、安全通訊等等。

- 快速傳遞應用程式，通常有不同的小組著重於不同的微服務。

- DevOps 與 CI/CD 的實務和基礎結構。

本指南只會涵蓋或介紹其中的前三點。 最後兩點與應用程式生命週期相關，其他電子書 [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) (利用 Microsoft 平台和工具的容器化 Docker 應用程式生命週期) 中會提供說明。

## <a name="additional-resources"></a>其他資源

- **Mark Russinovich：Microservices:An application revolution powered by the cloud (微服務：採用雲端技術的應用程式變革)**  \
  <https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/>

- **Martin Fowler：微服務** \
  <https://www.martinfowler.com/articles/microservices.html>

- **Martin Fowler：微服務先決條件** \
  <https://martinfowler.com/bliki/MicroservicePrerequisites.html>

- **Jimmy Nilsson：區塊雲端運算** \
  <https://www.infoq.com/articles/CCC-Jimmy-Nilsson>

- **Cesar de la Torre：Microsoft 平台和工具的容器化 Docker 應用程式生命週期** (可下載的電子書) \
  <https://aka.ms/dockerlifecycleebook>

>[!div class="step-by-step"]
>[上一頁](service-oriented-architecture.md)
>[下一頁](data-sovereignty-per-microservice.md)
