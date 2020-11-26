---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 180a06efc94acba40806e1f5d661553127549596
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248492"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="96450-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="96450-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="96450-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="96450-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="96450-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="96450-104">Description</span></span>  

 <span data-ttu-id="96450-105">El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="96450-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="96450-106">El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.</span><span class="sxs-lookup"><span data-stu-id="96450-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="96450-107">Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="96450-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="96450-108">No se realiza un seguimiento de los cambios subsiguientes hasta 0.</span><span class="sxs-lookup"><span data-stu-id="96450-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="96450-109">Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.</span><span class="sxs-lookup"><span data-stu-id="96450-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96450-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="96450-110">See also</span></span>

- [<span data-ttu-id="96450-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="96450-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="96450-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="96450-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="96450-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="96450-113">Administration and Diagnostics</span></span>](../index.md)
