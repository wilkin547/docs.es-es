---
title: 'punto de conexión: Flujo de transacciones por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264368"
---
# <a name="endpoint-transactions-flowed-per-second"></a>punto de conexión: Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo.  
  
## <a name="description"></a>Descripción  
 Número de transacciones de flujo a las operaciones en este punto de conexión en un segundo. Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al punto de conexión.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
