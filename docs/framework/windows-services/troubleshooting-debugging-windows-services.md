---
title: 'Solución del problema: depuración de servicios de Windows'
description: Introducción a la depuración de servicios de Windows. Cuando depura una aplicación de servicio de Windows, se produce la interacción entre el servicio y el Administrador de servicios de Windows.
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
ms.openlocfilehash: 2c1180ef8e3e44c50f10a263d86dcae830d9cd0e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270398"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="ca9fe-104">Solución del problema: depuración de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="ca9fe-104">Troubleshooting: Debugging Windows Services</span></span>

<span data-ttu-id="ca9fe-105">Cuando depura una aplicación de servicio de Windows, el servicio y el **Administrador de servicios de Windows** interactúan.</span><span class="sxs-lookup"><span data-stu-id="ca9fe-105">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="ca9fe-106">**Service Manager** inicia el servicio mediante una llamada al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y espera 30 segundos a que vuelva el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca9fe-106">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="ca9fe-107">Si el método no vuelve en este tiempo, el administrador muestra un error que indica que el servicio no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="ca9fe-107">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="ca9fe-108">Cuando se depura el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> como se describe en [Cómo: Depurar aplicaciones de servicios de Windows](how-to-debug-windows-service-applications.md), debe tener en cuenta este período de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="ca9fe-108">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="ca9fe-109">Si coloca un punto de interrupción en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y no lo supera en 30 segundos, el administrador no iniciará el servicio.</span><span class="sxs-lookup"><span data-stu-id="ca9fe-109">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9fe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca9fe-110">See also</span></span>

- [<span data-ttu-id="ca9fe-111">Cómo: Depurar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="ca9fe-111">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="ca9fe-112">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="ca9fe-112">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
