---
title: "Cómo: Cargar entidades relacionadas (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67f18d8dd9f25a5eb99f522ddd7942ff27dda497
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Cómo: Cargar entidades relacionadas (Data Services de WCF)
Cuando necesite cargar entidades asociadas en [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede usar el método <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>. También puede usar el <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> método en el <xref:System.Data.Services.Client.DataServiceQuery%601> para requerir que las entidades relacionadas se carguen rápidamente en la misma respuesta de consulta.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo cargar explícitamente la entidad `Customer` relacionada con cada instancia de `Orders` devuelta.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> para devolver las entidades `Order Details` pertenecientes a las entidades `Orders` devueltas por la consulta.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Vea también  
 [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
