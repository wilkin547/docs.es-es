---
title: 'punto de conexión: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271258"
---
# <a name="endpoint-calls-failed-per-second"></a>punto de conexión: Errores en llamadas por segundo

Nombre del contador: Errores de llamadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.  
  
## <a name="see-also"></a>Vea también

- [Especificación y administración de errores en contratos y servicios](../../specifying-and-handling-faults-in-contracts-and-services.md)
