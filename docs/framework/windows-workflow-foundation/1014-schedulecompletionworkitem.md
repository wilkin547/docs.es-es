---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275562"
---
# <a name="1014---schedulecompletionworkitem"></a>1014 - ScheduleCompletionWorkItem

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1014|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha programado un CompletionWorkItem.  
  
## <a name="message"></a>Message  

 Se ha programado un CompletionWorkItem para la actividad primaria ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Nombre del tipo de la actividad principal.|  
|ParentDisplayName|xs:string|Identificación y nombre para mostrar de la actividad principal.|  
|ParentInstanceId|xs:string|Identificador de instancia de la actividad principal.|  
|CompletedActivity|xs:string|El nombre del tipo de la actividad que se completó.|  
|CompletedActivityDisplayName|xs:string|Nombre para mostrar de la actividad que se ha completado.|  
|CompletedActivityInstanceId|xs:string|Identificador de instancia de la actividad que se ha completado.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
