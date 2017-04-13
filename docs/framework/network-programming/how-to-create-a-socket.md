---
title: "C&#243;mo crear un socket | Microsoft Docs"
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
  - "Redes"
  - "enviar datos, sockets"
  - "solicitudes de datos, sockets"
  - "solicitar datos de Internet, sockets"
  - "Socket (clase), crear sockets"
  - "Recursos de red"
  - "recibir datos, sockets"
  - "protocolos, sockets"
  - "Internet, sockets"
  - "sockets, crear"
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# C&#243;mo crear un socket
Antes de poder utilizar un socket para comunicarse con dispositivos remotos, el socket se debe inicializar con información de protocolo y dirección de red.  El constructor para la clase de <xref:System.Net.Sockets.Socket> tiene parámetros que especifican la familia de la dirección, el tipo de socket, y el tipo de protocolo que el socket utiliza para hacer las conexiones.  
  
## Ejemplo  
 El ejemplo siguiente crea un socket que se puede utilizar para comunicar en una red de TCP\/IP\-based, como internet.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
  
```  
  
 Para utilizar UDP en lugar de TCP, cambie el tipo de protocolo, como en el ejemplo siguiente:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
  
```  
  
 La enumeración de <xref:System.Net.Sockets.AddressFamily> especifica familias estándar de dirección utilizadas por la clase de **Socket** para resolver direcciones de red \(por ejemplo, el miembro de **AddressFamily.InterNetwork** especifica la familia de la dirección de la versión 4 de IP\).  
  
 La enumeración de <xref:System.Net.Sockets.SocketType> especifica el tipo de socket \(por ejemplo, el miembro de **SocketType.Stream** indica un socket estándar para enviar y recibir datos con el control de flujo\).  
  
 La enumeración de <xref:System.Net.Sockets.ProtocolType> especifica el protocolo de red para utilizar cuando se comunica en **Socket** \(por ejemplo, **ProtocolType.Tcp** indica que el socket utiliza TCP; **ProtocolType.Udp** indica que el socket utiliza UDP\).  
  
 Después de crear **Socket** , puede iniciar una conexión a un extremo remoto o recibir conexiones de dispositivos remotos.  
  
## Vea también  
 [Usar sockets de cliente](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)