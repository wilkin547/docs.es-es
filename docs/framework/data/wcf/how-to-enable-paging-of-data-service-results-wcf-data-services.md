---
title: "Como: Habilitar la paginaci&#243;n de los resultados del servicio de datos (WCF Data Services) | Microsoft Docs"
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
  - "salida de paginación [WCF Data Services]"
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Como: Habilitar la paginaci&#243;n de los resultados del servicio de datos (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite limitar el número de entidades devueltas por una consulta al servicio de datos.  Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.  
  
 Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente.  Para obtener más información, consulta [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos.  En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.  Este servicio se crea cuando se completa el [Tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos  
  
-   En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## Vea también  
 [Cargar contenido aplazado](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)   
 [Cómo: Cargar resultados paginados](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)