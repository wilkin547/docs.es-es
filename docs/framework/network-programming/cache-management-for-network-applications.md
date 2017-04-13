---
title: "Administraci&#243;n de la memoria cach&#233; para aplicaciones de red | Microsoft Docs"
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
  - "caché [.NET Framework], aplicaciones de red"
  - "recursos de red, almacenamiento en caché"
  - "Internet, almacenamiento en caché"
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Administraci&#243;n de la memoria cach&#233; para aplicaciones de red
Este tema y los subtemas relacionados describen el almacenamiento en caché de los recursos recopilados mediante <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, y las clases de <xref:System.Net.FtpWebRequest> .  
  
 Una caché proporciona almacenamiento temporal de recursos que han sido solicitados por una aplicación.  Si una aplicación solicita el mismo recurso más de una vez, el recurso se puede devolver desde la caché, lo que evita la sobrecarga de re\- solicitar del servidor.  El almacenamiento en caché puede mejorar el rendimiento de la aplicación reduciendo el tiempo necesario para obtener un recurso solicitado.  El almacenamiento en caché también puede reducir el tráfico de red se reduce el número de viajes al servidor.  Mientras el almacenamiento en memoria caché mejora el rendimiento, aumenta el riesgo de que el recurso devuelto a la aplicación está obsoleto, lo que significa que no es idéntico al recurso que se habría enviado por el servidor si almacenados en caché se ocultarse.  
  
 El almacenamiento en caché puede permitir que los usuarios no autorizados o procesos lean datos confidenciales.  Una respuesta autenticada se almacena en caché que se puede recuperar de caché sin una autorización adicional.  Si está habilitado el almacenamiento en caché, vaya a <xref:System.Net.WebRequest.CachePolicy%2A> a <xref:System.Net.Cache.RequestCacheLevel> o a <xref:System.Net.Cache.RequestCacheLevel> para deshabilitar el almacenamiento en caché para esta solicitud.  
  
 Debido a los problemas de seguridad, el almacenamiento en caché es **not** recomendado para los escenarios de nivel medio.  
  
## En esta sección  
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)  
 Explica qué es una directiva de caché y cómo definir uno.  
  
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Define cada tipo de directiva ubicación\- basada de caché esté disponible para los recursos de Protocolo de transferencia de hipertexto \(HTTP y https\).  
  
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Describe las consideraciones que se pueden utilizar para personalizar una directiva Tiempo\- basada de caché.  
  
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Describe cómo crear mediante programación las directivas y las solicitudes de caché que utilizan el almacenamiento en caché.  
  
## Referencia  
 <xref:System.Net.Cache>  
 Define los tipos y enumeraciones utilizados para definir directivas de los recursos recopilados mediante <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, y las clases de <xref:System.Net.FtpWebRequest> .