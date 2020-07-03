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
ms.openlocfilehash: ef682af33c10cf06ffc398c22e4a7dc1adf8290e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502072"
---
# <a name="using-a-synchronous-client-socket"></a><span data-ttu-id="76498-103">Usar un Socket de cliente sincrónico</span><span class="sxs-lookup"><span data-stu-id="76498-103">Using a Synchronous Client Socket</span></span>
<span data-ttu-id="76498-104">Un socket de cliente sincrónico suspende el programa de la aplicación mientras se completa la operación de red.</span><span class="sxs-lookup"><span data-stu-id="76498-104">A synchronous client socket suspends the application program while the network operation completes.</span></span> <span data-ttu-id="76498-105">Los sockets sincrónicos no son adecuados para las aplicaciones que hacen un uso intensivo de la red durante su funcionamiento, pero pueden proporcionar un acceso simple a los servicios de red para otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="76498-105">Synchronous sockets are not suitable for applications that make heavy use of the network for their operation, but they can enable simple access to network services for other applications.</span></span>  
  
 <span data-ttu-id="76498-106">Para enviar datos, pase una matriz de bytes a uno de los métodos de datos de envío de la clase <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.SendTo%2A>).</span><span class="sxs-lookup"><span data-stu-id="76498-106">To send data, pass a byte array to one of the <xref:System.Net.Sockets.Socket> class's send-data methods (<xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.SendTo%2A>).</span></span> <span data-ttu-id="76498-107">En el ejemplo siguiente se codifica una cadena en un búfer de matriz de bytes mediante la propiedad <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> y luego se transmite el búfer al dispositivo de red mediante el método **Send**.</span><span class="sxs-lookup"><span data-stu-id="76498-107">The following example encodes a string into a byte array buffer using the <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> property and then transmits the buffer to the network device using the **Send** method.</span></span> <span data-ttu-id="76498-108">El método **Send** devuelve el número de bytes enviados al dispositivo de red.</span><span class="sxs-lookup"><span data-stu-id="76498-108">The **Send** method returns the number of bytes sent to the network device.</span></span>  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 <span data-ttu-id="76498-109">El método **Send** quita los bytes del búfer y los pone en cola con la interfaz de red que se enviará al dispositivo de red.</span><span class="sxs-lookup"><span data-stu-id="76498-109">The **Send** method removes the bytes from the buffer and queues them with the network interface to be sent to the network device.</span></span> <span data-ttu-id="76498-110">Es posible que la interfaz de red no envíe los datos inmediatamente, pero los enviará, siempre y cuando la conexión se cierre correctamente con el método <xref:System.Net.Sockets.Socket.Shutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="76498-110">The network interface might not send the data immediately, but it will send it eventually, as long as the connection is closed normally with the <xref:System.Net.Sockets.Socket.Shutdown%2A> method.</span></span>  
  
 <span data-ttu-id="76498-111">Para recibir datos de un dispositivo de red, pase un búfer a uno de los métodos de datos de recepción de la clase **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> y <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span><span class="sxs-lookup"><span data-stu-id="76498-111">To receive data from a network device, pass a buffer to one of the **Socket** class's receive-data methods (<xref:System.Net.Sockets.Socket.Receive%2A> and <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span></span> <span data-ttu-id="76498-112">Los sockets sincrónicos suspenderán la aplicación hasta que se reciban bytes de la red o hasta que se cierre el socket.</span><span class="sxs-lookup"><span data-stu-id="76498-112">Synchronous sockets will suspend the application until bytes are received from the network or until the socket is closed.</span></span> <span data-ttu-id="76498-113">En el siguiente ejemplo se reciben datos de la red y se muestran en la consola.</span><span class="sxs-lookup"><span data-stu-id="76498-113">The following example receives data from the network and then displays it on the console.</span></span> <span data-ttu-id="76498-114">En el ejemplo se presupone que los datos procedentes de la red son texto codificado en ASCII.</span><span class="sxs-lookup"><span data-stu-id="76498-114">The example assumes that the data coming from the network is ASCII-encoded text.</span></span> <span data-ttu-id="76498-115">El método **Receive** devuelve el número de bytes recibidos de la red.</span><span class="sxs-lookup"><span data-stu-id="76498-115">The **Receive** method returns the number of bytes received from the network.</span></span>  
  
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
  
 <span data-ttu-id="76498-116">Cuando el socket ya no sea necesario, deberá liberarlo llamando al método <xref:System.Net.Sockets.Socket.Shutdown%2A> y, luego, llamando al método **Close**.</span><span class="sxs-lookup"><span data-stu-id="76498-116">When the socket is no longer needed, you need to release it by calling the <xref:System.Net.Sockets.Socket.Shutdown%2A> method and then calling the **Close** method.</span></span> <span data-ttu-id="76498-117">En el ejemplo siguiente se libera un **Socket**.</span><span class="sxs-lookup"><span data-stu-id="76498-117">The following example releases a **Socket**.</span></span> <span data-ttu-id="76498-118">La enumeración <xref:System.Net.Sockets.SocketShutdown> define constantes que indican si se debe cerrar el socket para efectuar un envío, una recepción o ambos.</span><span class="sxs-lookup"><span data-stu-id="76498-118">The <xref:System.Net.Sockets.SocketShutdown> enumeration defines constants that indicate whether the socket should be closed for sending, for receiving, or for both.</span></span>  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="76498-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="76498-119">See also</span></span>

- [<span data-ttu-id="76498-120">Uso de un socket de cliente asincrónico</span><span class="sxs-lookup"><span data-stu-id="76498-120">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="76498-121">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="76498-121">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="76498-122">Ejemplo de sockets de cliente sincrónicos</span><span class="sxs-lookup"><span data-stu-id="76498-122">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)
