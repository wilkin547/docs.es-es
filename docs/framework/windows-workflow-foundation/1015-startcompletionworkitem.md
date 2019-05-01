---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032271"
---
# <a name="1015---startcompletionworkitem"></a>1015 - StartCompletionWorkItem
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1015|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que un CompletionWorkItem está iniciando la ejecución.  
  
## <a name="message"></a>Mensaje  
 Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'. Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.  
  
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
