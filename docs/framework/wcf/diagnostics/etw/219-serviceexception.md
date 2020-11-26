---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241946"
---
# <a name="219---serviceexception"></a>219 - ServiceException

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|219|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se emite cuando un servicio WCF encuentra una excepción no controlada. Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.  
  
## <a name="message"></a>Message  

 Excepción no controlada del tipo '%2' durante el procesamiento de mensajes. ToString de excepción completa: %1.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|El resultado de llamar a `ToString`() en la excepción de CLR.|  
|ExceptionTypeName|`xs:string`|El nombre completo (FullName) de CLR del tipo de la excepción.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
