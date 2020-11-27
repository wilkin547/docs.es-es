---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: d74aa77aff7b45b50f6891c999889011d9e03381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278861"
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|218|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Los clientes emiten este evento justo después de finalizar una operación. Para las operaciones unidireccionales, esto es en cuanto se haya enviado correctamente el mensaje. Para las operaciones de solicitud-respuesta, esto es una vez recibida la respuesta.  
  
## <a name="message"></a>Message  

 El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'. El mensaje se envió a '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Acción|xs:string|El encabezado de acción de SOAP del mensaje saliente.|  
|Contract Name|`xs:string`|El nombre del contrato. Ejemplo: ICalculadora.|  
|Destination|`xs:string`|La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '. Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
