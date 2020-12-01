---
title: Usar sockets de cliente
description: En este ejemplo se muestra cómo crear una conexión TCP/IP a un servicio remoto mediante un Socket en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
ms.openlocfilehash: 6982d09c20cd0d7e9d27fc63880b39e0982c86ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265198"
---
# <a name="using-client-sockets"></a><span data-ttu-id="70d8a-103">Usar sockets de cliente</span><span class="sxs-lookup"><span data-stu-id="70d8a-103">Using Client Sockets</span></span>

<span data-ttu-id="70d8a-104">Antes de poder iniciar una conversación a través de un <xref:System.Net.Sockets.Socket>, debe crear una canalización de datos entre su aplicación y el dispositivo remoto.</span><span class="sxs-lookup"><span data-stu-id="70d8a-104">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="70d8a-105">Aunque existen otros protocolos y familias de direcciones de red, en este ejemplo se muestra cómo crear una conexión TCP/IP a un servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="70d8a-105">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="70d8a-106">TCP/IP usa una dirección de red y un número de puerto de servicio para identificar un servicio de forma única.</span><span class="sxs-lookup"><span data-stu-id="70d8a-106">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="70d8a-107">La dirección de red identifica un dispositivo específico en la red; el número de puerto identifica el servicio específico en ese dispositivo al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="70d8a-107">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="70d8a-108">La combinación de puerto de servicio y dirección de red se denomina "punto de conexión", que en .NET Framework se representa mediante la clase <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="70d8a-108">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="70d8a-109">Para cada familia de direcciones compatible se define un descendiente de **EndPoint**; para la familia de direcciones IP, la clase es <xref:System.Net.IPEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="70d8a-109">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="70d8a-110">La clase <xref:System.Net.Dns> proporciona servicios de nombre de dominio a las aplicaciones que usan los servicios de Internet de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="70d8a-110">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="70d8a-111">El método <xref:System.Net.Dns.Resolve%2A> consulta un servidor DNS para asignar un nombre de dominio descriptivo (por ejemplo, "host.contoso.com") a una dirección de Internet numérica (por ejemplo, 192.168.1.1).</span><span class="sxs-lookup"><span data-stu-id="70d8a-111">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="70d8a-112">**Resolve** devuelve un <xref:System.Net.IPHostEntry> que contiene una lista de direcciones y alias para el nombre solicitado.</span><span class="sxs-lookup"><span data-stu-id="70d8a-112">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="70d8a-113">En la mayoría de los casos, puede usar la primera dirección devuelta en la matriz <xref:System.Net.IPHostEntry.AddressList%2A>.</span><span class="sxs-lookup"><span data-stu-id="70d8a-113">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="70d8a-114">El código siguiente obtiene una <xref:System.Net.IPAddress> que contiene la dirección IP para el servidor host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="70d8a-114">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="70d8a-115">Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para obtener más información, vea [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro del nombre de servicio y del número de puerto del protocolo de transporte).</span><span class="sxs-lookup"><span data-stu-id="70d8a-115">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="70d8a-116">Hay otros servicios que pueden tener registrados números de puerto en el intervalo comprendido entre 1024 y 65 535.</span><span class="sxs-lookup"><span data-stu-id="70d8a-116">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="70d8a-117">El código siguiente combina la dirección IP para host.contoso.com con un número de puerto para crear un punto de conexión remoto para una conexión.</span><span class="sxs-lookup"><span data-stu-id="70d8a-117">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="70d8a-118">Una vez determinada la dirección del dispositivo remoto y elegido un puerto que se usará para la conexión, la aplicación puede intentar establecer una conexión con el dispositivo remoto.</span><span class="sxs-lookup"><span data-stu-id="70d8a-118">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="70d8a-119">En el ejemplo siguiente se usa un **IPEndPoint** existente para conectarse a un dispositivo remoto y se detectan todas las excepciones que se generan.</span><span class="sxs-lookup"><span data-stu-id="70d8a-119">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="70d8a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="70d8a-120">See also</span></span>

- [<span data-ttu-id="70d8a-121">Uso de un socket de cliente sincrónico</span><span class="sxs-lookup"><span data-stu-id="70d8a-121">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="70d8a-122">Uso de un socket de cliente asincrónico</span><span class="sxs-lookup"><span data-stu-id="70d8a-122">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="70d8a-123">Cómo: Crear un socket</span><span class="sxs-lookup"><span data-stu-id="70d8a-123">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="70d8a-124">Sockets</span><span class="sxs-lookup"><span data-stu-id="70d8a-124">Sockets</span></span>](sockets.md)
