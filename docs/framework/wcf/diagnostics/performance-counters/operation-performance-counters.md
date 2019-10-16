---
title: Contadores del rendimiento de las operaciones
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 59c75dacb2a01f1b85d67d5cc1651dbc55b6aa8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320174"
---
# <a name="operation-performance-counters"></a>Contadores del rendimiento de las operaciones
Los contadores de rendimiento de las operaciones se encuentran bajo el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento (Perfmon.exe). Cada operación posee una instancia individual. Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato. Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.  
  
> [!CAUTION]
> Hay un límite en la longitud del nombre de una instancia del contador de rendimiento. Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.  
  
## <a name="see-also"></a>Vea también

- [Contadores de rendimiento](index.md)
