---
title: dotnet restore 命令
description: 了解如何使用 dotnet restore 命令來還原相依性和專案特有工具。
ms.date: 05/29/2018
ms.openlocfilehash: 055a4250755af02ad392877663985f86a647f892
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275745"
---
# <a name="dotnet-restore"></a>dotnet restore

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet restore` - 還原專案的相依性和工具。

## <a name="synopsis"></a>概要

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a>描述

`dotnet restore` 命令會使用 NuGet 來還原相依性以及專案檔中指定的專案特定工具。 預設會平行執行相依性和工具的還原。

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

若要還原相依性，NuGet 需要套件所在的摘要。 摘要通常透過 *nuget.config* 組態檔提供。 安裝 CLI 工具時，會提供預設組態檔。 您可以在專案目錄中建立自己的 *nuget.config* 檔案，以指定其他摘要。 您也可以在命令提示字元中針對每個引動過程指定其他摘要。

針對相依性，您可以使用 `--packages` 引數指定已還原套件在還原作業期間的放置位置。 如果未指定，則會使用預設的 NuGet 套件快取，它位於所有作業系統上使用者主目錄的 `.nuget/packages` 目錄中。 例如，Linux 上的 */home/user1* 或 Windows 上的 *C:\Users\user1*。

針對專案特定工具，`dotnet restore` 會先還原在其中封裝工具的套件，然後繼續還原其專案檔中所指定的工具相依性。

### <a name="nugetconfig-differences"></a>nuget.config 差異

*nuget.config* 檔案中設定 (如果有的話) 會影響 `dotnet restore` 命令的行為。 例如，在 *nuget.config* 中設定 `globalPackagesFolder` 會將還原的 NuGet 套件置於所指定資料夾。 這是在 `dotnet restore` 命令上指定 `--packages` 選項的替代方式。 如需詳細資訊，請參閱 [nuget.config 參考](/nuget/schema/nuget-config-file)。

`dotnet restore` 會忽略三個特定設定：

- [bindingRedirects](/nuget/schema/nuget-config-file#bindingredirects-section)

  繫結重新導向不適用於 `<PackageReference>` 元素，且 .NET Core 針對 NuGet 套件僅支援 `<PackageReference>` 元素。

- [solution](/nuget/schema/nuget-config-file#solution-section)

  這是 Visual Studio 特定設定，不適用於 .NET Core。 .Net Core 不會使用 `packages.config` 檔案，而是針對 NuGet 套件使用 `<PackageReference>` 元素。

- [trustedSigners](/nuget/schema/nuget-config-file#trustedsigners-section)

  此設定不適用，因為 [NuGet 尚未支援信任套件的跨平臺驗證](https://github.com/NuGet/Home/issues/7939)。

## <a name="implicit-dotnet-restore"></a>隱含 `dotnet restore`

從 .NET Core 2.0 開始，當您發出下列命令時，`dotnet restore` 會於必要時隱含地執行：

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

多數情況下，您不再需要明確地使用 `dotnet restore` 命令。

有時候，可能不適合隱含執行 `dotnet restore`。 例如，某些自動化系統，像是建置系統，必須明確呼叫 `dotnet restore` 以控制還原發生的時間，進而控制網路使用量。 為避免隱含執行 `dotnet restore`，在使用任一這些命令時，可使用 `--no-restore` 旗標來停用隱含還原。

## <a name="arguments"></a>引數

`ROOT`

要還原之專案檔的選用路徑。

## <a name="options"></a>選項。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--configfile <FILE>`

要用於還原作業的 NuGet 組態檔 (*nuget.config*)。

`--disable-parallel`

停用平行還原多個專案。

`--force`

即使最後的還原成功，仍強制解析所有相依性。 指定這個旗標等同於刪除 *project.assets.json* 檔案。

`-h|--help`

印出命令的簡短說明。

`--ignore-failed-sources`

如果有套件符合版本需求，則只會警告有關失敗的來源。

`--no-cache`

指定不要快取套件和 HTTP 要求。

`--no-dependencies`

在還原包含專案對專案 (P2P) 參考的專案時，會還原根專案，而非參考。

`--packages <PACKAGES_DIRECTORY>`

指定已還原套件的目錄。

`-r|--runtime <RUNTIME_IDENTIFIER>`

指定套件還原的執行階段。 這用來針對 *.csproj* 檔案內 `<RuntimeIdentifiers>` 標記中未明確列出的執行階段還原套件。 如需執行階段識別項 (RID) 清單，請參閱 [RID 目錄](../rid-catalog.md)。 多次指定這個選項來提供多個 RID。

`-s|--source <SOURCE>`

指定要在還原作業期間使用的 NuGet 套件來源。 此設定會覆寫 *nuget.config* 檔案中指定的所有來源。 多次指定這個選項，即可提供多個來源。

`--verbosity <LEVEL>`

設定命令的詳細資訊層級。 允許的值為 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。 預設值為 `minimal`。

`--interactive`

允許命令停止並等候使用者輸入或動作 (例如完成驗證)。 自 .NET Core 2.1.400 起。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--configfile <FILE>`

要用於還原作業的 NuGet 組態檔 (*nuget.config*)。

`--disable-parallel`

停用平行還原多個專案。

`-h|--help`

印出命令的簡短說明。

`--ignore-failed-sources`

如果有套件符合版本需求，則只會警告有關失敗的來源。

`--no-cache`

指定不要快取套件和 HTTP 要求。

`--no-dependencies`

在還原包含專案對專案 (P2P) 參考的專案時，會還原根專案，而非參考。

`--packages <PACKAGES_DIRECTORY>`

指定已還原套件的目錄。

`-r|--runtime <RUNTIME_IDENTIFIER>`

指定套件還原的執行階段。 這用來針對 *.csproj* 檔案內 `<RuntimeIdentifiers>` 標記中未明確列出的執行階段還原套件。 如需執行階段識別項 (RID) 清單，請參閱 [RID 目錄](../rid-catalog.md)。 多次指定這個選項來提供多個 RID。

`-s|--source <SOURCE>`

指定要在還原作業期間使用的 NuGet 套件來源。 這會覆寫*nuget.exe*檔案中指定的所有來源，並有效地讀取*nuget.exe*檔案，就好像 @no__t 2 元素不存在一樣。 多次指定這個選項，即可提供多個來源。

`--verbosity <LEVEL>`

設定命令的詳細資訊層級。 允許的值為 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。 預設為 `minimal`。

---

## <a name="examples"></a>範例

還原目前目錄中專案的相依性和工具︰

`dotnet restore`

還原在指定路徑中找到之 `app1` 專案的相依性和工具︰

`dotnet restore ~/projects/app1/app1.csproj`

使用提供為來源的檔案路徑，還原目前目錄中專案的相依性和工具︰

`dotnet restore -s c:\packages\mypackages`

使用提供為來源的兩個檔案路徑，還原目前目錄中專案的相依性和工具︰

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

還原目前目錄中專案的相依性和工具，顯示詳細輸出：

`dotnet restore --verbosity detailed`
