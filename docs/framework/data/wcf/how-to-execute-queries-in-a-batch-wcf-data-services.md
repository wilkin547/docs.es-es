---
title: 'Cómo: Ejecutar consultas en un lote (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: d710d6539cf465624aa985ce19a67a6d8fb8ee8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355422"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Cómo: Ejecutar consultas en un lote (Data Services de WCF)
Mediante el uso de la [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente, puede ejecutar más de una consulta en el servicio de datos en un único lote. Para obtener más información, consulte [operaciones por lotes](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar al método <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> para ejecutar una matriz de los objetos <xref:System.Data.Services.Client.DataServiceRequest%601> que contiene consultas que devuelven objetos `Customers` y `Products` del servicio de datos de Northwind. La colección de objetos <xref:System.Data.Services.Client.QueryOperationResponse%601> del objeto <xref:System.Data.Services.Client.DataServiceResponse> devuelto es de tipo enumerado y la colección de objetos contenida en cada <xref:System.Data.Services.Client.QueryOperationResponse%601> también lo es.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
