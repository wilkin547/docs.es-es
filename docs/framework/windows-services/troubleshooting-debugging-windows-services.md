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
ms.workload: dotnet
ms.openlocfilehash: f38e65e93d4e6668795bf254573993d5100e2328
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-debugging-windows-services"></a>Solución de problemas: depurar servicios de Windows
Cuando se depura una aplicación de servicio de Windows, el servicio y el **Windows Service Manager** interactuar. El **Service Manager** inicia el servicio mediante una llamada a la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y, a continuación, espera a 30 segundos para la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método devuelva un valor. Si el método no devuelve en este momento, el administrador muestra un error que no se puede iniciar el servicio.  
  
 Cuando se depura el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método tal como se describe en [Cómo: depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe ser consciente de este período de 30 segundos. Si coloca un punto de interrupción en el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y no avanza antes de 30 segundos, el administrador no iniciará el servicio.  
  
## <a name="see-also"></a>Vea también  
 [Depuración de aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
