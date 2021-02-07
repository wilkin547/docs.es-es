---
description: 'Más información sobre: errores en las sesiones de mensajería de confianza por segundo'
title: Errores en sesiones de mensajería de confianza por segundo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 11759ad659d9e860c94b4428091fc0852ebf038c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716294"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Errores en sesiones de mensajería de confianza por segundo

Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.  
  
## <a name="description"></a>Descripción  

 Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
