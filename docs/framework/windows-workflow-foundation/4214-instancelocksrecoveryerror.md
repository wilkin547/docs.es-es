---
title: 4214 - InstanceLocksRecoveryError
ms.date: 03/30/2017
ms.assetid: d28fb2d5-bf15-4648-8d20-8141ad16f04b
ms.openlocfilehash: 4449232e5aed67f73936c5b93181f7852b164ad7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264119"
---
# <a name="4214---instancelocksrecoveryerror"></a>4214 - InstanceLocksRecoveryError

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4214|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 No se pudieron recuperar los bloqueos de instancia por una excepción.  
  
## <a name="message"></a>Message  

 No se pudieron recuperar los bloqueos de instancia por la siguiente excepción  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
