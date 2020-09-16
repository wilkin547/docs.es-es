---
title: Operaciones de transacción anuladas por segundo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: bf7d13f04f0bad315c879f1b4299a78e9515cc56
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550656"
---
# <a name="transacted-operations-aborted-per-second"></a>Operaciones de transacción anuladas por segundo
Nombre del contador: operaciones de transacción anuladas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de operaciones transaccionales anuladas en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
