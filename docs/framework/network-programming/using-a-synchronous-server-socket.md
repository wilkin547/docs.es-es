---
title: Usar un socket de servidor sincrónico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: cbc02c755ceefa8f31439f121a98978b82f33fa2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047035"
---
# <a name="using-a-synchronous-server-socket"></a>Usar un socket de servidor sincrónico
Los sockets de servidor sincrónico suspenden la ejecución de la aplicación hasta que se recibe una solicitud de conexión en el socket. Los sockets de servidor sincrónico no son adecuados para las aplicaciones que hacen un uso intensivo de la red durante su funcionamiento, pero pueden ser adecuados para las aplicaciones de red simple.  
  
 Una vez establecido un <xref:System.Net.Sockets.Socket> para que escuche en un punto de conexión mediante los métodos <xref:System.Net.Sockets.Socket.Bind%2A> y <xref:System.Net.Sockets.Socket.Listen%2A>, estará listo para aceptar solicitudes de conexión entrantes mediante el método <xref:System.Net.Sockets.Socket.Accept%2A>. La aplicación se suspende hasta que se recibe una solicitud de conexión cuando se llama al método **Accept**.  
  
 Al recibir una solicitud de conexión, **Accept** devuelve una nueva instancia **Socket** que está asociada con el cliente que se conecta. En el ejemplo siguiente se leen los datos desde el cliente, se muestran en la consola y se devuelven al cliente. La clase **Socket** no especifica ningún protocolo de mensajería, por lo que la cadena "\<EOF>" marca el final de los datos del mensaje. Se presupone que se ha inicializado y enlazado a un punto de conexión una clase **Socket** denominada `listener`.  
  
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
  
## <a name="see-also"></a>Vea también

- [Uso de un socket de servidor asincrónico](using-an-asynchronous-server-socket.md)
- [Ejemplo de sockets de servidor sincrónicos](synchronous-server-socket-example.md)
- [Escuchas con sockets](listening-with-sockets.md)
