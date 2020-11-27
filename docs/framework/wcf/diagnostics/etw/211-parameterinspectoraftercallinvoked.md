---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279069"
---
# <a name="211---parameterinspectoraftercallinvoked"></a>211 - ParameterInspectorAfterCallInvoked

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|211|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en `ParameterInspector`.  
  
## <a name="message"></a>Message  

 El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Nombre del tipo|`xs:string`|Nombre completo (FullName) de CLR del tipo del `ParameterInspector` invocado.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
