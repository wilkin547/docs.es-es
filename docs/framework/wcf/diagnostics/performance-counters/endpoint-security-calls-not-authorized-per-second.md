---
title: 'Extremo: Llamadas de seguridad no autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 8c287ef4c156bb0a76a4b1d08b0d70b40bd76229
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163181"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a>Extremo: Llamadas de seguridad no autorizadas por segundo
Nombre del contador: llamadas de seguridad no autorizadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de mensajes entrantes en un segundo, que son de un usuario válido y protegidos correctamente, pero el usuario no está autorizado para realizar tareas específicas.  
  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
