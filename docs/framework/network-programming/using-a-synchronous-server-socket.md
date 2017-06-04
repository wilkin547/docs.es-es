---
title: "Usar un socket de servidor sincr&#243;nico | Microsoft Docs"
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
  - "sockets de servidor sincrónicos"
  - "enviar datos, sockets"
  - "solicitudes de datos, sockets"
  - "solicitar datos de Internet, sockets"
  - "sockets de servidor"
  - "recibir datos, sockets"
  - "Socket (clase), sockets de servidor sincrónicos"
  - "protocolos, sockets"
  - "sockets, sockets de servidor sincrónicos"
  - "Internet, sockets"
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Usar un socket de servidor sincr&#243;nico
Sockets sincrónicos de servidor suspenden la ejecución de la aplicación hasta que una solicitud de conexión se recibe en el socket.  Sockets sincrónicos de servidor no son adecuados para las aplicaciones que utilizan intensivo de red en la operación, pero pueden ser adecuadas para aplicaciones sencillas de la red.  
  
 Después de que <xref:System.Net.Sockets.Socket> está configurado para escuchar en un extremo utilizando los métodos de <xref:System.Net.Sockets.Socket.Bind%2A> y de <xref:System.Net.Sockets.Socket.Listen%2A> , está listo para aceptar solicitudes de conexión entrante mediante el método de <xref:System.Net.Sockets.Socket.Accept%2A> .  Se suspende la aplicación hasta que se reciba una solicitud de conexión cuando se llama al método de **Aceptar** .  
  
 Cuando se recibe una solicitud de conexión, **Aceptar** devuelve una nueva instancia de **Socket** asociado al cliente de conexión.  El ejemplo siguiente lee datos del cliente, los muestra en la consola, y repite los datos al cliente.  **Socket** no especifica ningún protocolo de mensajería, por lo que las marcas de “\<EOF\>” de la cadena el final de los datos del mensaje.  Se supone que **Socket** denominado `listener`se ha inicializado y se ha enlazado a un extremo.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## Vea también  
 [Usar un socket de servidor asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Ejemplo de sockets de servidor sincrónicos](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)