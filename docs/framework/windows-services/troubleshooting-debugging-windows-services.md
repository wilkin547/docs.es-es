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
ms.openlocfilehash: cbedb0051cbb08c2875e145a2bad35ae4d02a74e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053508"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="fe372-102">Solución del problema: depuración de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="fe372-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="fe372-103">Cuando depura una aplicación de servicio de Windows, el servicio y el **Administrador de servicios de Windows** interactúan.</span><span class="sxs-lookup"><span data-stu-id="fe372-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="fe372-104">**Service Manager** inicia el servicio mediante una llamada al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y espera 30 segundos a que vuelva el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="fe372-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="fe372-105">Si el método no vuelve en este tiempo, el administrador muestra un error que indica que el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="fe372-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="fe372-106">Cuando se depura el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> como se describe en [Cómo: Depurar aplicaciones de servicios de Windows](how-to-debug-windows-service-applications.md), debe tener en cuenta este período de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="fe372-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="fe372-107">Si coloca un punto de interrupción en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y no lo supera en 30 segundos, el administrador no iniciará el servicio.</span><span class="sxs-lookup"><span data-stu-id="fe372-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe372-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe372-108">See also</span></span>

- [<span data-ttu-id="fe372-109">Cómo: Depurar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="fe372-109">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="fe372-110">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="fe372-110">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
