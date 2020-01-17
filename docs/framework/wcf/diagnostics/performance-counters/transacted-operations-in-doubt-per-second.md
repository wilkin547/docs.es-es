---
title: Operaciones de transacción dudosas por segundo
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: bc978f5b45352fa9fcce5aee5a616c9f86f56aeb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163844"
---
# <a name="transacted-operations-in-doubt-per-second"></a>Operaciones de transacción dudosas por segundo
Nombre del contador: Operaciones de transacción en duda por segundo.  
  
## <a name="description"></a>Descripción  
 El número de operaciones de transacción con un resultado en duda en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
