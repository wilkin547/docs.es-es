---
title: Flujo de transacciones por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552211"
---
# <a name="transactions-flowed-per-second"></a>Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo  
  
## <a name="description"></a>Descripción  
 Número de transacciones en esta operación en un segundo. Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
