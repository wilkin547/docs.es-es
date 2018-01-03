---
title: Procesar por lotes operaciones (Data Services de WCF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65bf6bfd0bd437848137506605a958f5f2e8d750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="batching-operations-wcf-data-services"></a>Procesar por lotes operaciones (Data Services de WCF)
El [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] admite el procesamiento por lotes de las solicitudes a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servicio basado en. Para obtener más información, consulte [OData: procesamiento por lotes](http://go.microsoft.com/fwlink/?LinkId=186075). En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], cada operación que utiliza el <xref:System.Data.Services.Client.DataServiceContext>, como ejecutar una consulta o guardar los cambios, los resultados de una solicitud independiente que se envían al servicio de datos. Para mantener un número razonable de conjuntos de operaciones, puede definir los lotes operacionales explícitamente. Esto garantiza que todas las operaciones del lote se envían al servicio de datos en una única solicitud HTTP, permite que el servidor procesar las operaciones de forma atómica y reduce el número de viajes de ida y vuelta al servicio de datos.  
  
## <a name="batching-query-operations"></a>Operaciones de consulta por lotes  
 Para ejecutar varias consultas en un lote único, debe crear cada consulta en el lote como una instancia independiente de la clase <xref:System.Data.Services.Client.DataServiceRequest%601>. Al crear una solicitud de consulta de esta manera, la propia consulta se define como un URI y sigue las reglas para el redireccionamiento de recursos. Para obtener más información, consulte [acceso a recursos de servicio de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md). Las solicitudes de consulta por lotes se envían al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, que contiene los objetos de la solicitud de consulta. Este método devuelve un objeto <xref:System.Data.Services.Client.DataServiceResponse>, que es una colección de objetos <xref:System.Data.Services.Client.QueryOperationResponse%601> que representan las respuestas a las consultas individuales del lote, cada una de los cuales contiene una colección de los objetos devueltos por la consulta o la información del error. Cuando se produce un error en cualquier operación de consulta única en el lote, se devuelve la información del error en el objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> para la operación fallida, pero se siguen ejecutando las operaciones restantes. Para obtener más información, consulte [Cómo: ejecutar consultas en un lote](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Las consultas por lotes se pueden ejecutar también de forma asincrónica. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Procesamiento por lotes de la operación SaveChanges  
 Cuando se llama a la <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> /método siguiente, todos los cambios que el contexto se traducen en operaciones basadas en REST que se envían como solicitudes a la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] servicio. De forma predeterminada, estos cambios no se envían en un mensaje de solicitud único. Para requerir que se envían todos los cambios en una sola solicitud, debe llamar a la <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> método e incluye un valor de <xref:System.Data.Services.Client.SaveChangesOptions.Batch> en el <xref:System.Data.Services.Client.SaveChangesOptions> enumeración que se proporciona al método.  
  
 También puede guardar de forma asincrónica los cambios por lotes. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
