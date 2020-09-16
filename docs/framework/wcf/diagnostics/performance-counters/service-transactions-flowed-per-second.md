---
title: 'Servicio: flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 2ed9f6711c998bbd3f1130b9a91d8ac850821a07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559329"
---
# <a name="service-transactions-flowed-per-second"></a>Servicio: flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  
 Número de transacciones que fluyen a las operaciones de este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
