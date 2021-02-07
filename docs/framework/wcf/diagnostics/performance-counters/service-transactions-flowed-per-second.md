---
description: 'Más información acerca de: servicio: flujo de transacciones por segundo'
title: 'Servicio: flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: aae78853272b46a97ce25a710039661f36bf7079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759502"
---
# <a name="service-transactions-flowed-per-second"></a>Servicio: flujo de transacciones por segundo

Nombre del contador: flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  

 Número de transacciones que fluyen a las operaciones de este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
