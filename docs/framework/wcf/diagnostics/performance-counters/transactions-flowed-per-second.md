---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392941"
---
# <a name="transactions-flowed-per-second"></a>Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo  
  
## <a name="description"></a>Descripción  
 Número de transacciones en esta operación en un segundo. Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
