---
title: Procedimiento Habilitar la paginación de resultados del servicio de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: edc150d118153849dd84eb40f1443d842c7d346d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875893"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Procedimiento Habilitar la paginación de resultados del servicio de datos (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite limitar el número de entidades devueltas por una consulta al servicio de datos. Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.  
  
 Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente. Para obtener más información, consulte [configurando el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos. En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind. Este servicio se crea al completar el [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos  
  
-   En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Vea también

- [Carga de contenido diferido](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Cómo: Cargar resultados paginados](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
