---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267174"
---
# <a name="4212---lockretrytimeout"></a>4212 - LockRetryTimeout

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4212|  
|Palabras clave|WFInstanceStore|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.  
  
## <a name="message"></a>Message  

 Tiempo de espera al intentar adquirir el bloqueo de la instancia.  La operación no se completó dentro del tiempo de espera asignado de %1. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|El retraso entre los reintentos.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
