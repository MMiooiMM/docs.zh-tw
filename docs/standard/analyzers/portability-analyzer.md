---
title: .NET Portability Analyzer - .NET
description: 了解如何使用.NET Portability Analyzer 工具來評估程式碼移植到不同 .NET 實作之間的可行性，包括 .NET Core、.NET Standard、UWP 和 Xamarin。
ms.date: 09/13/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: e0a5c791926b36fe5a35c5446471c3dcdb75cd7b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774382"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

要讓您的程式庫支援多平台？ 想要查看需要多少工作才能讓您的 .NET Framework 應用程式在 .NET Core 上執行？ [.Net 可攜性分析器](https://github.com/microsoft/dotnet-apiport)是一種工具，可分析元件，並提供有關 .net api 的詳細報表，這些應用程式或程式庫在您指定的目標 .net 平臺上是可移植的。 可攜性分析器以[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)模組的形式提供，它會分析每個專案的一個元件，並作為[ApiPort 主控台應用程式](https://aka.ms/apiportdownload)，以根據指定的檔案或目錄來分析元件。

當您將專案轉換成以新平臺（例如 .NET Core）為目標時，您可以使用以 Roslyn 為基礎的[API 分析器工具](api-analyzer.md)來識別會擲回 <xref:System.PlatformNotSupportedException> 例外狀況和其他相容性問題的 API。

## <a name="common-targets"></a>常見目標

- [.NET Core](../../core/index.md)︰具有模組化的設計，採用並存，並且適合在跨平台的情況下使用。 並存可讓您採用新的 .NET Core 版本，而不會中斷其他應用程式。 如果您的目標，是要將應用程式移植到 .NET Core 來支援跨平台，這是建議的目標。
- .[NET Standard](../../standard/net-standard.md)：包含適用于所有 .NET 部署的 .NET Standard API。 如果您的目標，是讓程式庫在所有支援 .NET 的平台上執行，這是建議的目標。
- [ASP.NET Core](/aspnet/core)：以 .NET Core 為基礎的新式 web 架構。 如果您的目標，是要將 Web 應用程式移植到 .NET Core 來支援多平台，這是建議的目標。
- .NET Core +[平臺延伸](../../core/porting/windows-compat-pack.md)模組：除了 Windows 相容性套件以外，還包含 .NET Core API，提供許多可用的 .NET Framework 技術。 如需將您的應用程式從 .NET Framework 移植到 Windows 上的 .NET Core，這是建議的目標。
- .NET Standard +[平臺擴充](../../core/porting/windows-compat-pack.md)功能：除了 Windows 相容性套件以外，還包括 .NET Standard API，其提供許多 .NET Framework 可用的技術。 如需將您的程式庫從 .NET Framework 移植到 Windows 上的 .NET Core，這是建議的目標。

## <a name="how-to-use-the-net-portability-analyzer"></a>如何使用 .NET 可攜性分析器

若要開始在 Visual Studio 中使用 .NET 可攜性分析器，您必須從 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) 下載及安裝此延伸模組。 它適用於 Visual Studio 2017 和更新版本。 您可以透過**分析** > **可攜性分析器設定**並選取目標平台 (這是您要評估可攜性間距的 .NET 平台/版本，與建置您目前組件的平台/版本比較)，在 Visual Studio 中對其進行設定。

![可攜性分析器的螢幕擷取畫面。](./media/portability-analyzer/portability-screenshot.png)

您也可以使用 ApiPort 主控台應用程式，可從 [ApiPort 存放庫](https://aka.ms/apiportdownload)下載。 您可以使用 `listTargets` 命令選項來顯示可用的目標清單，然後指定 `-t` 或 `--target` 命令選項來挑選目標平台。

### <a name="analyze-portability"></a>分析可攜性
若要在 Visual Studio 中分析整個專案，在 [方案總管] 中以滑鼠右鍵按一下您的專案，然後選取 [分析組件可攜性]。 否則，請移至 [分析] 功能表，然後選取 [Analyze Assembly Portability] (分析組件可攜性)。 從這裡選取專案的可執行檔或 DLL。

![方案總管的可攜性分析器螢幕擷取畫面。](./media/portability-analyzer/portability-solution-explorer.png)

您也可以使用 [ApiPort 主控台應用程式](https://aka.ms/apiportdownload)。

- 輸入下列命令分析目前的目錄︰`ApiPort.exe analyze -f .`
- 若要分析特定的 .dll 檔案清單，請輸入下列命令︰`ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
- 執行 `ApiPort.exe -?` 以取得詳細說明

建議您納入所有您擁有並想要移植的相關 exe 與 dll 檔案，並排除應用程式所依賴，但您未擁有也無法移植的檔案。 這會提供您最相關的可攜性報告。

### <a name="view-and-interpret-portability-result"></a>檢視並解譯可攜性結果

只有目標平台不支援的 API 會顯示在報表中。
在 Visual Studio 執行分析之後，您會看到 .NET 可攜性報表檔案連結。 如果您使用 [ApiPort 主控台應用程式](https://aka.ms/apiportdownload)，您的 .NET 可攜性報表會儲存為您指定格式的檔案。 預設會在您目前的目錄中儲存為 Excel 檔案 ( *.xlsx*)。

#### <a name="portability-summary"></a>可攜性摘要

![可攜性摘要的螢幕擷取畫面。](./media/portability-analyzer/api-catalog-portablility-summary.png)

此報表顯示的可攜性摘要區段，會顯示該次執行中每個組件的可攜性百分比。 在上述範例中，71.24% 用於 `svcutil` 應用程式中的 .NET Framework API 可在 .NET Core + 平台延伸模組中取得。 如果您對多個組件執行 .NET 可攜性分析工具，每個組件都應該在可攜性摘要報告中具有一個資料列。

#### <a name="details"></a>詳細資料

![可攜性詳細資料的螢幕擷取畫面。](./media/portability-analyzer/api-catalog-portablility-details.png)

報表的 [**詳細資料**] 區段會列出任何選取的**目標平臺**中遺失的 api。

- 目標類型：類型缺少目標平台的 API
- 目標成員：目標平台缺少方法
- 組件名稱：缺少之 API 所在的 .NET Framework 組件。
- 每個選取的目標平臺都是一個資料行，例如「.NET Core」：「不支援」的值表示此目標平臺不支援此 API。
- 建議的變更：建議變更 API 或技術。 目前，許多 API 的此欄位為空白或過期。 因為 API 太多，導致我們難以繼續。 我們將尋找替代解決方案，來為客戶提供有用的資訊。

#### <a name="missing-assemblies"></a>缺少的組件

![遺漏元件的螢幕擷取畫面。](./media/portability-analyzer/api-catalog-missing-assemblies.png)

您可在報表中找到缺少的組件區段。 該區段會告訴您這份組件清單由已分析的組件所參考，但未進行分析。 如果是您自己擁有的組件，請將其納入 API 可攜性分析器中執行，以便您可為其取得 API 層級的詳細可攜性報告。 如果是第三方程式庫，請查看是否有支援您目標平台的較新版本。 如果有，請考慮改用較新版本。 最後，您會預期這份清單包含您應用程式所依賴的所有第三方組件，並確認它們有支援您目標平台的版本。

如需 .NET Portability Analyzer 的詳細資訊，請瀏覽 [GitHub 文件](https://github.com/Microsoft/dotnet-apiport#documentation)和 Channel 9 影片 [Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (.NET Portability Analyzer 簡介)。
