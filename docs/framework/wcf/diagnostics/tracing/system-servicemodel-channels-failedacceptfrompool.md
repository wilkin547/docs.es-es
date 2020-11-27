---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 8615cca7d4ed8ea1f40baa9502e7136d4349eb9c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256318"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool

Error en un intento para usar de nuevo una conexión agrupada. Se realiza otro intento dentro del período de tiempo de espera especificado.  
  
## <a name="description"></a>Descripción  

 Este seguimiento de información indica que se ha producido un error mientras se intentaba reutilizar una conexión de grupo. Esto podría haber pasado porque la conexión de grupo no era compatible, no estaba preparada o estaba aún activa. Hay un tiempo establecido para realizar intentos adicionales de reutilizar otra conexión de grupo, y en caso de que no se encuentren conexiones utilizables, se crea una nueva.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
