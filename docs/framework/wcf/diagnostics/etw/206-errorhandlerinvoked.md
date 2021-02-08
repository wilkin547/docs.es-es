---
description: 'Más información acerca de: 206-ErrorHandlerInvoked'
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: addbcbdea25c7f8e7515b743e98e426476fa0b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783786"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|206|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Este evento se emite cuando `ErrorHandler` ha tenido la oportunidad de administrar una excepción producida en una operación de servicio.  
  
## <a name="message"></a>Message  

 El distribuidor invocó un ErrorHandler del tipo ' %1 ' con una excepción del tipo ' %3 '. ErrorHandled == '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Nombre completo (FullName) de CLR del tipo del `ErrorHandler` invocado.|  
|Controlado|`xs:unsignedByte`|`true` si el controlador de errores administra el error; de lo contrario, `false`.|  
|ExceptionTypeName|`xs:string`|El nombre completo (FullName) de CLR de la excepción que se administraba.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
