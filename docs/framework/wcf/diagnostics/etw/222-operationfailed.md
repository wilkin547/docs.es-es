---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781646"
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|222|  
|Palabras clave|EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se emite cuando `OperationInvoker` predeterminado del modelo de servicio detecta una excepción al invocar el método. Tenga en cuenta que las excepciones que derivan de `FaultException` hacen que este evento no se emita.  
  
## <a name="message"></a>Mensaje  
 El método '%1' produjo una excepción no controlada al invocarse por OperationInvoker. La duración de la llamada al método fue de '%2' ms.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Nombre del método|`xs:string`|El nombre de CLR del método invocado por `OperationInvoker`.|  
|Duración|`xs:long`|El tiempo, en milisegundos, que tardó `OperationInvoker` en invocar el método.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ". Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
