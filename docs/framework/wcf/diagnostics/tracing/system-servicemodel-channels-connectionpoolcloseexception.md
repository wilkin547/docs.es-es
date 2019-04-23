---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182200"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
Se produjo una excepción al cerrar las conexiones de este grupo de conexiones.  
  
## <a name="description"></a>Descripción  
 Este seguimiento de nivel de error indica que se ha producido un error al cerrar los grupos de conexiones utilizados por la característica de agrupación de conexiones de Windows Communication Foundation (WCF). Una posible razón para que esto suceda es el cierre incorrecto de una conexión agrupada o un conjunto de conexiones agrupadas dentro del CloseTimeout. Cuando se produce esta excepción, se anula cualquier conexión que permanezca abierta dentro de ese grupo y se abandonan las conexiones abiertas dentro de otros grupos.  
  
## <a name="see-also"></a>Vea también

- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
