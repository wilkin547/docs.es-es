---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774418"
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
  
## <a name="message"></a>Mensaje  
 Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2. Se han quitado las variables, anotaciones y datos del usuario.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Número del registro de seguimiento.|  
|ProviderId|xs:string|Identificador del proveedor ETW.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
