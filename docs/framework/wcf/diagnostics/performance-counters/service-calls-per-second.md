---
title: 'Servicio: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773370"
---
# <a name="service-calls-per-second"></a>Servicio: Llamadas por segundo
Nombre del contador: Llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 El número de llamadas por segundo a este servicio.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F), donde el numerador (N) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador (D) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.
