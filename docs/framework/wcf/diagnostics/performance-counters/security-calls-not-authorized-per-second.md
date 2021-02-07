---
description: 'Más información acerca de: llamadas de seguridad no autorizadas por segundo'
title: Llamadas de seguridad no autorizadas por segundo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 60e1baf2b1ed1f3dc502608e6667266608010f0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716216"
---
# <a name="security-calls-not-authorized-per-second"></a>Llamadas de seguridad no autorizadas por segundo

Nombre del contador: llamadas de seguridad no autorizadas por segundo.  
  
## <a name="description"></a>Descripción  

 El número de llamadas que no pudieron autorizarse en esta operación en un segundo.  
  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
