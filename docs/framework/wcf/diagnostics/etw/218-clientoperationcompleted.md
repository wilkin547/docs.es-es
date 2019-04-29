---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781776"
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
  
## <a name="message"></a>Mensaje  
 El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'. El mensaje se envió a '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Acción|xs:string|El encabezado de acción de SOAP del mensaje saliente.|  
|Contract Name|`xs:string`|El nombre del contrato. Ejemplo: ICalculator.|  
|Destino|`xs:string`|La dirección del punto de conexión de servicio a la que se ha enviado el mensaje.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ". Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
