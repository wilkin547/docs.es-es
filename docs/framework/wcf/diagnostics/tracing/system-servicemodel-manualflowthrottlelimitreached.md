---
description: 'Más información sobre: System. ServiceModel. ManualFlowThrottleLimitReached'
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 90c911131259ea02023eb05a97793f00f3eb43fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99633340"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="82a34-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="82a34-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="82a34-104">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="82a34-104">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="82a34-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="82a34-105">Description</span></span>  

 <span data-ttu-id="82a34-106">El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="82a34-106">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="82a34-107">El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.</span><span class="sxs-lookup"><span data-stu-id="82a34-107">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="82a34-108">Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="82a34-108">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="82a34-109">No se realiza un seguimiento de los cambios subsiguientes hasta 0.</span><span class="sxs-lookup"><span data-stu-id="82a34-109">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="82a34-110">Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.</span><span class="sxs-lookup"><span data-stu-id="82a34-110">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a34-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a34-111">See also</span></span>

- [<span data-ttu-id="82a34-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="82a34-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="82a34-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="82a34-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="82a34-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="82a34-114">Administration and Diagnostics</span></span>](../index.md)
