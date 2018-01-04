---
title: "Controlar inicio automático del host de servicio de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="a21ab-102">Controlar inicio automático del host de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="a21ab-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="a21ab-103">Puede controlar la capacidad de inicio automático del host de servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfSvcHost.exe) para un proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] al depurar otro proyecto de la misma solución de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contiene varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="a21ab-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="a21ab-104">Para ello, haga clic en el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proyecto de servicio en **el Explorador de soluciones**, elija **propiedades**y haga clic en **opciones de WCF** ficha. El **iniciar cuando se depure otro proyecto en la misma solución el Host de servicio de WCF** casilla de verificación está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a21ab-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="a21ab-105">Puede desactivarla para que no se inicie el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para este proyecto concreto cuando se depure otro proyecto en la misma solución.</span><span class="sxs-lookup"><span data-stu-id="a21ab-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="a21ab-106">Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="a21ab-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="a21ab-107">Esta opción está disponible para los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a21ab-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="a21ab-108">Proyecto de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a21ab-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library Project.</span></span>  
  
-   <span data-ttu-id="a21ab-109">Proyecto de biblioteca de servicio de flujo de trabajo secuencial.</span><span class="sxs-lookup"><span data-stu-id="a21ab-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="a21ab-110">Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="a21ab-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="a21ab-111">Proyecto de biblioteca de servicio de distribución.</span><span class="sxs-lookup"><span data-stu-id="a21ab-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21ab-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a21ab-112">See Also</span></span>  
 [<span data-ttu-id="a21ab-113">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a21ab-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
