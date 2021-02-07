---
description: 'Más información acerca de: llamadas por segundo'
title: Llamadas por segundo
ms.date: 03/30/2017
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
ms.openlocfilehash: 1d204e4c88d9f9ab113e59c76f1eaecc280e552e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759658"
---
# <a name="calls-per-second"></a>Llamadas por segundo

Nombre del contador: llamadas por segundo  
  
## <a name="description"></a>Descripción  

 Número de llamadas a esta operación en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
