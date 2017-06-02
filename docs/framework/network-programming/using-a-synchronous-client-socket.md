---
title: "Usar un Socket de cliente sincr&#243;nico | Microsoft Docs"
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
  - "solicitar datos de Internet, sockets"
  - "sockets de cliente sincrónicos"
  - "Socket (clase), sockets de cliente sincrónicos"
  - "recibir datos, sockets"
  - "sockets, sockets de cliente sincrónicos"
  - "protocolos, sockets"
  - "Internet, sockets"
  - "sockets de cliente"
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Usar un Socket de cliente sincr&#243;nico
Un socket sincrónico de cliente suspende el programa de aplicación mientras la operación de red completa.  Sockets sincrónicos no son adecuados para las aplicaciones que utilizan intensivo de red para la operación, pero pueden permitir el acceso sencillo a los servicios de red para otras aplicaciones.  
  
 Para enviar datos, pase una matriz de bytes a uno de los métodos de los enviar\- datos de clase de <xref:System.Net.Sockets.Socket> \(<xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.SendTo%2A>\).  El ejemplo siguiente codifica una cadena en un búfer de la matriz de bytes mediante la propiedad de <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName> y después transmite el búfer al dispositivo de red con el método de **Enviar** .  El método de **Enviar** devuelve el número de bytes enviados al dispositivo de red.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 El método de **Enviar** quita los bytes del búfer y los coloca en la cola con la interfaz de red que se va a enviar al dispositivo de red.  La interfaz de red no puede enviar los datos inmediatamente, pero la enviará finalmente, mientras se cierra la conexión normalmente con el método de <xref:System.Net.Sockets.Socket.Shutdown%2A> .  
  
 Para recibir datos de un dispositivo de red, pase un búfer a uno de los métodos de los recibir\- datos de clase de **Socket** \(<xref:System.Net.Sockets.Socket.Receive%2A> y <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>\).  Sockets sincrónicos suspenderán la aplicación hasta que los bytes se reciben de red o hasta que se cierra el socket.  El ejemplo siguiente recibe los datos de la red y de la muestra en la consola.  En el ejemplo se supone que los datos que provienen de red es texto ASCII\- codificada.  El método de **Receive** devuelve el número de bytes recibidos de la red.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Cuando el socket ya no se necesita, debe liberarlo llamando al método de <xref:System.Net.Sockets.Socket.Shutdown%2A> y después llamando al método de **Cerrar** .  El ejemplo siguiente se libera **Socket**.  La enumeración de <xref:System.Net.Sockets.SocketShutdown> define las constantes que indican si el socket se debe cerrar para enviar, recibir, o para ambos.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## Vea también  
 [Usar un socket de cliente asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Ejemplo de sockets de cliente sincrónicos](../../../docs/framework/network-programming/synchronous-client-socket-example.md)