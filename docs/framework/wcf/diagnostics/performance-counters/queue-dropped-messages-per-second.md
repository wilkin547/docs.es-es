---
title: Mensajes en cola quitados por segundo
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418253"
---
# <a name="queue-dropped-messages-per-second"></a>Mensajes en cola quitados por segundo
Nombre de contador: Mensajes en cola quitados por segundo.  
  
## <a name="description"></a>Descripción  
 Número de mensajes quitados cada segundo por el transporte en cola en este servicio.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
