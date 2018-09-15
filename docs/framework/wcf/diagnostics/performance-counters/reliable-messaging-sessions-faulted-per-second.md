---
title: Errores en sesiones de mensajería de confianza por segundo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625517"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Errores en sesiones de mensajería de confianza por segundo
Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.  
  
## <a name="description"></a>Descripción  
 Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
