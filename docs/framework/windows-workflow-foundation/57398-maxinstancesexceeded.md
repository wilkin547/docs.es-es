---
description: 'Más información acerca de: 57398-MaxInstancesExceeded'
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: 104c466cb2e0ee8156e2b268caf5e757353dfb09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720233"
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
  
## <a name="message"></a>Message  

 El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'. El límite para este acelerador se estableció en %1. El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Nombre|xs:string|Nombre del elemento.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
