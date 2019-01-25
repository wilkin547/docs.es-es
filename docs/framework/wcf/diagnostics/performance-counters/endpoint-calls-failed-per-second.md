---
title: 'Punto de conexión: Errores de llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 03fbdd83246fa811424f445823f705a3bef5697a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608042"
---
# <a name="endpoint-calls-failed-per-second"></a>Punto de conexión: Errores de llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de llamadas que tienen excepciones no controladas y son recibidas por este punto de conexión en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Este contador se incrementa siempre que se produce una excepción no controlada en este punto de conexión.  
  
## <a name="see-also"></a>Vea también
- [Especificación y gestión de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
