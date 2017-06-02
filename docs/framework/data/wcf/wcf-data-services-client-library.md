---
title: "Biblioteca de cliente de WCF Data Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "HTML"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DataServiceContext, clase, acerca de la clase DataServiceContext"
  - "DataServiceQuery, clase, acerca de la clase DataServiceQuery"
  - "WCF Data Services, biblioteca de cliente"
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Biblioteca de cliente de WCF Data Services
Cualquier aplicación puede interactuar con un servicio de datos basado en [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] si puede enviar una solicitud HTTP y procesar la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que devuelve un servicio de datos. Esta interoperabilidad le permite tener acceso a servicios basados en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde una amplia gama de aplicaciones habilitadas para web.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye bibliotecas de cliente que proporcionan una experiencia de programación más enriquecida cuando se usan fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde aplicaciones basadas en .NET Framework o Silverlight.  
  
 Las dos clases principales de la biblioteca cliente son <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>.  La clase <xref:System.Data.Services.Client.DataServiceContext> encapsula las operaciones admitidas en un servicio de datos determinado.  Los servicios de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] carecen de estado, pero no ocurre lo mismo con el contexto.  Por consiguiente, puede usar la clase <xref:System.Data.Services.Client.DataServiceContext> para mantener el estado en el cliente entre las interacciones con el servicio de datos para admitir características como la administración de cambios.  Esta clase también administra las identidades y realiza el seguimiento de los cambios.  La clase <xref:System.Data.Services.Client.DataServiceQuery%601> representa una consulta en un conjunto de entidades concreto.  
  
 En esta sección se describe cómo usar las bibliotecas de cliente para obtener acceso a los datos de una aplicación cliente de .NET Framework y para cambiarlos.  Para obtener más información sobre cómo utilizar la biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] con una aplicación basada en Silverlight, vea [WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=186016).  Existen otras bibliotecas cliente disponibles que permiten consumir una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en otros tipos de aplicaciones.  Para obtener más información, vea el tema sobre el [SDK de OData](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## En esta sección  
 [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Describe cómo generar una biblioteca cliente y las clases de servicio de datos de cliente basadas en fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Describe cómo consultar un servicio de datos desde una aplicación basada en .NET Framework usando bibliotecas de cliente.  
  
 [Cargar contenido aplazado](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Describe cómo cargar contenido adicional no incluido en la respuesta de la consulta inicial.  
  
 [Actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Describe cómo crear, modificar y eliminar entidades y relaciones usando bibliotecas de cliente.  
  
 [Operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Describe los medios proporcionados por las bibliotecas de cliente para trabajar con un servicio de datos de manera asincrónica.  
  
 [Realizar operaciones por lotes](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Describe cómo enviar varias solicitudes al servicio de datos en un solo lote usando las bibliotecas de cliente.  
  
 [Enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Describe cómo enlazar controles a la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que devuelve un servicio de datos.  
  
 [Operaciones de servicio de llamada](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Describe cómo usar la biblioteca de cliente para llamar a operaciones de servicio.  
  
 [Administrar el contexto del servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Describe las opciones para administrar el comportamiento de la biblioteca cliente.  
  
 [Trabajar con datos binarios](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Describe cómo obtener acceso y cambiar los datos binarios devueltos por el servicio de datos como un flujo de datos.  
  
## Vea también  
 [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)