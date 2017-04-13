---
title: "TCP/UDP | Microsoft Docs"
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
  - "protocolos, TCP/UDP"
  - "recursos de red, TCP/UDP"
  - "enviar datos, TCP/UDP"
  - "TCP/UDP"
  - "TcpClient (clase), acerca de la clase TcpClient"
  - "protocolos de aplicaciones, TCP/UDP"
  - "recibir datos, TCP/UDP"
  - "TcpListener (clase), acerca de la clase TcpListener"
  - "Socket (clase), acerca de la clase Socket"
  - "UDP"
  - "solicitudes de datos, TCP/UDP"
  - "solicitar datos de Internet, TCP/UDP"
  - "Internet, TCP/UDP"
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# TCP/UDP
Las aplicaciones pueden usar los servicios de \(UDP\) de Protocolo de control de transmisión \(TCP\) y de Protocolo de datagramas de usuario con <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, y las clases de <xref:System.Net.Sockets.UdpClient> .  Estas clases de protocolo se compilan sobre la clase de <xref:System.Net.Sockets.Socket?displayProperty=fullName> y tome precauciones detalles de transferir datos.  
  
 Las clases de protocolo utilizan los métodos sincrónicos de la clase de **Socket** para proporcionar acceso simple y directo a servicios de red sin la sobrecarga de información o de conocer de estado que mantiene los detalles de colocar los sockets protocolo\- concretos.  Para usar los métodos asincrónicos de **Socket** , puede utilizar los métodos asincrónicos proporcionados por la clase de <xref:System.Net.Sockets.NetworkStream> .  Acceso a las características de la clase de **Socket** no expuesta por las clases de protocolo, debe usar la clase de **Socket** .  
  
 **TcpClient** y **TcpListener** representan red mediante la clase de **NetworkStream** .  Utilice el método de <xref:System.Net.Sockets.TcpClient.GetStream%2A> para devolver la secuencia de red, y después llama a los métodos de <xref:System.Net.Sockets.NetworkStream.Read%2A> y de <xref:System.Net.Sockets.NetworkStream.Write%2A> de la secuencia.  **NetworkStream** no posee el socket subyacente a las clases de protocolo, por lo que el cerrarlo no afecta al socket.  
  
 La clase de **UdpClient** utiliza una matriz de bytes para contener el datagrama de UDP.  Utilice el método de <xref:System.Net.Sockets.UdpClient.Send%2A> para enviar datos a la red y al método de <xref:System.Net.Sockets.UdpClient.Receive%2A> para recibir un datagrama de entrada.  
  
## Vea también  
 [Usar Servicios TCP](../../../docs/framework/network-programming/using-tcp-services.md)   
 [Usar servicios UDP](../../../docs/framework/network-programming/using-udp-services.md)   
 [Usar flujos en la red](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Usar un socket de servidor asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Usar un socket de cliente asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)