---
title: 新增 WCF Web Service Reference
description: 新增 .NET Core 和 ASP.NET Core 專案功能的 Microsoft WCF Web Service Reference Provider 工具概觀，與 .NET Framework 專案的「新增服務參考」類似。
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc, seodec18
ms.openlocfilehash: feecf374e1af48f349495c13ea91b810c6b0a1c3
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191906"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a>使用 WCF Web Service Reference Provider 工具

多年來，許多 Visual Studio 開發人員都享受[**新增服務參考**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)工具在其 .NET Framework 專案需要存取 Web 服務時所提供的生產力。  **WCF Web Service Reference** 工具是 Visual Studio 連線服務延伸模組，以針對 .NET Core 和 ASP.NET Core 專案提供「新增服務參考」功能這類體驗。 此工具可從目前方案中的 Web 服務、網路位置或 WSDL 檔案擷取中繼資料，且能產生與 .NET Core 相容的來源檔案，其中包含的 Windows Communication Foundation (WCF) 用戶端 Proxy 程式碼可讓您用於存取 Web 服務。

> [!IMPORTANT]
> 您只應該參考來自信任來源的服務。 新增不信任來源的參考可能會危及安全性。

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2017 15.5 版](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)或更新版本

## <a name="how-to-use-the-extension"></a>如何使用延伸模組

> [!NOTE]
> **WCF Web Service Reference** 選項適用於使用下列專案範本建立的專案：
>
> - **Visual C#**  >  **.NET Core**
> - **Visual C#**  >  **.NET Standard**
> - **Visual C#**  > **Web** > **ASP.NET Core Web 應用程式**

使用 **ASP.NET Core Web 應用程式** 專案範本作為範例，本文會引導您完成將 WCF 服務參考新增至專案：

1. 在方案總管中，按兩下專案的 [已連線的服務] 節點 (針對 .NET Core 或 .NET Standard 專案，在方案總管中，以滑鼠右鍵按一下專案的 [相依性] 節點時，可以使用此選項)。

    [已連線的服務] 頁面隨即顯示 (如下圖所示)：

    ![適用於 .NET Core 的 [Visual Studio 連線服務] 索引標籤](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. 在 [已連線的服務] 頁面上，按一下 [Microsoft WCF Web Service Reference Provider]。 這會啟動 [設定 WCF Web 服務參考精靈]：

    ![適用於 .NET Core 的 [Visual Studio 服務端點] 索引標籤](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. 選取服務。

    3a. [設定 WCF Web 服務參考精靈] 內有數個服務搜尋選項可用：

     * 若要搜尋目前方案中所定義的服務，請按一下 [探索] 按鈕。
     * 若要搜尋所指定位址裝載的服務，請在 [位址] 方塊中輸入服務 URL，然後按一下 [執行] 按鈕。
     * 若要選取包含 Web 服務中繼資料資訊的 WSDL 檔案，請按一下 [瀏覽] 按鈕。

    3b. 在 [服務] 方塊中，從搜尋結果清單中選取服務。 如有需要，請在對應的 [命名空間] 文字方塊中輸入已產生程式碼的命名空間。

    3c. 按一下 [下一步] 按鈕以開啟 [資料類型選項] 和 [用戶端選項] 頁面。 或者，按一下 [完成] 按鈕以使用預設選項。

4. [資料類型選項] 表單可讓您精簡所產生的服務參考組態設定：

    ![適用於 .NET Core 的 [Visual Studio 資料類型選項] 索引標籤](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > 其中一個專案的參考組件內定義服務參考程式碼產生所需的資料類型時，[重複使用參考組件中的類型] 核取方塊選項十分有用。  請務必重複使用這些現有資料類型，避免造成編譯時期類型衝突或執行階段問題。

    根據專案相依性數目和其他系統效能因素，在載入類型資訊時可能會延遲。 除非取消核取 [重複使用參考組件中的類型] 核取方塊，否則會在載入期間停用 [完成] 按鈕。

5. 完成時，請按一下 [完成]。

顯示進度時，此工具會：

- 從 WCF 服務下載中繼資料。
- 在名為 *reference.cs* 的檔案中產生服務參考程式碼，並將它新增至 [已連線的服務] 節點下方的專案。
- 使用在目標平台上編譯和執行所需的 NuGet 套件參考來更新專案檔 (.csproj)。

![Visual Studio 進度視窗](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

完成這些程序時，您可以建立已產生 WCF 用戶端類型的執行個體，並叫用服務作業。

## <a name="see-also"></a>請參閱

- [Windows Communication Foundation 應用程式入門](../../framework/wcf/getting-started-tutorial.md)
- [Visual Studio 中的 Windows Communication Foundation 服務和 WCF 資料服務](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [.NET Core 上的 WCF 支援功能](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a>意見反應和問題

如果您有任何疑問或意見反應，請在使用「回報[問題](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)」工具的[開發人員小組](https://developercommunity.visualstudio.com/)報告。

## <a name="release-notes"></a>版本資訊

- 如需已更新的版本資訊，請參閱[版本資訊](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) (包含已知問題)。
