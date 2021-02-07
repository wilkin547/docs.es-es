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
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="35fe1-103">Cómo: Habilitar la paginación de los resultados de servicios de datos (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="35fe1-103">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="35fe1-104">Servicios de datos de WCF le permite limitar el número de entidades devueltas por una consulta de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="35fe1-104">WCF Data Services enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="35fe1-105">Los límites de página se definen en el método que se llama cuando se inicializa el servicio y se pueden establecer por separado para cada conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="35fe1-105">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="35fe1-106">Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente.</span><span class="sxs-lookup"><span data-stu-id="35fe1-106">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="35fe1-107">Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fe1-107">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="35fe1-108">En este tema se muestra cómo modificar un servicio de datos para habilitar la paginación de los conjuntos de entidades `Customers` y `Orders` devueltos.</span><span class="sxs-lookup"><span data-stu-id="35fe1-108">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="35fe1-109">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="35fe1-109">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="35fe1-110">Este servicio se crea cuando se completa la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35fe1-110">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="35fe1-111">Cómo habilitar la paginación de los conjuntos de entidades Customers y Orders devueltos</span><span class="sxs-lookup"><span data-stu-id="35fe1-111">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
- <span data-ttu-id="35fe1-112">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="35fe1-112">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="35fe1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="35fe1-113">See also</span></span>

- [<span data-ttu-id="35fe1-114">Carga de contenido diferido</span><span class="sxs-lookup"><span data-stu-id="35fe1-114">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="35fe1-115">Procedimiento para cargar resultados paginados</span><span class="sxs-lookup"><span data-stu-id="35fe1-115">How to: Load Paged Results</span></span>](how-to-load-paged-results-wcf-data-services.md)
