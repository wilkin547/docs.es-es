---
description: 'Más información acerca de: instancias por segundo'
title: Instancias por segundo
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: cfcdd85bef8b1873101c1bbb63ce40bd161a97f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655310"
---
# <a name="instances-per-second"></a>Instancias por segundo

Nombre de contador: Instancias creadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número de instancias del servicio creadas en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
