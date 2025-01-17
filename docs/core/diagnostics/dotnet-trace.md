---
title: dotnet-追蹤-.NET Core
description: 安裝和使用 dotnet 追蹤命令列工具。
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321579"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>效能分析公用程式追蹤（`dotnet-trace`）

**本文適用于：** .net CORE 3.0 SDK 和更新版本

## <a name="installing-dotnet-trace"></a>安裝 `dotnet-trace`

若要安裝 `dotnet-trace` [NuGet 套件](https://www.nuget.org/packages/dotnet-trace)的最新發行版本，請使用[dotnet tool install](../tools/dotnet-tool-install.md)命令：

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>概要

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>描述

@No__t_0 工具是一種跨平臺 CLI 全域工具，可讓您收集執行中進程的 .NET Core 追蹤，而不需要任何原生分析工具。 它是圍繞 .NET Core 執行時間的跨平臺 `EventPipe` 技術所建立的。 `dotnet-trace` 在 Windows、Linux 或 macOS 上提供相同的體驗。

## <a name="options"></a>選項

- **`--version`**

顯示 dotnet 計數器公用程式的版本。

- **`-h|--help`**

顯示命令列說明。

## <a name="commands"></a>命令

| 命令                                                     |
| ----------------------------------------------------------- |
| [dotnet-追蹤收集](#dotnet-trace-collect)               |
| [dotnet-追蹤轉換](#dotnet-trace-convert)               |
| [dotnet-追蹤清單-進程](#dotnet-trace-list-processes) |
| [dotnet-追蹤清單-設定檔](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-追蹤收集

從執行中的進程收集診斷追蹤。

### <a name="synopsis"></a>概要

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>選項

- **`-p|--process-id <PID>`**

  要從中收集追蹤的進程。

- **`--buffersize <size>`**

  設定記憶體中的迴圈緩衝區大小（以 mb 為單位）。 預設值： 256 MB。

- **`-o|--output <trace-file-path>`**

  所收集追蹤資料的輸出路徑。 如果未指定，則預設為 `trace.nettrace`。

- **`--providers <list-of-comma-separated-providers>`**

  要啟用的 `EventPipe` 提供者清單（以逗號分隔）。 這些提供者會補充 `--profile <profile-name>` 所隱含的任何提供者。 如果特定提供者有任何不一致的情況，此處的設定會優先于設定檔中的隱含設定。

  這份提供者清單的格式如下：

  - `Provider[,Provider]`
  - `Provider` 的格式為： `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`。
  - `KeyValueArgs` 的格式為： `[key1=value1][;key2=value2]`。

- **`--profile <profile-name>`**

  一組命名的預先定義提供者設定，可讓您簡潔地指定一般追蹤案例。

- **`--format <NetTrace|Speedscope>`**

  設定追蹤檔案轉換的輸出格式。

## <a name="dotnet-trace-convert"></a>dotnet-追蹤轉換

將 `nettrace` 追蹤轉換為替代的格式，以搭配替代的追蹤分析工具使用。

### <a name="synopsis"></a>概要

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>引數

- **`<input-filename>`**

  要轉換的輸入追蹤檔案。 預設為*nettrace*。

### <a name="options"></a>選項

- **`--format <NetTrace|Speedscope>`**

  設定追蹤檔案轉換的輸出格式。

- **`-o|--output <output-filename>`**

  輸出檔案名。 將會加入目標格式的副檔名。

## <a name="dotnet-trace-list-processes"></a>dotnet-追蹤清單-進程

列出可以追蹤的 dotnet 進程。

### <a name="synopsis"></a>概要

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-追蹤清單-設定檔

列出預先建立的追蹤設定檔，其中包含每個設定檔中提供者和篩選器的描述。

### <a name="synopsis"></a>概要

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>使用 `dotnet-trace` 收集追蹤

- 若要使用 `dotnet-trace` 收集追蹤，您必須先找出 .NET Core 應用程式的處理序識別碼（PID），以從中收集追蹤。

  - 在 Windows 上，有一些選項，例如使用工作管理員或 `tasklist` 命令。
  - 在 Linux 上，[一般] 選項可能會使用 `ps` 命令。

您也可以使用[dotnet-追蹤清單-進程](#dotnet-trace-list-processes)命令，找出執行中的 .net Core 進程及其 pid。

- 然後，執行下列命令：

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- 最後，按下 `<Enter>` 鍵來停止收集，`dotnet-trace` 會完成記錄事件以 `trace.nettrace` 檔案。

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>查看從 `dotnet-trace` 所捕獲的追蹤

在 Windows 上，您可以在[PerfView](https://github.com/microsoft/perfview)上查看 `.nettrace` 檔案以進行分析，就像使用 ETW 或 LTTng 收集的追蹤一樣。 針對在 Linux 上收集的追蹤，您可以將追蹤移至要在 PerfView 上查看的 Windows 電腦。

您也可以藉由將 `dotnet-trace` 的輸出格式變更為 `speedscope`，在 Linux 機器上觀看追蹤。 您可以使用 `-f|--format` 選項來變更輸出檔案格式，`-f speedscope` 會使 `dotnet-trace` 產生 `speedscope` 檔案。 您目前可以選擇 `nettrace` （預設選項）和 `speedscope`。 可以在 <https://www.speedscope.app> 開啟 `Speedscope` 檔案。

> [!NOTE]
> .NET Core 執行時間會以 `nettrace` 格式產生追蹤，並在追蹤完成之後，轉換成 speedscope （如果有指定的話）。 由於某些轉換可能會導致資料遺失，因此原始 `nettrace` 檔案會保留在轉換後的檔案旁邊。

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>使用 `dotnet-trace` 來收集一段時間的計數器值

如果您嘗試在效能相關設定（例如生產環境）中使用基本健全狀況監視的 `EventCounter`，而您想要收集追蹤，而不是即時監看它們，您也可以透過 `dotnet-trace` 來執行這項操作。

例如，如果您想要收集執行時間效能計數器的值，您可以使用下列命令：

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

此命令會告訴執行時間計數器每秒報告一次，以進行輕量的健全狀況監視。 以較高的值取代 `EventCounterIntervalSec=1` （例如，60），可讓您以較少的計數器資料收集較小的追蹤。

如果您想要停用運行時間事件以減少額外負荷（和追蹤大小），您可以使用下列命令來停用運行時間事件和 managed 堆疊 profiler。

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>.NET 提供者

.NET Core 執行時間支援下列 .NET 提供者。 .NET Core 會使用相同的關鍵字來啟用 `Event Tracing for Windows (ETW)` 和 `EventPipe` 追蹤。

| 提供者名稱                            | 內容 |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [執行時間提供者](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR 執行時間關鍵字](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [取消提供者](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR 取消關鍵字](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | 啟用範例 profiler。 |
