---
title: "C&#243;mo: Cargar resultados paginados (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, contenido aplazado"
  - "Servicios de datos de Microsoft WCF, cargar datos"
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Cargar resultados paginados (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] permite que el servicio de datos limite el número de entidades que se devuelven en una fuente de respuesta única.  Cuando esto sucede, la última entrada de la fuente contiene un vínculo a la página siguiente de datos.  El URI para la página siguiente de datos se obtiene llamando al método <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> de <xref:System.Data.Services.Client.QueryOperationResponse%601>, que se devuelve cuando se ejecuta <xref:System.Data.Services.Client.DataServiceQuery%601>. El URI representado por este objeto se usa a continuación para cargar la página siguiente de resultados.  Para obtener más información, consulta [Cargar contenido aplazado](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 En este ejemplo se usa un bucle `do…while` para cargar las entidades `Customers` desde los resultados paginados del servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## Ejemplo  
 En este ejemplo se devuelve las entidades `Orders` relacionadas con cada entidad `Customers` y se utiliza un bucle `do…while` para cargar páginas de entidades `Customers` y un bucle `while` anidado para cargar páginas de entidades `Orders` relacionadas del servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## Vea también  
 [Cargar contenido aplazado](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)   
 [Cómo: Cargar entidades relacionadas](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)