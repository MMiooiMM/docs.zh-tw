---
title: .NET Core 執行階段識別項 (RID) 目錄
description: 了解執行階段識別碼 (RID) 以及 RID 在 .NET Core 中的使用方式。
ms.date: 02/22/2019
ms.openlocfilehash: e6bc3f75858d4b67cc8598e49ff4ad75521f16d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100912"
---
# <a name="net-core-rid-catalog"></a>.NET Core RID 類別目錄

RID 是*執行階段識別項*的縮寫。 RID 值是用來識別應用程式執行所在的目標平台。
.NET 套件會使用它們來代表 NuGet 套件中的平台特定資產。 下列值是 RID 的範例：`linux-x64`、`ubuntu.14.04-x64`、`win7-x64` 或 `osx.10.12-x64`。
針對具有原生相依性的套件，RID 也可指定能在哪些平台上還原套件。

單一 RID 可在您專案檔的 `<RuntimeIdentifier>` 元素中設定。 可以在專案檔的 `<RuntimeIdentifiers>` 元素中，將多個 RID 定義為以分號分隔的清單。 它們也可以透過以`--runtime`選項搭配下列 [.NET Core CLI 命令](./tools/index.md)來使用：

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

代表具體作業系統的 RID 通常遵循 `[os].[version]-[architecture]-[additional qualifiers]` 這個模式，其中：

- `[os]` 是作業/平台系統 Moniker。 例如，`ubuntu`。

- `[version]` 是作業系統版本，使用以點分隔 (`.`) 的版本號碼表示。 例如，`15.10`。

  - 版本**不應為**行銷版本，因為行銷版本通常代表作業系統的多個個別版本，且具有不同平台 API 介面區。

- `[architecture]` 處理器架構。 例如：`x86`、`x64`、`arm` 或 `arm64`。

- `[additional qualifiers]` 進一步區分不同平台。 例如：`aot`。

## <a name="rid-graph"></a>RID 圖表

RID 圖表或執行階段後援圖形是與彼此相容的 RID 清單。 RID 是在 [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 套件中定義。 您可以在 [*runtime.json*](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) 檔案 (位於 CoreFX 存放庫) 中看到支援的 RID 清單與 RID 圖形。 在此檔案中，您可以看到所有 RID (基底項目除外) 都包含 `"#import"` 陳述式。 這些陳述式指出相容的 RID。

當 NuGet 還原套件時，它會嘗試尋找與所指定執行階段完全相符的項目。
若找不到完全相符的項目，NuGet 會返回到圖形，直到它根據 RID 圖形找到最接近的相容系統。

下列範例是 `osx.10.12-x64` RID 的實際項目：

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

上述 RID 指定 `osx.10.12-x64` 匯入 `osx.10.11-x64`。 因此，當 NuGet 還原套件時，它會嘗試在套件中尋找與 `osx.10.12-x64` 完全相符的項目。 例如，若 NuGet 找不到特定執行階段，它可以還原指定 `osx.10.11-x64` 執行階段的套件。

下列範例顯示也在 *runtime.json* 檔案中定義的稍大 RID 圖形：

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

所有的 RID 最終將對應至根 `any` RID。

處理 RID 時，您必須謹記一些考量：

- RID 是**隱晦字串**，因此必須以黑箱視之。
- 不要以程式設計方式建置 RID。
- 使用已針對平台定義的 RID。
- RID 必須是特定的，因此不要假設實際 RID 值會怎樣。

## <a name="using-rids"></a>使用 RID

若要使用 RID，必須先了解有哪些 RID 存在。 新的值會定期新增至平台。
如需最新的完整版本，請查看 CoreFX 存放庫上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) 檔案。

.NET Core 2.0 SDK 引進可攜式 RID 的概念。 它們是新增到 RID 圖形且未繫結到特定版本或 OS 發行版本的新值，適用於 .NET Core 2.0 和更新版本。 由於大部分發行版本的 RID 都會對應至可攜式 RID，因此在處理多個 Linux 發行版本時特別有用。

下列清單顯示用於每個 OS 的一小部分最常見 RID。

## <a name="windows-rids"></a>Windows RID

僅列出常見值。 如需最新的完整版本，請查看 CoreFX 存放庫上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) 檔案。

- 可攜式 (.NET Core 2.0 或更新版本)
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- Windows 7/Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8.1/Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10/Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

如需詳細資訊，請參閱 [Windows 上 .NET Core 的必要條件](windows-prerequisites.md)。

## <a name="linux-rids"></a>Linux RID

僅列出常見值。 如需最新的完整版本，請查看 CoreFX 存放庫上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) 檔案。 如果下方未列出裝置執行的發行版本，裝置可能可以使用其中一個可攜式 RID。 例如，如果 Raspberry Pi 裝置執行未列出的 Linux 發行版本，則可以 `linux-arm` 為目標。

- 可攜式 (.NET Core 2.0 或更新版本)
  - `linux-x64` (大部分的桌面發行版本，如 CentOS、Debian、Fedora、Ubuntu 和衍生版)
  - `linux-musl-x64` (使用 [musl](https://wiki.musl-libc.org/projects-using-musl.html) 的輕量發行版本，如 Alpine Linux)
  - `linux-arm` (在 ARM 上執行的 Linux 發行版本，如 Raspberry Pi)
- Red Hat Enterprise Linux
  - `rhel-x64` (RHEL 6 版以上已由 `linux-x64` 取代)
  - `rhel.6-x64` (.NET Core 2.0 或更新版本)
- Tizen (.NET Core 2.0 或更新版本)
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

如需詳細資訊，請參閱 [Linux 上 .NET Core 的必要條件](linux-prerequisites.md)。

## <a name="macos-rids"></a>macOS RID

macOS RID 使用較舊的 "OSX" 商標。 僅列出常見值。 如需最新的完整版本，請查看 CoreFX 存放庫上的 [runtime.json](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/runtime.json) 檔案。

- 可攜式 (.NET Core 2.0 或更新版本)
  - `osx-x64` (最低 OS 版本為 macOS 10.12 Sierra)
- macOS 10.10  Yosemite
  - `osx.10.10-x64`
- macOS 10.11 El Capitan
  - `osx.10.11-x64`
- macOS 10.12 Sierra (.NET Core 1.1 或更新版本)
  - `osx.10.12-x64`
- macOS 10.13 High Sierra (.NET Core 1.1 或更新版本)
  - `osx.10.13-x64`
- macOS 10.14 Mojave (.NET Core 1.1 或更新版本)
  - `osx.10.14-x64`

如需詳細資訊，請參閱 [macOS 上 .NET Core 的必要條件](macos-prerequisites.md)。

## <a name="see-also"></a>請參閱

- [執行階段識別碼](https://github.com/dotnet/corefx/blob/master/src/pkg/Microsoft.NETCore.Platforms/readme.md)
