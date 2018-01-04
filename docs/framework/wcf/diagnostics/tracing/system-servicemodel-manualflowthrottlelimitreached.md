---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f149423fc8c0cd2a25834742d7c8b79ad8d8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="eb326-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="eb326-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="eb326-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="eb326-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="eb326-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb326-104">Description</span></span>  
 <span data-ttu-id="eb326-105">El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="eb326-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="eb326-106">El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.</span><span class="sxs-lookup"><span data-stu-id="eb326-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="eb326-107">Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="eb326-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="eb326-108">No se realiza un seguimiento de los cambios subsiguientes hasta 0.</span><span class="sxs-lookup"><span data-stu-id="eb326-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="eb326-109">Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.</span><span class="sxs-lookup"><span data-stu-id="eb326-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb326-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb326-110">See Also</span></span>  
 [<span data-ttu-id="eb326-111">Traza</span><span class="sxs-lookup"><span data-stu-id="eb326-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="eb326-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="eb326-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="eb326-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="eb326-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
