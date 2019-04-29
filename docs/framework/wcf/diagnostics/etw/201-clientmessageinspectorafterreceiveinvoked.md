---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782044"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a>201 - ClientMessageInspectorAfterReceiveInvoked
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|201|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceiveReply` en un inspector de mensaje de cliente.  
  
## <a name="message"></a>Mensaje  
 El distribuidor invocó 'AfterReceiveReply' en un ClientMessageInspector de tipo '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|El nombre completo (FullName) de CLR del tipo del inspector invocado.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ". Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
