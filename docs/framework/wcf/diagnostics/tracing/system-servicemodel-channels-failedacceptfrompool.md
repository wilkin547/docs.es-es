---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: de0bdd9e5ab922b09249bf550fde745042be8e58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156486"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
Error en un intento para usar de nuevo una conexión agrupada. Se realiza otro intento dentro del período de tiempo de espera especificado.  
  
## <a name="description"></a>Descripción  
 Este seguimiento de información indica que se ha producido un error mientras se intentaba reutilizar una conexión de grupo. Esto podría haber pasado porque la conexión de grupo no era compatible, no estaba preparada o estaba aún activa. Hay un tiempo establecido para realizar intentos adicionales de reutilizar otra conexión de grupo, y en caso de que no se encuentren conexiones utilizables, se crea una nueva.  
  
## <a name="see-also"></a>Vea también

- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
