---
description: 'Más información acerca de: servicio: llamadas de seguridad no autorizadas por segundo'
title: 'Servicio: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 7203b62a1dd2f01aabd8502c992d357742ddc4e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635706"
---
# <a name="service-security-calls-not-authorized-per-second"></a>Servicio: Llamadas de seguridad no autorizadas por segundo

Nombre de contador: Llamadas de seguridad no autorizadas por segundo  
  
## <a name="description"></a>Descripción  

 Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.  
  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
