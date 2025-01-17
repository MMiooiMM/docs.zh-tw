---
title: 作法：從文字檔讀取 - C# 程式設計手冊
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 2b98f24da7f13ae752f248eb8f26c75c1d47a824
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923944"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>作法：從文字檔讀取 (C# 程式設計手冊)
這個範例會使用 <xref:System.IO.File?displayProperty=nameWithType> 類別中的靜態方法 <xref:System.IO.File.ReadAllText%2A> 和 <xref:System.IO.File.ReadAllLines%2A>，來讀取文字檔的內容。  
  
 如需使用 <xref:System.IO.StreamReader> 的範例，請參閱[如何：一次一行讀取文字檔](./how-to-read-a-text-file-one-line-at-a-time.md)。  
  
> [!NOTE]
> 此範例中所用的檔案是在[如何︰寫入文字檔](./how-to-write-to-a-text-file.md)主題中建立。  
  
## <a name="example"></a>範例  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 將程式碼複製並貼到 C# 主控台應用程式中。  
  
 如果您不想使用[如何：寫入文字檔](./how-to-write-to-a-text-file.md)中的文字檔，請以您電腦上的適當路徑和檔案名稱取代 `ReadAllText` 和 `ReadAllLines` 的引數。  
  
## <a name="robust-programming"></a>穩固程式設計  
 以下條件可能會造成例外狀況：  
  
- 檔案不存在或不在指定的位置。 請檢查路徑和檔案名稱的拼字。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 請勿依賴檔案的名稱來判斷檔案的內容。 例如，`myFile.cs` 檔案可能不是 C# 原始程式檔。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.IO?displayProperty=nameWithType>
- [C# 程式設計指南](../index.md)
- [檔案系統和登錄 (C# 程式設計指南)](./index.md)
