---
title: Usar un Socket de cliente sincrónico
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
ms.openlocfilehash: fdecd18dc5975cd469e49de0eb0b55081e738cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047071"
---
# <a name="using-a-synchronous-client-socket"></a><span data-ttu-id="fa388-102">Usar un Socket de cliente sincrónico</span><span class="sxs-lookup"><span data-stu-id="fa388-102">Using a Synchronous Client Socket</span></span>
<span data-ttu-id="fa388-103">Un socket de cliente sincrónico suspende el programa de la aplicación mientras se completa la operación de red.</span><span class="sxs-lookup"><span data-stu-id="fa388-103">A synchronous client socket suspends the application program while the network operation completes.</span></span> <span data-ttu-id="fa388-104">Los sockets sincrónicos no son adecuados para las aplicaciones que hacen un uso intensivo de la red durante su funcionamiento, pero pueden proporcionar un acceso simple a los servicios de red para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fa388-104">Synchronous sockets are not suitable for applications that make heavy use of the network for their operation, but they can enable simple access to network services for other applications.</span></span>  
  
 <span data-ttu-id="fa388-105">Para enviar datos, pase una matriz de bytes a uno de los métodos de datos de envío de la clase <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.SendTo%2A>).</span><span class="sxs-lookup"><span data-stu-id="fa388-105">To send data, pass a byte array to one of the <xref:System.Net.Sockets.Socket> class's send-data methods (<xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.SendTo%2A>).</span></span> <span data-ttu-id="fa388-106">En el ejemplo siguiente se codifica una cadena en un búfer de matriz de bytes mediante la propiedad <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> y luego se transmite el búfer al dispositivo de red mediante el método **Send**.</span><span class="sxs-lookup"><span data-stu-id="fa388-106">The following example encodes a string into a byte array buffer using the <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> property and then transmits the buffer to the network device using the **Send** method.</span></span> <span data-ttu-id="fa388-107">El método **Send** devuelve el número de bytes enviados al dispositivo de red.</span><span class="sxs-lookup"><span data-stu-id="fa388-107">The **Send** method returns the number of bytes sent to the network device.</span></span>  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 <span data-ttu-id="fa388-108">El método **Send** quita los bytes del búfer y los pone en cola con la interfaz de red que se enviará al dispositivo de red.</span><span class="sxs-lookup"><span data-stu-id="fa388-108">The **Send** method removes the bytes from the buffer and queues them with the network interface to be sent to the network device.</span></span> <span data-ttu-id="fa388-109">Es posible que la interfaz de red no envíe los datos inmediatamente, pero los enviará, siempre y cuando la conexión se cierre correctamente con el método <xref:System.Net.Sockets.Socket.Shutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa388-109">The network interface might not send the data immediately, but it will send it eventually, as long as the connection is closed normally with the <xref:System.Net.Sockets.Socket.Shutdown%2A> method.</span></span>  
  
 <span data-ttu-id="fa388-110">Para recibir datos de un dispositivo de red, pase un búfer a uno de los métodos de datos de recepción de la clase **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> y <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span><span class="sxs-lookup"><span data-stu-id="fa388-110">To receive data from a network device, pass a buffer to one of the **Socket** class's receive-data methods (<xref:System.Net.Sockets.Socket.Receive%2A> and <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span></span> <span data-ttu-id="fa388-111">Los sockets sincrónicos suspenderán la aplicación hasta que se reciban bytes de la red o hasta que se cierre el socket.</span><span class="sxs-lookup"><span data-stu-id="fa388-111">Synchronous sockets will suspend the application until bytes are received from the network or until the socket is closed.</span></span> <span data-ttu-id="fa388-112">En el siguiente ejemplo se reciben datos de la red y se muestran en la consola.</span><span class="sxs-lookup"><span data-stu-id="fa388-112">The following example receives data from the network and then displays it on the console.</span></span> <span data-ttu-id="fa388-113">En el ejemplo se presupone que los datos procedentes de la red son texto codificado en ASCII.</span><span class="sxs-lookup"><span data-stu-id="fa388-113">The example assumes that the data coming from the network is ASCII-encoded text.</span></span> <span data-ttu-id="fa388-114">El método **Receive** devuelve el número de bytes recibidos de la red.</span><span class="sxs-lookup"><span data-stu-id="fa388-114">The **Receive** method returns the number of bytes received from the network.</span></span>  
  
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
  
 <span data-ttu-id="fa388-115">Cuando el socket ya no sea necesario, deberá liberarlo llamando al método <xref:System.Net.Sockets.Socket.Shutdown%2A> y, luego, llamando al método **Close**.</span><span class="sxs-lookup"><span data-stu-id="fa388-115">When the socket is no longer needed, you need to release it by calling the <xref:System.Net.Sockets.Socket.Shutdown%2A> method and then calling the **Close** method.</span></span> <span data-ttu-id="fa388-116">En el ejemplo siguiente se libera un **Socket**.</span><span class="sxs-lookup"><span data-stu-id="fa388-116">The following example releases a **Socket**.</span></span> <span data-ttu-id="fa388-117">La enumeración <xref:System.Net.Sockets.SocketShutdown> define constantes que indican si se debe cerrar el socket para efectuar un envío, una recepción o ambos.</span><span class="sxs-lookup"><span data-stu-id="fa388-117">The <xref:System.Net.Sockets.SocketShutdown> enumeration defines constants that indicate whether the socket should be closed for sending, for receiving, or for both.</span></span>  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa388-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa388-118">See also</span></span>

- [<span data-ttu-id="fa388-119">Uso de un socket de cliente asincrónico</span><span class="sxs-lookup"><span data-stu-id="fa388-119">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="fa388-120">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="fa388-120">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="fa388-121">Ejemplo de sockets de cliente sincrónicos</span><span class="sxs-lookup"><span data-stu-id="fa388-121">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)
