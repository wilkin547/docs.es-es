---
title: Procesar por lotes operaciones (Servicios de datos de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: f6e6356b8acc6b5abb217ecc4edd2c3cd185f71a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346159"
---
# <a name="batching-operations-wcf-data-services"></a>Procesar por lotes operaciones (Servicios de datos de WCF)
El Open Data Protocol (OData) admite el procesamiento por lotes de solicitudes a un servicio basado en OData. Para obtener más información, vea [OData: Batch Processing](https://www.odata.org/documentation/odata-version-2-0/batch-processing/). En WCF Data Services, cada operación que usa el <xref:System.Data.Services.Client.DataServiceContext>, como ejecutar una consulta o guardar cambios, da como resultado que se envíe una solicitud independiente al servicio de datos. Para mantener un número razonable de conjuntos de operaciones, puede definir los lotes operacionales explícitamente. Esto garantiza que todas las operaciones del lote se envían al servicio de datos en una única solicitud HTTP, permite que el servidor Procese las operaciones de forma atómica y reduce el número de viajes de ida y vuelta al servicio de datos.  
  
## <a name="batching-query-operations"></a>Operaciones de consulta por lotes  
 Para ejecutar varias consultas en un lote único, debe crear cada consulta en el lote como una instancia independiente de la clase <xref:System.Data.Services.Client.DataServiceRequest%601>. Al crear una solicitud de consulta de esta manera, la propia consulta se define como un URI y sigue las reglas para el redireccionamiento de recursos. Para obtener más información, consulte [acceso a los recursos del servicio de datos](accessing-data-service-resources-wcf-data-services.md). Las solicitudes de consulta por lotes se envían al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, que contiene los objetos de la solicitud de consulta. Este método devuelve un objeto <xref:System.Data.Services.Client.DataServiceResponse>, que es una colección de objetos <xref:System.Data.Services.Client.QueryOperationResponse%601> que representan las respuestas a las consultas individuales del lote, cada una de los cuales contiene una colección de los objetos devueltos por la consulta o la información del error. Cuando se produce un error en cualquier operación de consulta única en el lote, se devuelve la información del error en el objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> para la operación fallida, pero se siguen ejecutando las operaciones restantes. Para obtener más información, vea [Cómo: ejecutar consultas en un lote](how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Las consultas por lotes se pueden ejecutar también de forma asincrónica. Para obtener más información, vea [operaciones asincrónicas](asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Procesamiento por lotes de la operación SaveChanges  
 Cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>, todos los cambios de los que el contexto realiza seguimientos se convierten en operaciones basadas en REST que se envían como solicitudes al servicio OData. De forma predeterminada, estos cambios no se envían en un mensaje de solicitud único. Para requerir que todos los cambios se envíen en una única solicitud, debe llamar al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> e incluir un valor de <xref:System.Data.Services.Client.SaveChangesOptions.Batch> en la enumeración <xref:System.Data.Services.Client.SaveChangesOptions> que se proporciona al método.  
  
 También puede guardar de forma asincrónica los cambios por lotes. Para obtener más información, vea [operaciones asincrónicas](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
