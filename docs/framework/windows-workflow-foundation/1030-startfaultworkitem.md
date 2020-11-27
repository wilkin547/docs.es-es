---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281864"
---
# <a name="1030---startfaultworkitem"></a>1030 - StartFaultWorkItem

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1030|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que un FaultWorkItem está iniciando la ejecución.  
  
## <a name="message"></a>Message  

 Iniciando la ejecución de un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Nombre de tipo de la actividad que generó el error.|  
|FaultActivityDisplayName|xs:string|Nombre para mostrar de la actividad que generó el error.|  
|FaultActivityInstanceId|xs:string|Identificador de la actividad que generó el error.|  
|ExceptionActivity|xs:string|El nombre de tipo para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityDisplayName|xs:string|El nombre para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityInstanceId|xs:string|Identificador de instancia de la actividad que generó la excepción.|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
