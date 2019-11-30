---
title: 'Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 6b7cea2475a5c11091a04ef3044bbc958e55fc5d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569089"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)
WCF Data Services le permite limitar el número de entidades devueltas por una consulta de servicio de datos. Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.  
  
 Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).  
  
 En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos. En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind. Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos  
  
- En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Vea también

- [Carga de contenido diferido](loading-deferred-content-wcf-data-services.md)
- [Carga de resultados paginados](how-to-load-paged-results-wcf-data-services.md)
