---
title: Mensajes dudosos en cola por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d755b9c9e4c8e7ef9e57a0d93c05f87830d63c5c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164000"
---
# <a name="queued-poison-messages-per-second"></a>Mensajes dudosos en cola por segundo
Nombre de contador: Mensajes dudosos en cola por segundo.  
  
## <a name="description"></a>Descripción  
 Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
