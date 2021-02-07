---
description: 'Más información acerca de cómo: habilitar la paginación de los resultados del servicio de datos (Servicios de datos de WCF)'
title: 'Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 27a2b37f432d906022d06492b2f687681d9b9ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765339"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF le permite limitar el número de entidades devueltas por una consulta de servicio de datos. Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.  
  
 Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).  
  
 En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos. En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind. Este servicio se crea cuando se completa la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos  
  
- En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Vea también

- [Carga de contenido diferido](loading-deferred-content-wcf-data-services.md)
- [Procedimiento para cargar resultados paginados](how-to-load-paged-results-wcf-data-services.md)
