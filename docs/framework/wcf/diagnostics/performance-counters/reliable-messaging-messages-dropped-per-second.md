---
title: Mensajes de mensajería de confianza quitados por segundo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 946e0408b8b6602bba7824b45e4d6cb91cdaa4eb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163961"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Mensajes de mensajería de confianza quitados por segundo
Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número total de mensajes de mensajería de confianza que han sido quitados en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
