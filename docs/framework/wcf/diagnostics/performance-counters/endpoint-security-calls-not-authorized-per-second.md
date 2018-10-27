---
title: 'punto de conexión: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: c62bec570daf8b107ca0540871eb6eac43ca2d7e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188357"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a>punto de conexión: Llamadas de seguridad no autorizadas por segundo
Nombre del contador: llamadas de seguridad no autorizadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.  
  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
