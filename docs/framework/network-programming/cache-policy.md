---
title: "Directiva de cach&#233; | Microsoft Docs"
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
  - "directivas de caché de duración definida"
  - "directivas de caché basadas en la ubicación"
  - "caché [.NET Framework], directivas"
  - "solicitar directivas de caché"
  - "actualización de los recursos almacenados en caché"
  - "directivas de caché de contenido"
  - "contenido caducado"
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Directiva de cach&#233;
Una directiva de caché define reglas que se utilizan para determinar si una solicitud se puede satisfacer utilizando una copia del recurso solicitado almacenada en caché.  Las aplicaciones especifican los requisitos de memoria caché del cliente para la actualización, pero la directiva efectiva de caché está determinada por los requisitos de memoria caché del cliente, los requisitos de la expiración del contenido del servidor, y los requisitos de volver a validar de servidor.  La interacción de los requisitos de la directiva y el servidor de la memoria caché del cliente siempre da lugar a la directiva más conservadora de caché, para asegurarse de que el contenido más reciente se devuelto a la aplicación cliente.  
  
 Ubicación\- se basan o Tiempo\- se basan las directivas de caché.  Una directiva ubicación\- basada de caché define la actualización de las entradas almacenadas en caché basadas en donde el recurso solicitado se puede realizar.  Una directiva Tiempo\- basada de caché define la actualización de entradas almacenadas en caché utilizando el tiempo que recuperada el recurso, los encabezados devueltos al recurso, y la hora actual.  La mayoría de las aplicaciones pueden utilizar la directiva Tiempo\- basada predeterminado de caché, que implementa el especificado en el documento RFC 2616 de la directiva de almacenamiento en caché, disponibles en [http:\/\/www.ietf.org](http://www.ietf.org/).  
  
 Las clases que se describen en la siguiente tabla se utilizan para especificar las directivas de caché.  
  
|Nombre de la clase|Descripción|  
|------------------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Representa ubicación\- basándose y Tiempo\- basándose las directivas de caché para los recursos solicitados mediante los objetos de <xref:System.Net.HttpWebRequest> .|  
|<xref:System.Net.Cache.RequestCachePolicy>|Representa ubicación\- basándose las directivas de caché o la directiva Tiempo\- basada <xref:System.Net.Cache.RequestCacheLevel> de los recursos solicitados mediante los objetos de <xref:System.Net.WebRequest> .|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Especifica los valores utilizados para crear los objetos Tiempo\- en función de <xref:System.Net.Cache.HttpRequestCachePolicy> .|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Especifica los valores utilizados para crear los objetos ubicación\- basados y Tiempo\- en función de <xref:System.Net.Cache.HttpRequestCachePolicy> .|  
|<xref:System.Net.Cache.RequestCacheLevel>|Especifica los valores utilizados para crear ubicación\- basado u objetos Tiempo\- basados <xref:System.Net.Cache.RequestCacheLevel> de <xref:System.Net.Cache.RequestCachePolicy> .|  
  
 Puede definir una directiva de caché para todas las solicitudes realizadas por la aplicación o para las solicitudes individuales.  Cuando se especifica una directiva en la aplicación de caché y un solicitud\- nivel almacena en caché la directiva, se utiliza la directiva de solicitud\- nivel.  Puede especificar una directiva en la aplicación de caché o mediante los archivos de la aplicación o de configuración del equipo.  Para obtener más información, vea [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Para crear una directiva de caché, debe crear un objeto de directiva creando una instancia de la clase de <xref:System.Net.Cache.RequestCachePolicy> o de <xref:System.Net.Cache.HttpRequestCachePolicy> .  Para especificar la directiva en una solicitud, establezca la propiedad de <xref:System.Net.WebRequest.CachePolicy%2A> de solicitud al objeto de directiva.  Al establecer una directiva en la aplicación mediante programación, establezca la propiedad de <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> al objeto de directiva.  
  
 Para obtener ejemplos de código que muestran cómo crear y utilizar las directivas de caché, vea [El almacenamiento en caché de configuración en aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)