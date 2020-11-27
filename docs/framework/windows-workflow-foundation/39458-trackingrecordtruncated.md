---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275897"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|39458|  
|Palabras clave|WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha truncado un registro de seguimiento. Se han quitado las variables, anotaciones y datos del usuario.  
  
## <a name="message"></a>Message  

 Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2. Se han quitado las variables, anotaciones y datos del usuario.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ProviderId|xs:string|Identificador del proveedor ETW.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
