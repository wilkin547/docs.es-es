---
title: 'Cómo: Cargar entidades relacionadas (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 84c2448f317e813a95688feaaac1c97436de1b16
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569013"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Cómo: Cargar entidades relacionadas (Data Services de WCF)
Cuando necesite cargar entidades asociadas en WCF Data Services, puede utilizar el método <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> en la clase <xref:System.Data.Services.Client.DataServiceContext>. También puede utilizar el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en el <xref:System.Data.Services.Client.DataServiceQuery%601> para requerir que las entidades relacionadas se carguen diligentemente en la misma respuesta de la consulta.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo cargar explícitamente la entidad `Customer` relacionada con cada instancia de `Orders` devuelta.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> para devolver las entidades `Order Details` pertenecientes a las entidades `Orders` devueltas por la consulta.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Vea también

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)
