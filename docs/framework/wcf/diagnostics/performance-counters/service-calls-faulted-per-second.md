---
title: 'Servicio: Errores en las llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: b4a8a1eeec13195e4f8fe088da14dff7c06ecdb3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44127938"
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="fa18b-102">Servicio: Errores en las llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="fa18b-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="fa18b-103">Nombre del contador: Errores de llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="fa18b-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fa18b-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa18b-104">Description</span></span>  
 <span data-ttu-id="fa18b-105">Número de llamadas que han devuelto errores a este servicio en un segundo.</span><span class="sxs-lookup"><span data-stu-id="fa18b-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="fa18b-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="fa18b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fa18b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="fa18b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="fa18b-108">En las aplicaciones de Windows Communication Foundation (WCF), los métodos de servicio comunican información de errores de procesamiento mediante mensajes de error SOAP.</span><span class="sxs-lookup"><span data-stu-id="fa18b-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="fa18b-109">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="fa18b-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="fa18b-110">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="fa18b-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa18b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa18b-111">See Also</span></span>  
 [<span data-ttu-id="fa18b-112">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="fa18b-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
