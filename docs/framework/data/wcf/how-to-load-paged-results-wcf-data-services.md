---
title: 'Cómo: Cargar resultados paginados (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 6706ad2eb6821c2c30b5d2482f709ba849b59f32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356595"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Cómo: Cargar resultados paginados (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] permite que el servicio de datos limite el número de entidades que se devuelven en una fuente de respuesta única. Cuando esto sucede, la última entrada de la fuente contiene un vínculo a la página siguiente de datos. El URI a la página de datos siguiente se obtiene llamando al método <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> del objeto <xref:System.Data.Services.Client.QueryOperationResponse%601>, que se obtiene cuando se ejecuta <xref:System.Data.Services.Client.DataServiceQuery%601>. A continuación, el URI representado por este objeto se utiliza para cargar la página siguiente de resultados. Para obtener más información, consulte [cargar contenido diferido](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa un bucle `do…while` para cargar las entidades `Customers` desde los resultados paginados del servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se devuelve las entidades `Orders` relacionadas con cada entidad `Customers` y se utiliza un bucle `do…while` para cargar páginas de entidades `Customers` y un bucle `while` anidado para cargar páginas de entidades `Orders` relacionadas del servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Vea también  
 [Carga de contenido diferido](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [Carga de entidades relacionadas](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)
