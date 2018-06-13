---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: a6b4e369d2d22d2441b3896321b7c152e21d967b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483336"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="2ad03-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="2ad03-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="2ad03-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="2ad03-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="2ad03-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ad03-104">Description</span></span>  
 <span data-ttu-id="2ad03-105">El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="2ad03-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="2ad03-106">El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.</span><span class="sxs-lookup"><span data-stu-id="2ad03-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="2ad03-107">Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="2ad03-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="2ad03-108">No se realiza un seguimiento de los cambios subsiguientes hasta 0.</span><span class="sxs-lookup"><span data-stu-id="2ad03-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="2ad03-109">Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.</span><span class="sxs-lookup"><span data-stu-id="2ad03-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad03-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad03-110">See Also</span></span>  
 [<span data-ttu-id="2ad03-111">Traza</span><span class="sxs-lookup"><span data-stu-id="2ad03-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2ad03-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2ad03-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2ad03-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2ad03-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
