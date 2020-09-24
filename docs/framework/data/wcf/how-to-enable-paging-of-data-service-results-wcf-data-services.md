---
title: 'Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 1c8bb8fe757c35f6096b139da6ca939b1ce1c283
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150627"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="de7ae-102">Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="de7ae-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>

<span data-ttu-id="de7ae-103">WCF Data Services le permite limitar el número de entidades devueltas por una consulta de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="de7ae-103">WCF Data Services enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="de7ae-104">Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="de7ae-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="de7ae-105">Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente.</span><span class="sxs-lookup"><span data-stu-id="de7ae-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="de7ae-106">Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="de7ae-106">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="de7ae-107">En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos.</span><span class="sxs-lookup"><span data-stu-id="de7ae-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="de7ae-108">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="de7ae-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="de7ae-109">Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="de7ae-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="de7ae-110">Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos</span><span class="sxs-lookup"><span data-stu-id="de7ae-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
- <span data-ttu-id="de7ae-111">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="de7ae-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="de7ae-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="de7ae-112">See also</span></span>

- [<span data-ttu-id="de7ae-113">Carga de contenido diferido</span><span class="sxs-lookup"><span data-stu-id="de7ae-113">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="de7ae-114">Procedimiento para cargar resultados paginados</span><span class="sxs-lookup"><span data-stu-id="de7ae-114">How to: Load Paged Results</span></span>](how-to-load-paged-results-wcf-data-services.md)
