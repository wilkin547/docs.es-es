---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dd38ab45bceeee577d9e33f699a03a81c09dfc99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|219|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite cuando un servicio WCF encuentra una excepción no controlada. Esto incluye las excepciones no controladas durante la activación, durante el procesamiento de mensajes y en código de usuario.  
  
## <a name="message"></a>Mensaje  
 Excepción no controlada del tipo '%2' durante el procesamiento de mensajes. ToString de excepción completa: %1.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|El resultado de llamar a `ToString`() en la excepción de CLR.|  
|ExceptionTypeName|`xs:string`|El nombre completo (FullName) de CLR del tipo de la excepción.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'. Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
