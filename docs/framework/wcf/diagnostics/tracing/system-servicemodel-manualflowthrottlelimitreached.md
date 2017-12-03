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
ms.openlocfilehash: 49b41e27847005c7187435229e030994df10df26
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="8c5ed-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="8c5ed-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="8c5ed-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="8c5ed-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="8c5ed-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c5ed-104">Description</span></span>  
 <span data-ttu-id="8c5ed-105">El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="8c5ed-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="8c5ed-106">El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.</span><span class="sxs-lookup"><span data-stu-id="8c5ed-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="8c5ed-107">Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="8c5ed-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="8c5ed-108">No se realiza un seguimiento de los cambios subsiguientes hasta 0.</span><span class="sxs-lookup"><span data-stu-id="8c5ed-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="8c5ed-109">Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.</span><span class="sxs-lookup"><span data-stu-id="8c5ed-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5ed-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c5ed-110">See Also</span></span>  
 [<span data-ttu-id="8c5ed-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="8c5ed-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8c5ed-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="8c5ed-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8c5ed-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8c5ed-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
