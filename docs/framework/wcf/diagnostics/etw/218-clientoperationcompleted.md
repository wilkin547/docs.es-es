---
title: "218 - ClientOperationCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 218 - ClientOperationCompleted
## Propiedades  
  
|||  
|-|-|  
|Id.|218|  
|Palabras clave|Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Los clientes emiten este evento justo después de finalizar una operación.Para las operaciones unidireccionales, esto es en cuanto se haya enviado correctamente el mensaje.Para las operaciones de solicitud\-respuesta, esto es una vez recibida la respuesta.  
  
## Mensaje  
 El cliente ha terminado de ejecutar la acción '%1' asociada al contrato '%2'.El mensaje se envió a '%3'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Action|xs:string|El encabezado de acción de SOAP del mensaje saliente.|  
|Contract Name|`xs:string`|El nombre del contrato.Ejemplo: ICalculadora.|  
|Destination|`xs:string`|La dirección del extremo de servicio a la que se ha enviado el mensaje.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|