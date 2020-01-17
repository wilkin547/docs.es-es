---
title: 'Extremo: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: d639d881bcedd336c7bbabd28ec385f60ff54d43
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163792"
---
# <a name="endpoint-calls-per-second"></a>Extremo: Llamadas por segundo
Nombre del contador: llamadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número de llamadas a este punto de conexión en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
