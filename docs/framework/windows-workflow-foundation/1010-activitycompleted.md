---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509702"
---
# <a name="1010---activitycompleted"></a>1010 - ActivityCompleted
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1010|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que una actividad ha completado su ejecución.  
  
## <a name="message"></a>Mensaje  
 Actividad “%1", DisplayName: “%2 ", InstanceId: “%3 " se ha completado en el estado “%4".  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|Estado|xs:string|Estado de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
