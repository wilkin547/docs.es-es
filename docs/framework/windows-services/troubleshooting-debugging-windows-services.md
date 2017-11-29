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
# <a name="troubleshooting-debugging-windows-services"></a>Solución de problemas: depurar servicios de Windows
Cuando se depura una aplicación de servicio de Windows, el servicio y el **Windows Service Manager** interactuar. El **Service Manager** inicia el servicio mediante una llamada a la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y, a continuación, espera a 30 segundos para la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método devuelva un valor. Si el método no devuelve en este momento, el administrador muestra un error que no se puede iniciar el servicio.  
  
 Cuando se depura el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método tal como se describe en [Cómo: depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe ser consciente de este período de 30 segundos. Si coloca un punto de interrupción en el <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método y no avanza antes de 30 segundos, el administrador no iniciará el servicio.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: depurar aplicaciones de servicio de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
