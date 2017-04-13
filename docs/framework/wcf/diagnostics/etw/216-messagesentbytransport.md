---
title: "216 - MessageSentByTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 216 - MessageSentByTransport
## Propiedades  
  
|||  
|-|-|  
|Id.|216|  
|Palabras clave|Solución de problemas, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Servidor de aplicaciones\-Aplicaciones\/Analítico|  
  
## Descripción  
 Este evento se produce cuando un transporte basado en TCP envía un mensaje.Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.Esto puede deberse al comportamiento de la infraestructura, siendo la seguridad un buen ejemplo.Por lo tanto, el número de eventos **MessageSentByTransport** que se emiten varía dependiendo del enlace del servicio y de su configuración.  
  
## Mensaje  
 El transporte ha enviado un mensaje a '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|DestinationAddress|`xs:string`|La dirección a la que se ha enviado el mensaje de solicitud.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|