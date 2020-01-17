---
title: Instancias por segundo
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: 3ae0b83066b22187ce062596a62e9d17aa2acd45
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163805"
---
# <a name="instances-per-second"></a>Instancias por segundo
Nombre de contador: Instancias creadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de instancias del servicio creadas en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
