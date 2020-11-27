---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286960"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException

Se produjo una excepción al cerrar las conexiones de este grupo de conexiones.  
  
## <a name="description"></a>Descripción  

 Este seguimiento de nivel de error indica que se ha producido un error al cerrar los grupos de conexiones usados por la característica de agrupación de conexiones de Windows Communication Foundation (WCF). Una posible razón para que esto suceda es el cierre incorrecto de una conexión agrupada o un conjunto de conexiones agrupadas dentro del CloseTimeout. Cuando se produce esta excepción, se anula cualquier conexión que permanezca abierta dentro de ese grupo y se abandonan las conexiones abiertas dentro de otros grupos.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
