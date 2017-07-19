---
title: "Sockets | Microsoft Docs"
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
  - "protocolos de aplicaciones, sockets"
  - "enviar datos, sockets"
  - "solicitudes de datos, sockets"
  - "Windows Sockets"
  - "sockets, sobre sockets"
  - "Clase socket, sobre la clase Socket"
  - "sockets"
  - "solicitar datos de Internet, sockets"
  - "red, sockets"
  - "recibir datos, sockets"
  - "protocolos, sockets"
  - "Internet, sockets"
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Sockets
El espacio de nombres <xref:System.Net.Sockets> contiene una implementación administrada de la interfaz de Windows Sockets.  El resto de las clases de acceso de red en el espacio de nombres <xref:System.Net> se compilan sobre esta implementación de sockets.  
  
 La clase de .NET Framework <xref:System.Net.Sockets.Socket> es una versión de código administrado de los servicios de socket proporcionados por el Winsock32 API.  En la mayoría de los casos, de **Socket** de clase de los métodos datos de calcular las referencias simplemente en sus homólogos nativos de Win32 y controlan las comprobaciones de seguridad necesaria.  
  
 La clase de **Socket** admite a dos modos básicos, sincrónico y asincrónico.  En modo sincrónico, las llamadas a funciones que realizan las operaciones de red \(como <xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.Receive%2A>\) espera hasta que la operación finalice antes de devolver el control al programa de llamada.  En modo asincrónico, estas llamadas devuelve inmediatamente.  
  
## Vea también  
 [Cómo crear un socket](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)   
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)