---
title: 陣列轉換 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 475f3f5357f7c989a30ca9e6c5d32b8cc989436f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581853"
---
# <a name="array-conversions-visual-basic"></a>陣列轉換 (Visual Basic)
您可以將陣列類型轉換成不同的陣列類型，前提是您符合下列條件：  
  
- **相等順位。** 這兩個數組的次序必須相同，也就是說，它們必須有相同數目的維度。 不過，個別維度的長度不需要相同。  
  
- **元素資料類型。** 這兩個數組之元素的資料類型必須是參考型別。 您無法將 `Integer` 陣列轉換成 `Long` 陣列，甚至是 `Object` 陣列，因為至少有一個數值型別涉及。 如需詳細資訊，請參閱 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。  
  
- **可轉換性.** 這兩個數組的元素類型之間必須有轉換，也就是擴展或縮小。 失敗這項需求的範例是嘗試在 `String` 陣列與衍生自 <xref:System.Attribute?displayProperty=nameWithType> 的類別陣列之間進行轉換。 這兩種類型都不會有任何作用，而且它們之間不會有任何類型的轉換。  
  
 將一個陣列型別轉換成另一個，是根據個別元素的轉換是擴展或縮小而定。 如需詳細資訊，請參閱 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。  
  
## <a name="conversion-to-an-object-array"></a>轉換成物件陣列  
 當您宣告 `Object` 陣列而不將它初始化時，只要它保持未初始化，它的元素類型就會 `Object`。 當您將它設定為特定類別的陣列時，它會採用該類別的類型。 不過，它的基礎類型仍然 `Object`，您可以接著將它設定為不相關類別的另一個陣列。 由於所有類別都是衍生自 `Object`，因此您可以將陣列的元素類型從任何類別變更為任何其他類別。  
  
 在下列範例中，類型 `student` 和 `String` 之間不存在任何轉換，但兩者都是衍生自 `Object`，因此所有指派都是有效的。  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>陣列的基礎類型  
 如果您最初宣告具有特定類別的陣列，其基礎元素類型就是該類別。 如果您接著將它設定為另一個類別的陣列，則這兩個類別之間必須有轉換。  
  
 在下列範例中，`students` 是 `student` 陣列。 因為 `String` 與 `student` 之間沒有任何轉換存在，所以最後一個語句會失敗。  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>請參閱

- [資料類型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Visual Basic 中的類型轉換](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [隱含和明確轉換](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [字串與其他類型之間的轉換](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [如何：在 Visual Basic 中將物件轉換為另一種類型](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [資料類型](../../../../visual-basic/language-reference/data-types/index.md)
- [類型轉換函式](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [陣列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
