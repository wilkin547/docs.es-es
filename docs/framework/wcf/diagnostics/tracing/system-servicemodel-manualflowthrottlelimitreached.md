---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 180a06efc94acba40806e1f5d661553127549596
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248492"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a>System.ServiceModel.ManualFlowThrottleLimitReached

System.ServiceModel.ManualFlowThrottleLimitReached  
  
## <a name="description"></a>Descripción  

 El sistema alcanzó el límite establecido para el acelerador de ManualFlowControlLimit. El valor de acelerador se puede cambiar modificando la propiedad ManualFlowControlLimit en ServiceHost o InstanceContext, según sea aplicable.  
  
 Se emite este seguimiento cuando el límite del control de flujo manual se reduce inicialmente a 0. No se realiza un seguimiento de los cambios subsiguientes hasta 0. Para cada contexto se realiza un seguimiento del límite del control de flujo en el contexto de la instancia.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
