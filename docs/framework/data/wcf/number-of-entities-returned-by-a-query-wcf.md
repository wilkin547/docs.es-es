---
description: 'Más información acerca de cómo: determinar el número de entidades devueltas por una consulta (Servicios de datos de WCF)'
title: 'Cómo: Determinar el número de entidades devueltas por una consulta (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: f8eb305bc515d1d69025ce3bcd0a6a9f3baf8232
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794993"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Cómo: Determinar el número de entidades devueltas por una consulta (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Con Servicios de datos de WCF, puede determinar el número de entidades que se encuentran en el conjunto de entidades especificado por un URI de consulta. Este número se puede incluir junto con el resultado de la búsqueda o como valor entero. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se ejecuta una consulta después de llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>. La propiedad <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> devuelve el número de entidades del conjunto de entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se llama al método <xref:System.Linq.Enumerable.Count%2A> para devolver únicamente un valor entero que es el número de entidades del conjunto de entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Vea también

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)
