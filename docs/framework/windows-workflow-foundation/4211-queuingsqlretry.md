---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267187"
---
# <a name="4211---queuingsqlretry"></a>4211 - QueuingSqlRetry

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4211|  
|Palabras clave|WFInstanceStore|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica poner en cola el intento de SQL.  
  
## <a name="message"></a>Message  

 Poniendo en cola el reintento SQL con %1 milisegundos de retraso.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|El retraso entre los reintentos.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
