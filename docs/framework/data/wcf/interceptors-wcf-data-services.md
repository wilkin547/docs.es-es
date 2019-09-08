---
title: Interceptores (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 7decfdd738e71a01afa8cb32604953142b46e588
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790443"
---
# <a name="interceptors-wcf-data-services"></a>Interceptores (Servicios de datos de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]permite que una aplicación intercepte los mensajes de solicitud para que pueda agregar lógica personalizada a una operación. Puede usar esta lógica personalizada para validar datos en los mensajes entrantes. También puede utilizarla como restricción adicional del ámbito de una solicitud de consulta, por ejemplo, para insertar una directiva de autorización personalizada por solicitud.  
  
 Métodos con atributos especiales realizan la interceptación en el servicio de datos. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] llama a estos métodos en el punto adecuado del procesamiento de mensajes. Los interceptores se definen en cada conjunto de entidades, y los métodos de interceptor no pueden aceptar parámetros de la solicitud, como las operaciones de servicio. Los métodos de interceptor de consulta, a los que se llama al procesar una solicitud HTTP GET, deben devolver una expresión lambda que determine si los resultados de la consulta deben devolver una instancia del conjunto de entidades del interceptor. El servicio de datos utiliza esta expresión para perfeccionar más la operación solicitada. El ejemplo siguiente muestra una definición de un interceptor de consulta.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Para obtener más información, consulte [Cómo Interceptar mensajes](how-to-intercept-data-service-messages-wcf-data-services.md)del servicio de datos.  
  
 Los interceptores de cambio, a los que se llama al procesar las operaciones que no son de consulta, deben devolver `void` (`Nothing` en Visual Basic). Los métodos de interceptor de cambio deben aceptar los dos siguientes parámetros:  
  
1. Un parámetro de un tipo que es compatible con el tipo de entidad del conjunto de entidades. Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la información de la entidad que envía la solicitud.  
  
2. Un parámetro de tipo <xref:System.Data.Services.UpdateOperations>. Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la operación que la solicitud intenta realizar.  
  
 El ejemplo siguiente muestra una definición de un interceptor de cambio.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Para obtener más información, consulte [Cómo Interceptar mensajes](how-to-intercept-data-service-messages-wcf-data-services.md)del servicio de datos.  
  
 La interceptación admite los siguientes atributos.  
  
 **[QueryInterceptor (** *entitySetName* **)]**  
 Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.QueryInterceptorAttribute> cuando se recibe una solicitud GET de HTTP para el recurso de conjunto de entidades concreto. Estos métodos siempre deben devolver una expresión lambda en el formulario de `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor (** *entitySetName* **)]**  
 Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.ChangeInterceptorAttribute> cuando se recibe una solicitud HTTP distinta de GET para el recurso de conjunto de entidades concreto. Estos métodos siempre deben devolver `void` (`Nothing` en Visual Basic).  
  
 Para obtener más información, consulte [Cómo Interceptar mensajes](how-to-intercept-data-service-messages-wcf-data-services.md)del servicio de datos.  
  
## <a name="see-also"></a>Vea también

- [Operaciones de servicio](service-operations-wcf-data-services.md)
