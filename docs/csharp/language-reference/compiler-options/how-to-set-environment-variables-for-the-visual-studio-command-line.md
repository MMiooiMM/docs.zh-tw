---
title: 作法：為 Visual Studio 命令列設定環境變數
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 9b26f6b80488ad4043054cd23f0f351773e8d6d1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602863"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>作法：為 Visual Studio 命令列設定環境變數

VsDevCmd.bat 檔案可設定適當的環境變數，以啟用命令列組建。

> [!NOTE]
> VsDevCmd.bat 檔是隨附於 Visual Studio 2017 的新檔案。 Visual Studio 2015 及更早的版本則使用 VSVARS32.bat 作為相同用途。 此檔案的儲存位置為 \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools。

如果安裝最新版 Visual Studio 的電腦上也有安裝舊版 Visual Studio，請勿於相同的命令提示字元視窗中，執行不同版本的 VsDevCmd.bat 及 VSVARS32.BAT。 而是應改為在各版本本身的視窗中執行命令。

### <a name="to-run-vsdevcmdbat"></a>執行 VsDevCmd.BAT

1. 從 [開始]  功能表中，開啟 [適用於 VS 2017 的開發人員命令提示字元]  。  位置在 **Visual Studio 2017** 資料夾中。

2. 根據您的安裝變更到 \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools 或是 \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools 子目錄。  (目前的*版本*為 *2017*。 *供應項目*為 *Enterprise*、*Professional* 或 *Community* 中的其中一個。)

3. 鍵入 **VsDevCmd**以執行 VsDevCmd.bat。

    > [!CAUTION]
    > 在不同的電腦上，VsDevCmd.bat 檔案可能也不同。 請勿使用另一部電腦的 VsDevCmd.bat 來取代遺失或損毀的 VsDevCmd.bat 檔案。 請重新執行安裝程式以取代遺失的檔案。

### <a name="available-options-for-vsdevcmdbat"></a>適用於 VsDevCmd.BAT 的可用選項

若要查看適用於 VsDevCmd.BAT 的可用選項，請搭配 `-help` 選項執行命令：

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>另請參閱

- [使用 csc.exe 建置命令列](./command-line-building-with-csc-exe.md)
