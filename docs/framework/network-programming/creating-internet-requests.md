---
title: "Crear solicitudes de Internet | Microsoft Docs"
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
  - "WebRequest (clase), enviar y recibir datos"
  - "Redes"
  - "HttpWebResponse (clase), enviar y recibir datos"
  - "solicitar datos de Internet, crear solicitudes"
  - "Recursos de red"
  - "Internet, solicitar datos"
  - "solicitudes de datos, crear solicitudes"
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Crear solicitudes de Internet
Las aplicaciones crean instancias de <xref:System.Net.WebRequest> con el método de <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> .  Éste es un método estático que crea una clase derivada de **WebRequest** según el esquema de URI pasado a él.  
  
## Web, archivos y solicitudes de FTP  
 .NET Framework proporciona la clase de <xref:System.Net.HttpWebRequest> , que se deriva de **WebRequest**, las solicitudes http del identificador y HTTPS.  En la mayoría de los casos, la clase de **WebRequest** proporciona todas las propiedades que debe realizar una solicitud; al menos en caso necesario, puede convertir los objetos de **WebRequest** creados por el método de **WebRequest.Create** al tipo de **HttpWebRequest** para tener acceso a las propiedades Http\- específicas de la solicitud.  De igual forma, los controladores de objeto de **HttpWebResponse** las respuestas de solicitudes HTTP y HTTPS.  Para tener acceso a las propiedades Http\- específicas de **HttpWebResponse** opóngase, necesita convertir los objetos de **WebResponse** al tipo de **HttpWebResponse** .  
  
 .NET Framework también proporciona clases de <xref:System.Net.FileWebRequest> y de <xref:System.Net.FileWebResponse> a las solicitudes de los recursos que utilizan “file: ” Esquema de URI.  Igualmente, <xref:System.Net.FtpWebRequest> y las clases de <xref:System.Net.FtpWebResponse> se proporcionan las solicitudes de los recursos que utilizan “FTP: ” esquema.  Si la solicitud es para un recurso que usa cualquiera de estos esquemas, puede utilizar el método de **WebRequest.Create** para obtener un objeto con el que realizar la solicitud.  
  
 Para controlar las solicitudes que utilizan otros protocolos en la aplicación, debe implementar las clases protocolo\- específicas derivadas de **WebRequest** y de **WebResponse**.  Para obtener más información, vea [Protocolos conectables de programación](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## Vea también  
 [Cómo solicitar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)