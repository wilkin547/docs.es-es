---
title: "C&#243;mo: establecer los encabezados en la solicitud de cliente (Servicios de datos de WCF) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, personalizar solicitudes"
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: establecer los encabezados en la solicitud de cliente (Servicios de datos de WCF)
Cuando use la biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para acceder a un servicio de datos compatible con [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], la biblioteca establece automáticamente los encabezados HTTP necesarios en los mensajes de solicitud enviados al servicio de datos.  Sin embargo, la biblioteca cliente no sabe establecer los encabezados de mensaje necesarios en ciertos casos, como cuando el servicio de datos necesita cookies o autenticación basada en notificaciones.  Para obtener más información, vea [Proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication).  En estos casos, debe establecer manualmente los encabezados de mensaje del mensaje de solicitud antes de enviarlo.  En el ejemplo de este tema se muestra cómo controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> para agregar un nuevo encabezado al mensaje de solicitud antes de que se envíe al servicio de datos.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Además puede usar el  [servicio de datos de ejemplo Northwind](http://go.microsoft.com/fwlink/?LinkId=187426) que se publica en el sitio web de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Este servicio de datos de ejemplo es de solo lectura y si se intentan guardar los cambios, devuelve un error.  Los servicios de datos de ejemplo del sitio web de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] permiten la autenticación anónima.  
  
## Ejemplo  
 En el siguiente ejemplo se registra un controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y, a continuación, se ejecuta una consulta en el servicio de datos.  
  
> [!NOTE]
>  Cuando un servicio de datos necesita que se establezca manualmente el encabezado del mensaje de todas las solicitudes, plantéese registrar el controlador del evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> mediante la invalidación del método parcial `OnContextCreated` del contenedor de entidades que represente el servicio de datos, que en este caso es `NorthwindEntities`.  
  
 [!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]
 [!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]  
  
## Ejemplo  
 El siguiente método controla el evento <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> y agrega un encabezado de autenticación a la solicitud.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## Vea también  
 [Proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)