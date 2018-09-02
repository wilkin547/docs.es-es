---
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467479"
---
# <a name="transacted-operations-committed-per-second"></a>Operaciones de transacción confirmadas por segundo
Nombre del contador: Operaciones de transacción confirmadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de operaciones transaccionales confirmadas en este servicio cada segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
