---
title: 'Servicio: Errores en llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: e165348a71101b21fa66bd4907c43335b1e476e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163987"
---
# <a name="service-calls-failed-per-second"></a>Servicio: Errores en llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 El contador se incrementa cada vez que hay una excepción no atendida en este servicio.  
  
## <a name="see-also"></a>Vea también

- [Especificación y gestión de errores en contratos y servicios](../../specifying-and-handling-faults-in-contracts-and-services.md)
