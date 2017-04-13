---
title: "215 - MessageReceivedByTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 215 - MessageReceivedByTransport
## Propiedades  
  
|||  
|-|-|  
|Id.|215|  
|Palabras clave|Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Descripción  
 Este evento se produce cuando un transporte basado en TCP recibe un mensaje.  Observe que, en el nivel de transporte, pueden intercambiarse múltiples mensajes entre los clientes y servicios para una única operación.  Esto puede deberse al comportamiento de la infraestructura, y la seguridad es un buen ejemplo.  Por lo tanto, el número de eventos `MessageReceivedByTransport` que se emiten varía según el enlace del servicio y su configuración.  
  
> [!NOTE]
>  Este evento no se emite para transportes unidireccionales.  
  
## Mensaje  
 El transporte ha recibido un mensaje de '%1'.  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|Listen Address|`xs:string`|La dirección que recibió el mensaje.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  El formato se define como 'Ruta de acceso virtual de la aplicación del nombre del sitio web&#124;Ruta de acceso virtual del servicio&#124;NombreServicio'.  Ejemplo: 'Sitio web predeterminado\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|