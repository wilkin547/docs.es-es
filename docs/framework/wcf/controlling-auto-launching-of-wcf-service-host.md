---
title: Controlar inicio automático del host de servicio de WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f7f58a684449819fe945ad1ba5bff12f425c8294
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712397"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="bf28d-102">Controlar inicio automático del host de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="bf28d-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="bf28d-103">Puede controlar la capacidad de inicio automático del Host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost.exe) para un proyecto de biblioteca de servicios WCF al depurar otro proyecto en la misma solución de Visual Studio que contiene varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="bf28d-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="bf28d-104">Para ello, haga clic en el proyecto de servicio WCF en **el Explorador de soluciones**, elija **propiedades**y haga clic en **opciones WCF** ficha. El **iniciar Host del servicio WCF al depurar otro proyecto en la misma solución** casilla de verificación está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bf28d-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="bf28d-105">Puede desactivar la casilla para que no se inicie el Host de servicio WCF para este proyecto concreto cuando se depure otro proyecto en la misma solución.</span><span class="sxs-lookup"><span data-stu-id="bf28d-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="bf28d-106">Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="bf28d-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="bf28d-107">Esta opción está disponible para los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf28d-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="bf28d-108">Proyecto de biblioteca de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="bf28d-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="bf28d-109">Proyecto de biblioteca de servicio de flujo de trabajo secuencial.</span><span class="sxs-lookup"><span data-stu-id="bf28d-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="bf28d-110">Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="bf28d-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="bf28d-111">Proyecto de biblioteca de servicio de distribución.</span><span class="sxs-lookup"><span data-stu-id="bf28d-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf28d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf28d-112">See also</span></span>
- [<span data-ttu-id="bf28d-113">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="bf28d-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
