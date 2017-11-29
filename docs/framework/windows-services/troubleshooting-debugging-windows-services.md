---
title: "Solución de problemas: depurar servicios de Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="bccb0-102">Solución de problemas: depurar servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="bccb0-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="bccb0-103">Cuando se depura una aplicación de servicio de Windows, el servicio y el **Windows Service Manager** interactuar.</span><span class="sxs-lookup"><span data-stu-id="bccb0-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="bccb0-104">El **Service Manager** inicia el servicio mediante una llamada a la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y, a continuación, espera a 30 segundos para la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="bccb0-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="bccb0-105">Si el método no devuelve en este momento, el administrador muestra un error que no se puede iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bccb0-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="bccb0-106">Cuando se depura el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método tal como se describe en [Cómo: depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe ser consciente de este período de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="bccb0-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="bccb0-107">Si coloca un punto de interrupción en el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y no avanza antes de 30 segundos, el administrador no iniciará el servicio.</span><span class="sxs-lookup"><span data-stu-id="bccb0-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccb0-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccb0-108">See Also</span></span>  
 [<span data-ttu-id="bccb0-109">Cómo: depurar aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="bccb0-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="bccb0-110">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="bccb0-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
