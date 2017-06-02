---
title: "C&#243;mo: Adjuntar una entidad existente a DataServiceContext (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, cambiar datos"
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Adjuntar una entidad existente a DataServiceContext (WCF Data Services)
Cuando una entidad ya existe en un servicio de datos, la biblioteca de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite adjuntar un objeto que representa directamente la entidad en la clase <xref:System.Data.Services.Client.DataServiceContext> sin ejecutar una consulta primero.  Para obtener más información, consulta [Actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un objeto `Customer` existente que contiene cambios que se van a guardar en el servicio de datos.  Se adjunta el objeto al contexto y se llama al método <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> para marcar el objeto adjunto como <xref:System.Data.Services.Client.EntityStates> antes de llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)