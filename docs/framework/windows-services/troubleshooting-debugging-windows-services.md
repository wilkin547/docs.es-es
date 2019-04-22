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
ms.openlocfilehash: 0552fc005a25e83065bb44e425770f9cef84f71b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082586"
---
# <a name="troubleshooting-debugging-windows-services"></a>Solución del problema: depuración de servicios de Windows
Cuando depura una aplicación de servicio de Windows, el servicio y el **Administrador de servicios de Windows** interactúan. **Service Manager** inicia el servicio mediante una llamada al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y espera 30 segundos a que vuelva el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Si el método no vuelve en este tiempo, el administrador muestra un error que indica que el servicio no se puede iniciar.  
  
 Cuando se depura el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> como se describe en [Cómo: Depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), debe tener en cuenta este período de 30 segundos. Si coloca un punto de interrupción en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y no lo supera en 30 segundos, el administrador no iniciará el servicio.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Depurar aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
