---
description: 'Más información acerca de: 452-MessageLogWarning'
title: 452 - MessageLogWarning
ms.date: 03/30/2017
ms.assetid: 22a9f6ea-5b5f-4110-8a4e-9be9c983fbbb
ms.openlocfilehash: 475ebaa86051485326b8a215cf299e929a731df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744596"
---
# <a name="452---messagelogwarning"></a>452 - MessageLogWarning

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|452|  
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
