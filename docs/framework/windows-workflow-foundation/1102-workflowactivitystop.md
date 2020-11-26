---
title: 1102 - WorkflowActivityStop
ms.date: 03/30/2017
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
ms.openlocfilehash: 7b5c7874946ae494f41e73f3e7c90f3944a3521d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238696"
---
# <a name="1102---workflowactivitystop"></a>1102 - WorkflowActivityStop

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1102|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que la actividad de flujo de trabajo se ha detenido.  
  
## <a name="message"></a>Message  

 Id. de WorkflowInstance: '%1' actividad E2E  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Identificación de instancia del flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
