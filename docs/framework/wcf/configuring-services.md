---
title: 設定 WCF 服務
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 4fcf01c9f65f2b1bd11462a6f7d61b3551f37b86
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320654"
---
# <a name="configuring-wcf-services"></a>設定 WCF 服務

在設計並實作您的服務合約之後，就可開始設定您的服務。 您可在此處定義及自訂向用戶端公開服務的方式，包括指定所在的位址、用於傳送及接收訊息的傳輸和訊息編碼，以及所需要的安全性類型。  
  
 此處所使用的組態包括所有的方法，如命令式程式碼或使用組態檔，您可以在其中定義及自訂服務的各方面，例如指定端點位址、使用的傳輸以及安全性配置。 實際上，撰寫設定是 WCF 應用程式設計的主要部分。  
  
## <a name="in-this-section"></a>本章節內容  
 [簡化設定](simplified-configuration.md)  
 從 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] 開始，WCF 會隨附新的預設設定模型，以簡化 WCF 設定需求。 如果您未提供特定服務的任何 WCF 設定，執行時間會自動以預設端點、系結和行為來設定您的服務。  
  
 [使用設定檔設定服務](configuring-services-using-configuration-files.md)  
 Windows Communication Foundation （WCF）服務可使用 .NET Framework 設定技術來設定。 最常見的情況是，XML 元素會加入至裝載 WCF 服務的 Internet Information Services （IIS）網站的 web.config 檔案中。 這些項目允許您變更詳細資料，例如各電腦的端點位址 (用於與服務通訊的實際位址)。  
  
 [繫結](bindings.md)  
 此外，WCF 包含數種系統提供的一般設定，其形式為系結，可讓您快速選取用戶端和服務如何通訊的最基本功能，例如所使用的傳輸、安全性和訊息編碼。  
  
 [端點](endpoints.md)  
 所有與 WCF 服務的通訊都是透過服務的*端點*進行。 端點包含合約、在繫結中指定的組態資訊，以及指出何處可找到服務或何處可取得有關服務之資訊的位址。  
  
 [保護服務安全](securing-services.md)  
 使用 WCF 和現有的安全性機制，您可以在任何服務中實施機密性、完整性、驗證和授權。 您也可以稽核安全性成功和失敗。  
  
 [建立 WS-I Basic Profile 1.1 交互操作服務](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 在 WS-I Basic Profile 1.1 規格中略述了部署與其他平台或作業系統上的服務和用戶端互通之服務的需求。  
  
## <a name="reference"></a>參考資料  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>相關章節  
 [基本程式設計週期](basic-programming-lifecycle.md)  
  
 [設計與實作服務](designing-and-implementing-services.md)  
  
 [裝載服務](hosting-services.md)  
  
 [建置用戶端](building-clients.md)  
  
 [擴充性簡介](introduction-to-extensibility.md)  
  
 [管理與診斷](./diagnostics/index.md)  
  
## <a name="see-also"></a>請參閱

- [基本 WCF 程式設計](basic-wcf-programming.md)
- [概念性概觀](conceptual-overview.md)
- [WCF 功能詳細資料](./feature-details/index.md)
