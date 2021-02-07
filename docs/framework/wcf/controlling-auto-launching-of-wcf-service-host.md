---
description: Más información acerca de cómo controlar el inicio automático del host de servicio WCF
title: Controlar inicio automático del host de servicio de WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f0e9a4e79a403920c0bc6a512b30fb038b2aa1f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677397"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="5e03e-103">Controlar inicio automático del host de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="5e03e-103">Controlling Auto-launching of WCF Service Host</span></span>

<span data-ttu-id="5e03e-104">Puede controlar la capacidad de inicio automático del host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost.exe) para un proyecto de biblioteca de servicios WCF, al depurar otro proyecto en la misma solución de Visual Studio que contiene varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="5e03e-104">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="5e03e-105">Para ello, haga clic con el botón secundario en el proyecto de servicio WCF en **Explorador de soluciones**, elija **propiedades** y haga clic en la pestaña **Opciones de WCF** . La casilla **iniciar el host del servicio WCF al depurar otro proyecto en la misma solución** está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e03e-105">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="5e03e-106">Puede desactivar la casilla para que el host del servicio WCF para este proyecto específico no se inicie cuando se depure otro proyecto en la misma solución.</span><span class="sxs-lookup"><span data-stu-id="5e03e-106">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="5e03e-107">Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="5e03e-107">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="5e03e-108">Esta opción está disponible para los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e03e-108">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="5e03e-109">Proyecto de biblioteca de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="5e03e-109">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="5e03e-110">Proyecto de biblioteca de servicio de flujo de trabajo secuencial.</span><span class="sxs-lookup"><span data-stu-id="5e03e-110">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="5e03e-111">Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="5e03e-111">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="5e03e-112">Proyecto de biblioteca de servicio de distribución.</span><span class="sxs-lookup"><span data-stu-id="5e03e-112">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e03e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e03e-113">See also</span></span>

- [<span data-ttu-id="5e03e-114">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="5e03e-114">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
