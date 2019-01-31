---
title: 'Solución del problema: depuración de servicios de Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: cdffb3a8ce9c5119a0a17a8bc7e6ca78276423f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745680"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="7bcb2-102">Solución del problema: depuración de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="7bcb2-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="7bcb2-103">Cuando depura una aplicación de servicio de Windows, el servicio y el **Administrador de servicios de Windows** interactúan.</span><span class="sxs-lookup"><span data-stu-id="7bcb2-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="7bcb2-104">**Service Manager** inicia el servicio mediante una llamada al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y espera 30 segundos a que vuelva el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bcb2-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="7bcb2-105">Si el método no vuelve en este tiempo, el administrador muestra un error que indica que el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="7bcb2-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="7bcb2-106">Cuando se depura el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> como se describe en [Cómo: Depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe tener en cuenta este período de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="7bcb2-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="7bcb2-107">Si coloca un punto de interrupción en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y no lo supera en 30 segundos, el administrador no iniciará el servicio.</span><span class="sxs-lookup"><span data-stu-id="7bcb2-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcb2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bcb2-108">See also</span></span>
- [<span data-ttu-id="7bcb2-109">Cómo: Depurar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="7bcb2-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="7bcb2-110">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="7bcb2-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
