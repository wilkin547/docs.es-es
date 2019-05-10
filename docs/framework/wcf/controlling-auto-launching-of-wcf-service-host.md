---
title: Controlar inicio automático del host de servicio de WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 806d85df2a7fff63704db755400b81cc2dc5c37b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652086"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Controlar inicio automático del host de servicio de WCF
Puede controlar la capacidad de inicio automático del Host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost.exe) para un proyecto de biblioteca de servicios WCF al depurar otro proyecto en la misma solución de Visual Studio que contiene varios proyectos.  
  
 Para ello, haga clic en el proyecto de servicio WCF en **el Explorador de soluciones**, elija **propiedades**y haga clic en **opciones WCF** ficha. El **iniciar Host del servicio WCF al depurar otro proyecto en la misma solución** casilla de verificación está habilitada de forma predeterminada. Puede desactivar la casilla para que no se inicie el Host de servicio WCF para este proyecto concreto cuando se depure otro proyecto en la misma solución.  
  
 Este comportamiento no afecta a la depuración de F5 o a las funcionalidades de Agregar referencia de servicio para este proyecto.  
  
 Esta opción está disponible para los proyectos siguientes:  
  
- Proyecto de biblioteca de servicio WCF.  
  
- Proyecto de biblioteca de servicio de flujo de trabajo secuencial.  
  
- Proyecto de biblioteca de servicio de flujo de trabajo de equipo de estado.  
  
- Proyecto de biblioteca de servicio de distribución.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
