---
title: 作法：使用反映提供者建立資料服務（WCF Data Services）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: feee679c37cd3dafb80021752ee25444c54f0809
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791005"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>HOW TO：使用反映提供者建立資料服務（WCF Data Services）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 可讓您定義以任意類別為基礎的資料模型，只要將這些類別公開為實作 <xref:System.Linq.IQueryable%601> 介面的物件即可。 如需詳細資訊，請參閱[資料服務提供者](data-services-providers-wcf-data-services.md)。  
  
## <a name="example"></a>範例  
 下列範例定義包含 `Orders` 及 `Items` 的資料模型。 實體容器類別 `OrderItemData` 具有兩個會傳回 <xref:System.Linq.IQueryable%601> 介面的公開方法。 這些介面是 `Orders` 和 `Items` 實體類型的實體集。 `Order` 可以包括多個 `Items`，因此 `Orders` 實體類型具有一個 `Items` 導覽屬性，該屬性會傳回 `Items` 物件的集合。 `OrderItemData` 實體容器類別是 <xref:System.Data.Services.DataService%601> 類別的泛型型別，`OrderItems` 資料服務即衍生於此。  
  
> [!NOTE]
> 由於本範例示範的是記憶體內部資料提供者，在目前物件執行個體外部所進行的變更將無法持續，因此實作 <xref:System.Data.Services.IUpdatable> 介面並不會產生任何益處。 如需實作為<xref:System.Data.Services.IUpdatable>介面的範例，請參閱[如何：使用 LINQ to SQL 資料來源](create-a-data-service-using-linq-to-sql-wcf.md)建立資料服務。  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>另請參閱

- [如何：使用 LINQ to SQL 資料來源建立資料服務](create-a-data-service-using-linq-to-sql-wcf.md)
- [資料服務提供者](data-services-providers-wcf-data-services.md)
- [如何：使用 ADO.NET Entity Framework 資料來源建立資料服務](create-a-data-service-using-an-adonet-ef-data-wcf.md)
