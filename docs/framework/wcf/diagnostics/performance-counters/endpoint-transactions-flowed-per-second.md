---
description: 'Más información acerca de: punto de conexión: flujo de transacciones por segundo'
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 96a122b97bce703b0a0e00c6e74f72c980253652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655362"
---
# <a name="endpoint-transactions-flowed-per-second"></a>punto de conexión: Flujo de transacciones por segundo

Nombre del contador: flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  

 Número de transacciones de flujo a las operaciones en este extremo en un segundo. Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
