---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|57398|  
|Palabras clave|WFServices|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Indica que el sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.  
  
## <a name="message"></a>Mensaje  
 El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'. El límite para este acelerador se estableció en %1. El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Name|xs:string|Nombre del elemento.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
