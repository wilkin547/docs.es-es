---
title: "directivas de cach&#233; basadas en la ubicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Directiva de caché si está disponible"
  - "volver a cargar directiva"
  - "directivas de caché basadas en la ubicación"
  - "Directiva de solo caché"
  - "caché local"
  - "caché intermedia"
  - "Directiva de ninguna directiva ningún almacén"
  - "caché [.NET Framework], directivas basadas en ubicación"
  - "Revalidar directiva"
  - "actualización de los recursos almacenados en caché"
  - "Directiva de caché o solo siguiente caché"
  - "Actualizar directiva"
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# directivas de cach&#233; basadas en la ubicaci&#243;n
Una directiva ubicación\- basada de caché define la actualización de las entradas almacenadas en caché válidos según de donde el recurso solicitado se puede realizar.  Un recurso almacenado en caché es válido si no lo hace uso no infringe requisitos Servidor\- especificados de volver a validar.  Una directiva ubicación\- basada en caché se crea mediante programación utilizando un constructor de clase de <xref:System.Net.Cache.RequestCachePolicy> o de <xref:System.Net.Cache.HttpRequestCachePolicy> .  Pasan al tipo de directiva ubicación\- basada en el constructor con un valor de enumeración de <xref:System.Net.Cache.RequestCacheLevel> o de <xref:System.Net.Cache.HttpRequestCacheLevel> .  Para obtener ejemplos de código que crean directivas ubicación\- basadas de caché, vea [Cómo: Establecer una Directiva Ubicación\- Basada en caché para una aplicación](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md).  Las secciones siguientes se explica cada tipo de directiva ubicación\- basada en caché para los recursos de Protocolo de transferencia de hipertexto \(HTTP y https\).  
  
## La memoria caché si Directiva disponibles  
 Si un recurso solicitado válido está en la memoria caché local, se utilizará el recurso almacenado en caché; si no, la solicitud para el recurso se envía al servidor.  Si el recurso solicitado está disponible en cualquier caché entre cliente y servidor, la solicitud se puede satisfacer mediante caché intermedia.  
  
## Directiva de caché solo  
 Si un recurso solicitado válido está en la memoria caché local, se utilizará el recurso almacenado en caché.  Cuando se especifica este nivel de directiva de caché, se produce una excepción de <xref:System.Net.WebException> si el elemento no está en la caché local.  
  
## Caché o Directiva siguiente de la caché únicamente  
 Si un recurso solicitado válido está en la memoria caché local o caché intermedia en la red de área local, utilice el recurso almacenado en caché.  En caso contrario, se producirá una excepción <xref:System.Net.WebException>.  En el HTTP que almacena en caché protocolo, esto se logra utilizando la directiva solamente\-si\- almacenada en memoria caché de control de la memoria caché.  
  
## Ninguna caché ningún política del almacén  
 Un recurso solicitado nunca se utiliza de cualquier caché y nunca se coloca en la caché.  Si un recurso solicitado está en la memoria caché local, se quita.  Este nivel de directiva indica a memorias caché intermedias que también quitar el recurso.  En el HTTP que almacena en caché protocolo, esto se logra mediante la directiva del control de caché de ninguno\- almacén.  
  
## Directiva de actualización  
 Un recurso solicitado se puede utilizar si se obtiene del servidor o se encuentra en caché distinto de la memoria caché local.  Para que una caché intermedia pueda atender la solicitud, la caché debe volver a validar su entrada almacenada en memoria caché con el servidor.  En el HTTP que almacena en caché protocolo, esto se logra utilizando la Máx. \- edad \= 0 directivas de control de caché y el encabezado de Pragma de ninguno\- caché.  
  
## Recargue la Directiva  
 Los recursos solicitados deben obtener del servidor.  La respuesta se puede guardar en caché local.  En el HTTP que almacena en caché protocolo, esto se logra mediante la directiva de control de la caché de ninguno\- caché y el encabezado de Pragma de ninguno\- caché.  
  
## Directiva de Validar  
 Compara la copia del recurso en la caché con la copia en el servidor.  Si la copia del servidor es más reciente, se utiliza para atender la solicitud y reemplaza la copia en la caché.  Si la copia en la caché es la misma que la del servidor, se utiliza la copia almacenada en memoria caché.  En el protocolo de almacenamiento en caché HTTP, esto se logra utilizando una solicitud condicional.  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)