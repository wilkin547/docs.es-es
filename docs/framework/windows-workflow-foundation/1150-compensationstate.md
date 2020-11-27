---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 2adb317521b8659c2419e4c04aabf4cf4499b36f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285114"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1150|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica un cambio de estado en un CompensableActivity.  
  
## <a name="message"></a>Message  

 CompensableActivity '%1' no tiene el estado '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|State|xs:string|Estado de compensación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
