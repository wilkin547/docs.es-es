---
title: "C&#243;mo: Determinar el n&#250;mero de entidades devueltas por una consulta (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Servicios de datos de Microsoft WCF, recuento de filas"
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Determinar el n&#250;mero de entidades devueltas por una consulta (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede determinar el número de entidades que existen en el conjunto de entidades especificado por un URI de consulta.  Este número se puede incluir junto con el resultado de la búsqueda o como valor entero.  Para obtener más información, consulta [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 En este ejemplo se ejecuta una consulta después de llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>.  La propiedad <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> devuelve el número de entidades del conjunto de entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomers)]  
  
## Ejemplo  
 En este ejemplo se llama al método <xref:System.Linq.Enumerable.Count%2A> para devolver únicamente un valor entero que es el número de entidades del conjunto de entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomersvalueonly)]  
  
## Vea también  
 [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)