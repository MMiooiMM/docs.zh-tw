---
title: Visual Basic 中的 Main 程序
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 1c76e3ade0b383727c3241fdaf5ae44b677559c8
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775700"
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic 中的 Main 程序
每個 Visual Basic 應用程式都必須包含一個稱為 `Main` 的程式。 此程式可做為您應用程式的起點和整體控制。 .NET Framework 在載入您的應用程式並準備好將控制權傳遞給它時，會呼叫 `Main` 程式。 除非您要建立 Windows Forms 應用程式，否則必須針對自己執行的應用程式撰寫 `Main` 程式。

 `Main` 包含第一個執行的程式碼。 在 `Main` 中，您可以決定要在程式啟動時先載入哪一個表單、找出應用程式的複本是否已經在系統上執行、為您的應用程式建立一組變數，或是開啟應用程式所需的資料庫。

## <a name="requirements-for-the-main-procedure"></a>主要程式的需求
 本身執行的檔案（通常副檔名為 .exe）必須包含 `Main` 程式。 程式庫（例如，副檔名為 .dll）本身不會執行，而且不需要 `Main` 程式。 您可以建立的不同專案類型的需求如下：

- 主控台應用程式會自行執行，而且您必須至少提供一個 `Main` 程式。

- Windows Forms 應用程式會自行執行。 不過，Visual Basic 編譯器會在這類應用程式中自動產生 `Main` 程式，而您不需要撰寫一個。

- 類別庫不需要 `Main` 程式。 其中包括 Windows 控制項程式庫和 Web 控制項程式庫。 Web 應用程式會部署為類別庫。

## <a name="declaring-the-main-procedure"></a>宣告 Main 程式
 有四種方式可以宣告 `Main` 程式。 它可以接受引數，也可以傳回值。

> [!NOTE]
> 如果您在類別中宣告 `Main`，則必須使用 `Shared` 關鍵字。 在模組中，不需要 `Shared` `Main`。

- 最簡單的方式是宣告不接受引數或傳回值的 `Sub` 程式。

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` 也可以傳回 `Integer` 值，以供作業系統用來做為程式的結束代碼。 其他程式則可以藉由檢查 Windows ERRORLEVEL 值來測試此程式碼。 若要傳回結束代碼，您必須將 `Main` 宣告為 `Function` 程式，而不是 `Sub` 程式。

    ```vb
    Module mainModule
        Function Main() As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- `Main` 也可以接受 `String` 陣列做為引數。 陣列中的每個字串都包含用來叫用程式的其中一個命令列引數。 您可以根據它們的值來採取不同的動作。

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- 您可以宣告 `Main` 來檢查命令列引數，但不會傳回結束代碼，如下所示。

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>請參閱

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Visual Basic 程式的結構](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Sub 陳述式](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function 陳述式](../../../visual-basic/language-reference/statements/function-statement.md)
- [Integer 資料類型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [String 資料類型](../../../visual-basic/language-reference/data-types/string-data-type.md)
