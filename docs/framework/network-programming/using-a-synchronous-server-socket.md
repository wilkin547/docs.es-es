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
ms.openlocfilehash: 43e1d54d4e74b49fdf1a8997d1cc89492c9412bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117257"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="af305-102">Usar un socket de servidor sincrónico</span><span class="sxs-lookup"><span data-stu-id="af305-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="af305-103">Los sockets de servidor sincrónico suspenden la ejecución de la aplicación hasta que se recibe una solicitud de conexión en el socket.</span><span class="sxs-lookup"><span data-stu-id="af305-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="af305-104">Los sockets de servidor sincrónico no son adecuados para las aplicaciones que hacen un uso intensivo de la red durante su funcionamiento, pero pueden ser adecuados para las aplicaciones de red simple.</span><span class="sxs-lookup"><span data-stu-id="af305-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="af305-105">Una vez establecido un <xref:System.Net.Sockets.Socket> para que escuche en un punto de conexión mediante los métodos <xref:System.Net.Sockets.Socket.Bind%2A> y <xref:System.Net.Sockets.Socket.Listen%2A>, estará listo para aceptar solicitudes de conexión entrantes mediante el método <xref:System.Net.Sockets.Socket.Accept%2A>.</span><span class="sxs-lookup"><span data-stu-id="af305-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="af305-106">La aplicación se suspende hasta que se recibe una solicitud de conexión cuando se llama al método **Accept**.</span><span class="sxs-lookup"><span data-stu-id="af305-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="af305-107">Al recibir una solicitud de conexión, **Accept** devuelve una nueva instancia **Socket** que está asociada con el cliente que se conecta.</span><span class="sxs-lookup"><span data-stu-id="af305-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="af305-108">En el ejemplo siguiente se leen los datos desde el cliente, se muestran en la consola y se devuelven al cliente.</span><span class="sxs-lookup"><span data-stu-id="af305-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="af305-109">La clase **Socket** no especifica ningún protocolo de mensajería, por lo que la cadena "\<EOF>" marca el final de los datos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="af305-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="af305-110">Se presupone que se ha inicializado y enlazado a un punto de conexión una clase **Socket** denominada `listener`.</span><span class="sxs-lookup"><span data-stu-id="af305-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af305-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="af305-111">See also</span></span>

- [<span data-ttu-id="af305-112">Usar un socket de servidor asincrónico</span><span class="sxs-lookup"><span data-stu-id="af305-112">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="af305-113">Ejemplo de sockets de servidor sincrónicos</span><span class="sxs-lookup"><span data-stu-id="af305-113">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)
- [<span data-ttu-id="af305-114">escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="af305-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
