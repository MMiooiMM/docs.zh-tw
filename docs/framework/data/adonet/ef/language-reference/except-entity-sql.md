---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: c4df8c2b72ee60a425c98c64a13a1e2d43d4506e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833865"
---
# <a name="except-entity-sql"></a>EXCEPT (Entity SQL)
從 EXCEPT 運算元左側的查詢運算式傳回任何相異值集合，這些相異值是 EXCEPT 運算元右側的查詢運算式沒有傳回的。 所有運算式都必須具有與 `expression`相同的型別或是共同基底型別或衍生型別。  
  
## <a name="syntax"></a>語法  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a>引數  
 `expression`  
 任何有效的查詢運算式，該運算式會傳回要與另一個查詢運算式傳回之集合相比較的集合。  
  
## <a name="return-value"></a>傳回值  
 具有與 `expression`相同的型別或是共同基底類型或衍生型別的集合。  
  
## <a name="remarks"></a>備註  
 EXCEPT 是其中一個 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 設定運算子。 所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 設定運算子都會從左到右評估。 下表顯示 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 設定運算子的優先順序。  
  
|優先順序|運算子|  
|----------------|---------------|  
|最高|INTERSECT|  
||UNION<br /><br /> UNION ALL|  
||EXCEPT|  
|最低|EXISTS<br /><br /> OVERLAPS<br /><br /> FLATTEN<br /><br /> SET|  
  
## <a name="example"></a>範例  
 下列 Entity SQL 查詢會使用 EXCEPT 運算子，從兩個查詢運算式傳回任何相異值的集合。 此查詢是根據 AdventureWorks Sales Model。 若要編譯及執行此查詢，請遵循以下步驟：  
  
1. 依照 [How 中的程式進行：執行可傳回 StructuralType 結果 @ no__t-0 的查詢。  
  
2. 將下列查詢當成引數，傳遞至 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a>另請參閱

- [Entity SQL 參考](entity-sql-reference.md)
