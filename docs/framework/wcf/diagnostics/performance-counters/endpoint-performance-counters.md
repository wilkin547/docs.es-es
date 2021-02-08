---
description: 'Más información acerca de: contadores de rendimiento del punto de conexión'
title: Contadores de rendimiento del extremo
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 60cd94d5d954c87f4b37469688ee809a13fa3cb4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771241"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="810bf-103">Contadores de rendimiento del extremo</span><span class="sxs-lookup"><span data-stu-id="810bf-103">Endpoint Performance Counters</span></span>

<span data-ttu-id="810bf-104">Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes.</span><span class="sxs-lookup"><span data-stu-id="810bf-104">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="810bf-105">Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="810bf-105">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="810bf-106">Las instancias se denominan utilizando este patrón:</span><span class="sxs-lookup"><span data-stu-id="810bf-106">The instances are named using this pattern:</span></span>  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 <span data-ttu-id="810bf-107">Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="810bf-107">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="810bf-108">Hay un límite en la longitud del nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="810bf-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="810bf-109">Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.</span><span class="sxs-lookup"><span data-stu-id="810bf-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810bf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="810bf-110">See also</span></span>

- [<span data-ttu-id="810bf-111">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="810bf-111">Performance Counters</span></span>](index.md)
