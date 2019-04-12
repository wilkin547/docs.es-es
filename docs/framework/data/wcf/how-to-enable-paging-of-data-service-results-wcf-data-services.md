---
title: Filtrar Habilitar la paginación de resultados del servicio de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: edc150d118153849dd84eb40f1443d842c7d346d
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517845"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="98b05-102">Filtrar Habilitar la paginación de resultados del servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="98b05-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="98b05-103">le permite limitar el número de entidades devueltas por una consulta al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="98b05-103">enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="98b05-104">Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="98b05-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="98b05-105">Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente.</span><span class="sxs-lookup"><span data-stu-id="98b05-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="98b05-106">Para obtener más información, consulte [configurando el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="98b05-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="98b05-107">En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos.</span><span class="sxs-lookup"><span data-stu-id="98b05-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="98b05-108">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="98b05-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="98b05-109">Este servicio se crea al completar el [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="98b05-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="98b05-110">Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos</span><span class="sxs-lookup"><span data-stu-id="98b05-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="98b05-111">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="98b05-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="98b05-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="98b05-112">See also</span></span>

- [<span data-ttu-id="98b05-113">Carga de contenido diferido</span><span class="sxs-lookup"><span data-stu-id="98b05-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="98b05-114">Cómo: Cargar resultados paginados</span><span class="sxs-lookup"><span data-stu-id="98b05-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
