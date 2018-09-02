---
title: Interceptores (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: c2086d451af72157785796052af123cd210ee036
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400305"
---
# <a name="interceptors-wcf-data-services"></a>Interceptores (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] permite que una aplicación interceptar los mensajes de solicitud, lo que puede agregar lógica personalizada a una operación. Puede usar esta lógica personalizada para validar los datos en los mensajes entrantes. También puede utilizarla como restricción adicional del ámbito de una solicitud de consulta, por ejemplo, para insertar una directiva de autorización personalizada por solicitud.  
  
 Métodos con atributos especiales realizan la interceptación en el servicio de datos. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] llama a estos métodos en el punto adecuado del procesamiento de mensajes. Los interceptores se definen según el conjunto por entidad, y los métodos de interceptor no pueden aceptar parámetros de la solicitud, como las operaciones de servicio pueden. Los métodos de interceptor de consulta, que se llama al procesar una solicitud GET de HTTP, deben devolver los resultados de consulta debe devolver una expresión lambda que determina si se establece una instancia de entidad del interceptor. El servicio de datos utiliza esta expresión para perfeccionar más la operación solicitada. El ejemplo siguiente muestra una definición de un interceptor de consulta.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Para obtener más información, consulte [Cómo: interceptar mensajes de servicio de datos](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Los interceptores de cambio, a los que se llama al procesar las operaciones que no son de consulta, deben devolver `void` (`Nothing` en Visual Basic). Los métodos de interceptor de cambio deben aceptar los dos siguientes parámetros:  
  
1.  Un parámetro de un tipo que es compatible con el tipo de entidad del conjunto de entidades. Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la información de la entidad que envía la solicitud.  
  
2.  Un parámetro de tipo <xref:System.Data.Services.UpdateOperations>. Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la operación que la solicitud intenta realizar.  
  
 El ejemplo siguiente muestra una definición de un interceptor de cambio.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Para obtener más información, consulte [Cómo: interceptar mensajes de servicio de datos](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 La interceptación admite los siguientes atributos.  
  
 **[QueryInterceptor (** *EntitySetName* **)]**  
 Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.QueryInterceptorAttribute> cuando se recibe una solicitud GET de HTTP para el recurso de conjunto de entidades concreto. Estos métodos siempre deben devolver una expresión lambda en el formulario de `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor (** *EntitySetName* **)]**  
 Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.ChangeInterceptorAttribute> cuando se recibe una solicitud HTTP distinta de GET para el recurso de conjunto de entidades concreto. Estos métodos siempre deben devolver `void` (`Nothing` en Visual Basic).  
  
 Para obtener más información, consulte [Cómo: interceptar mensajes de servicio de datos](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de servicio](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
