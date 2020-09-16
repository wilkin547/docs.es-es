---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: a50d1881040f248d7c58e82ce2e477b51591c2f3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553589"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="5756d-102">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5756d-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="5756d-103">Nombre del contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5756d-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5756d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="5756d-104">Description</span></span>  
 <span data-ttu-id="5756d-105">Número de llamadas que devolvieron errores a esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="5756d-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="5756d-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="5756d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5756d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5756d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="5756d-108">En las aplicaciones Windows Communication Foundation (WCF), los métodos de servicio comunican la información de errores de procesamiento mediante mensajes de error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="5756d-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="5756d-109">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="5756d-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="5756d-110">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="5756d-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5756d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5756d-111">See also</span></span>

- [<span data-ttu-id="5756d-112">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="5756d-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
