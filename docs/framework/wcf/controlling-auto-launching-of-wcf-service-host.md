---
title: Controlar inicio automático del host de servicio de WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320624"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controlar inicio automático del host de servicio de WCF
Puede controlar la capacidad de inicio automático del host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost. exe) para un proyecto de biblioteca de servicios WCF, al depurar otro proyecto en la misma solución de Visual Studio que contiene varios proyectos.  
  
 Para ello, haga clic con el botón secundario en el proyecto de servicio WCF en **Explorador de soluciones**, elija **propiedades**y haga clic en la pestaña **Opciones de WCF** . La casilla **iniciar el host del servicio WCF al depurar otro proyecto en la misma solución** está habilitada de forma predeterminada. Puede desactivar la casilla para que el host del servicio WCF para este proyecto específico no se inicie cuando se depure otro proyecto en la misma solución.  
  
 Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.  
  
 Esta opción está disponible para los proyectos siguientes:  
  
- Proyecto de biblioteca de servicio WCF.  
  
- Proyecto de biblioteca de servicio de flujo de trabajo secuencial.  
  
- Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.  
  
- Proyecto de biblioteca de servicio de distribución.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
