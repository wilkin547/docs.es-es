---
title: 452 - MessageLogWarning
ms.date: 03/30/2017
ms.assetid: 22a9f6ea-5b5f-4110-8a4e-9be9c983fbbb
ms.openlocfilehash: 484909bcdac27c1b04be967df1182a67294f4920
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242661"
---
# <a name="452---messagelogwarning"></a>452 - MessageLogWarning

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|452|  
|Palabras clave|Solución de problemas, WCFMessageLogging|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se genera cuando se envía la advertencia del registro de mensajes.  
  
## <a name="message"></a>Message  

 %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
