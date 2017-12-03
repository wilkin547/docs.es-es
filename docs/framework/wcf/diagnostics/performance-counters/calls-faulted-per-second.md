---
title: Errores de llamadas por segundo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffb4d00166c3a2d9fcb921f053bcfb7fde0dade9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="f95c5-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="f95c5-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="f95c5-103">Nombre del contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="f95c5-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f95c5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="f95c5-104">Description</span></span>  
 <span data-ttu-id="f95c5-105">Número de llamadas que devolvieron errores a esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="f95c5-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="f95c5-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="f95c5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f95c5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f95c5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="f95c5-108">En las aplicaciones [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], los métodos de servicio comunican la información sobre errores de procesamiento mediante mensajes de error SOAP.</span><span class="sxs-lookup"><span data-stu-id="f95c5-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="f95c5-109">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="f95c5-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="f95c5-110">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="f95c5-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f95c5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f95c5-111">See Also</span></span>  
 [<span data-ttu-id="f95c5-112">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="f95c5-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
