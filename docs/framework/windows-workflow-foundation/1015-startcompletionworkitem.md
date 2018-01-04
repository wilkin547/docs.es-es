---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a>1015 - StartCompletionWorkItem
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1015|  
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
