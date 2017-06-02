---
title: "Realizar operaciones por lotes (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, biblioteca de cliente"
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Realizar operaciones por lotes (WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] admite el procesamiento por lotes de solicitudes en un servicio basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Para obtener más información, vea el tema sobre [OData: procesamiento por lotes](http://go.microsoft.com/fwlink/?LinkId=186075). En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], cada operación que usa <xref:System.Data.Services.Client.DataServiceContext>, como ejecutar una consulta o guardar cambios, tiene como resultado el envío de una solicitud independiente al servicio de datos.  Para mantener un número razonable de conjuntos de operaciones, puede definir los lotes operacionales explícitamente.  Esto garantiza que todas las operaciones del lote se envían al servicio de datos en una única solicitud HTTP, permite al servidor procesar las operaciones automáticamente y reduce el número de viajes de ida y vuelta \(round trip\) al servicio de datos.  
  
## Operaciones de consulta por lotes  
 Para ejecutar varias consultas en un lote único, debe crear cada consulta en el lote como una instancia independiente de la clase <xref:System.Data.Services.Client.DataServiceRequest%601>.  Al crear una solicitud de consulta de esta manera, la propia consulta se define como un URI y sigue las reglas para el redireccionamiento de recursos.  Para obtener más información, consulta [Acceso a recursos del servicio de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md).  Las solicitudes de consulta por lotes se envían al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, que contiene los objetos de la solicitud de consulta.  Este método devuelve un objeto <xref:System.Data.Services.Client.DataServiceResponse>, que es una colección de objetos <xref:System.Data.Services.Client.QueryOperationResponse%601> que representan las respuestas a las consultas individuales del lote, cada una de los cuales contiene una colección de los objetos devueltos por la consulta o la información del error.  Cuando se produce un error en cualquier operación de consulta única en el lote, se devuelve la información del error en el objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> para la operación fallida, pero se siguen ejecutando las operaciones restantes.  Para obtener más información, consulta [Cómo: Ejecutar consultas por lotes](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Las consultas por lotes se pueden ejecutar también de forma asincrónica.  Para obtener más información, consulta [Operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## Procesamiento por lotes de la operación SaveChanges  
 Al llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>, todos los cambios detectados por el contexto se traducen en operaciones basadas en REST, que se envían como solicitudes al servicio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  De forma predeterminada, estos cambios no se envían en un mensaje de solicitud único.  Para requerir que todos los cambios se envíen en una solicitud única, debe llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> e incluir un valor de <xref:System.Data.Services.Client.SaveChangesOptions> en la enumeración <xref:System.Data.Services.Client.SaveChangesOptions> que proporcione al método.  
  
 También puede guardar de forma asincrónica los cambios por lotes.  Para obtener más información, consulta [Operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)