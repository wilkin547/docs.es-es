---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: 6147c70448efb122cb43a2b42a1e9b59980fab29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278952"
---
# <a name="214---operationcompleted"></a>214 - OperationCompleted

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|214|  
|Palabras clave|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio ha finalizado una llamada a un método sin que dicho método haya generado una excepción.  
  
## <a name="message"></a>Message  

 Un OperationInvoker completó la llamada al método '%1'. La duración de la llamada al método fue de '%2' ms.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Nombre del método|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Duration|`xs:long`|El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
