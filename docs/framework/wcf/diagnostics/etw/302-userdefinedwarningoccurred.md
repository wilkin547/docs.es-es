---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243448"
---
# <a name="302---userdefinedwarningoccurred"></a>302 - UserDefinedWarningOccurred

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|302|  
|Palabras clave|Solución de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se emite desde el código de usuario. Los desarrolladores pueden emitir este evento cuando se produce un evento de advertencia definido por el usuario en su servicio. Esto se puede llevar a cabo mediante las API de <xref:System.Diagnostics.Eventing>. Además, hay un ejemplo de WCF que ajusta esa API y muestra cómo emitir este evento correctamente.  
  
## <a name="message"></a>Message  

 Nombre: '%1', referencia: '%2', carga:%3  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|NOMBRE|`xs:string`|El nombre del evento definido por el usuario.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|Carga|`xs:string`|La carga del evento definida por el usuario.|
