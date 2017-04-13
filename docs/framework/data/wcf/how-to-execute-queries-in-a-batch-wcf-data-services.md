---
title: "C&#243;mo: Ejecutar consultas por lotes (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, solicitudes por lotes"
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Ejecutar consultas por lotes (WCF Data Services)
La biblioteca de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite ejecutar más de una consulta en el servicio de datos de un solo lote.  Para obtener más información, consulta [Realizar operaciones por lotes](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar al método <xref:Microsoft.SqlServer.ReportingServices.ReportingService.ExecuteBatch%2A> para ejecutar una matriz de los objetos <xref:System.Data.Services.Client.DataServiceRequest%601> que contiene consultas que devuelven objetos `Products` y `Customers` del servicio de datos de Northwind.  La colección de objetos <xref:System.Data.Services.Client.QueryOperationResponse%601> del objeto <xref:System.Data.Services.Client.DataServiceResponse> devuelto es de tipo enumerado y la colección de objetos contenida en cada <xref:System.Data.Services.Client.QueryOperationResponse%601> también lo es.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)