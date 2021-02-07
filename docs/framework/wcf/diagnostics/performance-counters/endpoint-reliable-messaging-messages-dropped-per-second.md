---
description: 'Más información acerca de: punto de conexión: mensajes de mensajería de confianza quitados por segundo'
title: 'Extremo: mensajes de mensajería de confianza quitados por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 257ea74aeb23ef8962ce8910dee635b83f76d960
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735886"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Extremo: mensajes de mensajería de confianza quitados por segundo

Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.  
  
## <a name="description"></a>Descripción  

 Número total de mensajes de mensajería de confianza quitados en este punto de conexión en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
