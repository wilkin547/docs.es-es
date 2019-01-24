---
title: Contadores de rendimiento del punto de conexión
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: de750b3e5ee61b6bfc5b387fb7de84b74171d8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501966"
---
# <a name="endpoint-performance-counters"></a>Contadores de rendimiento del punto de conexión
Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes. Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento. Las instancias se denominan utilizando este patrón:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del extremo.  
  
> [!CAUTION]
>  Hay un límite en la longitud del nombre de una instancia del contador de rendimiento. Cuando un nombre de instancia del contador de Windows Communication Foundation (WCF) supera la longitud máxima, WCF reemplaza una parte del nombre de instancia con un valor hash.  
  
## <a name="see-also"></a>Vea también
- [Contadores de rendimiento](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
