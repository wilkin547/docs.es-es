---
title: Errores de llamadas por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321123"
---
# <a name="calls-failed-per-second"></a>Errores de llamadas por segundo
Nombre de contador: errores de llamadas por segundo  
  
## <a name="description"></a>Descripción  
 Número de llamadas con excepciones no atendidas en esta operación en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Este contador se incrementa cada vez que hay una excepción no controlada en esta operación.  
  
## <a name="see-also"></a>Vea también

- [Especificación y gestión de errores en contratos y servicios](../../specifying-and-handling-faults-in-contracts-and-services.md)
