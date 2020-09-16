---
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553797"
---
# <a name="endpoint-transactions-flowed-per-second"></a>punto de conexión: Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  
 Número de transacciones de flujo a las operaciones en este extremo en un segundo. Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
