---
description: 'Más información acerca de: operaciones de transacción confirmadas por segundo'
title: Operaciones de transacción confirmadas por segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 019906cccc527a032d91eb20328eddbb6d9aada8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655089"
---
# <a name="transacted-operations-committed-per-second"></a>Operaciones de transacción confirmadas por segundo

Nombre del contador: Operaciones de transacción confirmadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número de operaciones transaccionales confirmadas en este servicio cada segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
