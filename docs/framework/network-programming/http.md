---
title: "HTTP | Microsoft Docs"
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
  - "protocolos, HTTP"
  - "enviar datos, HTTP"
  - "HttpWebResponse (clase), enviar y recibir datos"
  - "HTTP"
  - "recibir datos, HTTP"
  - "protocolos de aplicaciones, HTTP"
  - "Internet, HTTP"
  - "recursos de red, HTTP"
  - "HTTP, información sobre HTTP"
  - "HttpWebRequest (clase), enviar y recibir datos"
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# HTTP
.NET Framework proporciona compatibilidad completa para el protocolo HTTP, compuesta a la mayoría de todo el tráfico de Internet, con las clases de<xref:System.Net.HttpWebRequest> y de <xref:System.Net.HttpWebResponse> .  Estas clases, derivadas de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse>, se devuelven de forma predeterminada siempre que el método estático <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> busque un URI a partir de “http” o “https”.  En la mayoría de los casos, las clases de **WebRequest** y de **WebResponse** proporcionan todo que sea necesario realizar la solicitud, pero si necesita obtener acceso a las características Http\- específicas expuestas como propiedades, puede convertir estas clases a **HttpWebRequest** o a **HttpWebResponse**.  
  
 **HttpWebRequest** y **HttpWebResponse** encapsulan una transacción estándar de la solicitud\-y\- respuesta HTTP y proporcionan acceso a los encabezados HTTP comunes.  Estas clases también admiten la mayoría de HTTP 1,1 características, incluida la canalización, enviar y recibir datos en fragmentos, la autenticación, el preauthentication, el cifrado, la compatibilidad de proxy, la validación del certificado de servidor, y administración de la conexión.  Los encabezados personalizados y encabezados no proporcionados mediante propiedades pueden almacenarse en y obtener acceso mediante la propiedad de **Headers** .  
  
 **HttpWebRequest** es la clase predeterminada utilizada por **WebRequest** y no es necesario registrar antes de poder pasar un URI al método de **WebRequest.Create** .  
  
 Puede hacer que la aplicación sigue redirecciones HTTP automáticamente estableciendo la propiedad de <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> a **true** \(valor predeterminado\).  La aplicación se redirigirá solicitudes, y la propiedad de [ResponseURI](frlrfsystemnethttpwebresponseclassresponseuritopic) de **HttpWebResponse** contendrá el recurso web real que respondió a la solicitud.  Si se **AllowAutoRedirect** establecido en **false**, la aplicación debe poder administrar redirecciones como errores de protocolo HTTP.  
  
 Las aplicaciones reciben errores de protocolo HTTP detectando <xref:System.Net.WebException> con <xref:System.Net.WebException.Status%2A> establecido en [WebExceptionStatus.ProtocolError](frlrfsystemnetwebexceptionstatusclasstopic).  La propiedad de <xref:System.Net.WebException.Response%2A> contiene **WebResponse** enviado por el servidor e indica el error real HTTP encontrado.  
  
## Vea también  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Cómo: obtener acceso a propiedades específicas de HTTP](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)