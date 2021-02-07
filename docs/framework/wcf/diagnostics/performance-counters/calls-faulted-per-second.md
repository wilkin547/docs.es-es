---
description: 'Más información sobre: errores de llamadas por segundo'
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: cbff7b24d2aa457bdbe3c600109f24c9672c7ab2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759684"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="738af-103">Errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="738af-103">Calls Faulted Per Second</span></span>

<span data-ttu-id="738af-104">Nombre del contador: errores de llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="738af-104">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="738af-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="738af-105">Description</span></span>  

 <span data-ttu-id="738af-106">Número de llamadas que devolvieron errores a esta operación en un segundo.</span><span class="sxs-lookup"><span data-stu-id="738af-106">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="738af-107">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="738af-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="738af-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="738af-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="738af-109">En las aplicaciones Windows Communication Foundation (WCF), los métodos de servicio comunican la información de errores de procesamiento mediante mensajes de error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="738af-109">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="738af-110">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="738af-110">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="738af-111">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="738af-111">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738af-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="738af-112">See also</span></span>

- [<span data-ttu-id="738af-113">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="738af-113">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
