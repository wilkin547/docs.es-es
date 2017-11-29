---
title: "Contadores de rendimiento del punto de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d34df7c70e0edeef831843d9afcb2db32422ebe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-performance-counters"></a>Contadores de rendimiento del punto de conexión
Los contadores de rendimiento del punto de conexión capturan datos que revelan cómo un punto de conexión está aceptando los mensajes. Se pueden encontrar en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al verlo con el Monitor de rendimiento. Las instancias se denominan utilizando este patrón:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Los datos son similares a los datos reunidos para las operaciones individuales, pero solo se agregan a lo largo del extremo.  
  
> [!CAUTION]
>  Hay un límite en la longitud del nombre de una instancia del contador de rendimiento. Cuando un nombre de instancia de contador [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la longitud máxima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] reemplaza una parte del nombre de instancia con un valor hash.  
  
## <a name="see-also"></a>Vea también  
 [Contadores de rendimiento](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
