---
title: "HttpListener | Microsoft Docs"
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
  - "HTTP"
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# HttpListener
La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación.  El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.  
  
## HTTP.SYS  
 La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows.  HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web.  Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL.  Para obtener más información, vea la documentación de la herramienta [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Server](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## Vea también  
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 [HTTP Server](http://go.microsoft.com/fwlink/?LinkID=178285)   
 [Mejoras de seguridad en Internet Información](http://go.microsoft.com/fwlink/?LinkID=178286)   
 [Ejemplo de aplicación de host ASPX HttpListener](http://go.microsoft.com/fwlink/?LinkID=179560)   
 [Ejemplo de tecnología HttpListener](http://go.microsoft.com/fwlink/?LinkID=179558)   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)