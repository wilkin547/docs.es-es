---
title: escuchas con sockets
description: Obtenga información sobre cómo crear un servicio remoto en el que un socket de servidor abre un puerto en la red y espera a que un cliente se conecte a ese puerto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: 0b6de67772bae397373e307ec02ce69a71b0542e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502319"
---
# <a name="listening-with-sockets"></a><span data-ttu-id="ac516-103">escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="ac516-103">Listening with Sockets</span></span>
<span data-ttu-id="ac516-104">Los sockets de escucha o de servidor abren un puerto en la red y esperan a que un cliente se conecte a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="ac516-104">Listener or server sockets open a port on the network and then wait for a client to connect to that port.</span></span> <span data-ttu-id="ac516-105">Aunque existen otros protocolos y familias de direcciones de red, en este ejemplo se muestra cómo crear un servicio remoto para una red TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="ac516-105">Although other network address families and protocols exist, this example shows how to create remote service for a TCP/IP network.</span></span>  
  
 <span data-ttu-id="ac516-106">La dirección única de un servicio TCP/IP se define mediante la combinación de la dirección IP del host con el número de puerto del servicio para crear un punto de conexión para el servicio.</span><span class="sxs-lookup"><span data-stu-id="ac516-106">The unique address of a TCP/IP service is defined by combining the IP address of the host with the port number of the service to create an endpoint for the service.</span></span> <span data-ttu-id="ac516-107">La clase <xref:System.Net.Dns> proporciona métodos que devuelven información sobre las direcciones de red compatibles con el dispositivo de red local.</span><span class="sxs-lookup"><span data-stu-id="ac516-107">The <xref:System.Net.Dns> class provides methods that return information about the network addresses supported by the local network device.</span></span> <span data-ttu-id="ac516-108">Cuando el dispositivo de red local tiene más de una dirección de red, o si el sistema local admite más de un dispositivo de red, la clase **Dns** devuelve información sobre todas las direcciones de red y la aplicación debe elegir la dirección correcta para el servicio.</span><span class="sxs-lookup"><span data-stu-id="ac516-108">When the local network device has more than one network address, or if the local system supports more than one network device, the **Dns** class returns information about all network addresses, and the application must choose the proper address for the service.</span></span> <span data-ttu-id="ac516-109">Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para obtener más información, vea [Registro del nombre de servicio y del número de puerto del protocolo de transporte](https://www.iana.org/assignments/port-numbers)</span><span class="sxs-lookup"><span data-stu-id="ac516-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services; for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="ac516-110">Hay otros servicios que pueden tener registrados números de puerto en el intervalo comprendido entre 1024 y 65 535.</span><span class="sxs-lookup"><span data-stu-id="ac516-110">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="ac516-111">En el ejemplo siguiente se crea una clase <xref:System.Net.IPEndPoint> para un servidor mediante la combinación de la primera dirección IP devuelta por **Dns** para el equipo host con un número de puerto elegido entre el intervalo de números de puerto registrados.</span><span class="sxs-lookup"><span data-stu-id="ac516-111">The following example creates an <xref:System.Net.IPEndPoint> for a server by combining the first IP address returned by **Dns** for the host computer with a port number chosen from the registered port numbers range.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 <span data-ttu-id="ac516-112">Una vez que se ha determinado el punto de conexión local, es necesario asociar el <xref:System.Net.Sockets.Socket> con ese punto de conexión mediante el método <xref:System.Net.Sockets.Socket.Bind%2A> y establecerlo de modo que escuche en el punto de conexión mediante el método <xref:System.Net.Sockets.Socket.Listen%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac516-112">After the local endpoint is determined, the <xref:System.Net.Sockets.Socket> must be associated with that endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> method and set to listen on the endpoint using the <xref:System.Net.Sockets.Socket.Listen%2A> method.</span></span> <span data-ttu-id="ac516-113">El método **Bind** produce una excepción si la combinación específica de dirección y puerto ya está en uso.</span><span class="sxs-lookup"><span data-stu-id="ac516-113">**Bind** throws an exception if the specific address and port combination is already in use.</span></span> <span data-ttu-id="ac516-114">En el ejemplo siguiente se muestra cómo asociar un **socket** con una clase **IPEndPoint**.</span><span class="sxs-lookup"><span data-stu-id="ac516-114">The following example demonstrates associating a **Socket** with an **IPEndPoint**.</span></span>  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp)
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 <span data-ttu-id="ac516-115">El método **Listen** toma un único parámetro que especifica cuántas conexiones pendientes con el **socket** se permiten antes de que se devuelva un error de servidor ocupado al cliente que intenta conectarse.</span><span class="sxs-lookup"><span data-stu-id="ac516-115">The **Listen** method takes a single parameter that specifies how many pending connections to the **Socket** are allowed before a server busy error is returned to the connecting client.</span></span> <span data-ttu-id="ac516-116">En este caso, se colocan en la cola de conexión hasta 100 clientes antes de que se devuelva una respuesta de servidor ocupado al cliente 101.</span><span class="sxs-lookup"><span data-stu-id="ac516-116">In this case, up to 100 clients are placed in the connection queue before a server busy response is returned to client number 101.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac516-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac516-117">See also</span></span>

- [<span data-ttu-id="ac516-118">Uso de un socket de servidor sincrónico</span><span class="sxs-lookup"><span data-stu-id="ac516-118">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="ac516-119">Uso de un socket de servidor asincrónico</span><span class="sxs-lookup"><span data-stu-id="ac516-119">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="ac516-120">Uso de sockets de cliente</span><span class="sxs-lookup"><span data-stu-id="ac516-120">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="ac516-121">Cómo: Crear un socket</span><span class="sxs-lookup"><span data-stu-id="ac516-121">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="ac516-122">Sockets</span><span class="sxs-lookup"><span data-stu-id="ac516-122">Sockets</span></span>](sockets.md)
