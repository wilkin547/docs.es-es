---
title: 'Servicio: Errores de llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167497"
---
# <a name="service-calls-failed-per-second"></a>Servicio: Errores de llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de llamadas que tienen excepciones no controladas y que son recibidas por este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 En código administrado, las excepciones se inician al producirse condiciones de error.  
  
 El contador se incrementa cada vez que hay una excepción no atendida en este servicio.  
  
## <a name="see-also"></a>Vea también

- [Especificación y gestión de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
