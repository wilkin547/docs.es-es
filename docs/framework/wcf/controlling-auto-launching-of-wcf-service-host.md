---
title: Controlar inicio automático del host de servicio de WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2fa060e567fba9bb5e6344b2c8fc67fb639ad0f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228502"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controlar inicio automático del host de servicio de WCF
Puede controlar la capacidad de inicio automático del Host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost.exe) para un proyecto de biblioteca de servicios WCF al depurar otro proyecto en la misma solución de Visual Studio que contiene varios proyectos.  
  
 Para ello, haga clic en el proyecto de servicio WCF en **el Explorador de soluciones**, elija **propiedades**y haga clic en **opciones WCF** ficha. El **iniciar Host del servicio WCF al depurar otro proyecto en la misma solución** casilla de verificación está habilitada de forma predeterminada. Puede desactivar la casilla para que no se inicie el Host de servicio WCF para este proyecto concreto cuando se depure otro proyecto en la misma solución.  
  
 Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.  
  
 Esta opción está disponible para los proyectos siguientes:  
  
-   Proyecto de biblioteca de servicio WCF.  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo secuencial.  
  
-   Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.  
  
-   Proyecto de biblioteca de servicio de distribución.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
