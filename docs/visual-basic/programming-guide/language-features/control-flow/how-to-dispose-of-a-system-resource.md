---
title: 如何：處置系統資源 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c780ee1a174ad044593960bc30a3ee2e1f929390
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583149"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>如何：處置系統資源 (Visual Basic)
您可以使用 `Using` 區塊，確保當您的程式碼結束區塊時，系統會處置資源。 如果您使用的系統資源會耗用大量的記憶體，或其他元件也想要使用，這就很有用。  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>若要在程式碼完成時處置資料庫連接  
  
1. 請確定您在來源檔案的開頭包含資料庫連接的適當[Imports 語句（.Net 命名空間和類型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) （在此案例中為 <xref:System.Data.SqlClient>）。  
  
2. 使用 `Using` 和 `End Using` 語句來建立 `Using` 區塊。 在區塊內，放入處理資料庫連接的程式碼。  
  
3. 宣告連接，並建立它的實例做為 `Using` 語句的一部分。  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     無論您如何結束區塊，系統都會處置資源，包括未處理之例外狀況的情況。  
  
     請注意，您無法從 `Using` 區塊外部存取 `sqc`，因為它的範圍限制為區塊。  
  
     您可以在系統資源（例如檔案控制代碼或 COM 包裝函式）上使用這項相同的技術。 當您想要在結束 [`Using`] 區塊之後，保留其他元件的可用資源時，請使用 `Using` 區塊。  
  
## <a name="see-also"></a>請參閱

- <xref:System.Data.SqlClient.SqlConnection>
- [控制流程](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [決策結構](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [迴圈結構](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [其他控制結構](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [巢狀控制結構](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using 陳述式](../../../../visual-basic/language-reference/statements/using-statement.md)
