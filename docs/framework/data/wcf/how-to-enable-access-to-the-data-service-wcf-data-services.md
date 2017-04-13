---
title: "C&#243;mo: Habilitar el acceso al servicio de datos (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, configurar"
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Habilitar el acceso al servicio de datos (WCF Data Services)
En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], debe permitir explícitamente el acceso a los recursos expuestos por un servicio de datos.  Esto significa que después de crear un nuevo servicio de datos, debe proporcionar explícitamente acceso a los recursos individuales como conjuntos de entidades.  En este tema se muestra cómo permitir el acceso de lectura y escritura a cinco de los conjuntos de entidades en el servicio de datos Northwind que se crea al completar el [tutorial rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Como la enumeración <xref:System.Data.Services.EntitySetRights> se define usando <xref:System.FlagsAttribute>, puede usar un operador lógico OR para especificar varios permisos para un único conjunto de entidades.  
  
> [!NOTE]
>  Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.  En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos, también debería proteger la aplicación.  Para obtener más información, consulta [NIB: ASP.NET Security](http://msdn.microsoft.com/es-es/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### Para habilitar el acceso al servicio de datos  
  
-   En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     De esta forma, los clientes pueden tener acceso de lectura y escritura a los conjuntos de entidades de `Orders` y `Order_Details`, y acceso de solo lectura a los conjuntos de entidades de `Customers`.  
  
## Vea también  
 [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)   
 [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)