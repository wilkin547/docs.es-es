---
title: Usar un Socket de cliente sincrónico
description: En este ejemplo se muestra un socket de cliente sincrónico en .NET Framework, que suspende el programa de la aplicación mientras se completa la operación de red.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
ms.openlocfilehash: f198f283f2acfdcfbafed25baecb02a64e9d1e26
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236317"
---
# <a name="using-a-synchronous-client-socket"></a>Usar un Socket de cliente sincrónico

Un socket de cliente sincrónico suspende el programa de la aplicación mientras se completa la operación de red. Los sockets sincrónicos no son adecuados para las aplicaciones que hacen un uso intensivo de la red durante su funcionamiento, pero pueden proporcionar un acceso simple a los servicios de red para otras aplicaciones.  
  
 Para enviar datos, pase una matriz de bytes a uno de los métodos de datos de envío de la clase <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.SendTo%2A>). En el ejemplo siguiente se codifica una cadena en un búfer de matriz de bytes mediante la propiedad <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> y luego se transmite el búfer al dispositivo de red mediante el método **Send**. El método **Send** devuelve el número de bytes enviados al dispositivo de red.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 El método **Send** quita los bytes del búfer y los pone en cola con la interfaz de red que se enviará al dispositivo de red. Es posible que la interfaz de red no envíe los datos inmediatamente, pero los enviará, siempre y cuando la conexión se cierre correctamente con el método <xref:System.Net.Sockets.Socket.Shutdown%2A>.  
  
 Para recibir datos de un dispositivo de red, pase un búfer a uno de los métodos de datos de recepción de la clase **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> y <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>). Los sockets sincrónicos suspenderán la aplicación hasta que se reciban bytes de la red o hasta que se cierre el socket. En el siguiente ejemplo se reciben datos de la red y se muestran en la consola. En el ejemplo se presupone que los datos procedentes de la red son texto codificado en ASCII. El método **Receive** devuelve el número de bytes recibidos de la red.  
  
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
  
 Cuando el socket ya no sea necesario, deberá liberarlo llamando al método <xref:System.Net.Sockets.Socket.Shutdown%2A> y, luego, llamando al método **Close**. En el ejemplo siguiente se libera un **Socket**. La enumeración <xref:System.Net.Sockets.SocketShutdown> define constantes que indican si se debe cerrar el socket para efectuar un envío, una recepción o ambos.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>Vea también

- [Uso de un socket de cliente asincrónico](using-an-asynchronous-client-socket.md)
- [Escuchas con sockets](listening-with-sockets.md)
- [Ejemplo de sockets de cliente sincrónicos](synchronous-client-socket-example.md)
