---
description: 'Más información acerca de: contadores de rendimiento del punto de conexión'
title: Contadores de rendimiento del extremo
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 60cd94d5d954c87f4b37469688ee809a13fa3cb4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771241"
---
# <a name="endpoint-performance-counters"></a>Contadores de rendimiento del extremo

Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes. Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento. Las instancias se denominan utilizando este patrón:  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del punto de conexión.  
  
> [!CAUTION]
> Hay un límite en la longitud del nombre de una instancia del contador de rendimiento. Cuando un nombre de instancia de contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia por un valor hash.  
  
## <a name="see-also"></a>Vea también

- [Contadores de rendimiento](index.md)
