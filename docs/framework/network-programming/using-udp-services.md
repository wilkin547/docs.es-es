---
title: Usar servicios UDP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- protocols, UDP
- network resources, UDP
- requesting data from Internet, UDP
- UDP
- receiving data, UDP
- Internet, UDP
- broadcasting messages to multiple addresses
- data requests, UDP
- UdpClient class, about UdpClient class
- sending data, UDP
- application protocols, UDP
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
ms.openlocfilehash: 477095ada6e44f66cbc60cd80375da9a87f38e39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180604"
---
# <a name="using-udp-services"></a><span data-ttu-id="1993c-102">Usar servicios UDP</span><span class="sxs-lookup"><span data-stu-id="1993c-102">Using UDP Services</span></span>
<span data-ttu-id="1993c-103">La clase <xref:System.Net.Sockets.UdpClient> se comunica con los servicios de red mediante UDP.</span><span class="sxs-lookup"><span data-stu-id="1993c-103">The <xref:System.Net.Sockets.UdpClient> class communicates with network services using UDP.</span></span> <span data-ttu-id="1993c-104">Las propiedades y métodos de la clase <xref:System.Net.Sockets.UdpClient> abstraen los detalles de la creación de un <xref:System.Net.Sockets.Socket> para solicitar y recibir datos mediante UDP.</span><span class="sxs-lookup"><span data-stu-id="1993c-104">The properties and methods of the <xref:System.Net.Sockets.UdpClient> class abstract the details of creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using UDP.</span></span>

<span data-ttu-id="1993c-105">El Protocolo de datagramas de usuario (UDP) es un protocolo simple que hace todo lo posible para entregar datos a un host remoto.</span><span class="sxs-lookup"><span data-stu-id="1993c-105">User Datagram Protocol (UDP) is a simple protocol that makes a best effort to deliver data to a remote host.</span></span> <span data-ttu-id="1993c-106">Pero como el protocolo UDP es un protocolo sin conexión, no se garantiza que lleguen los datagramas de UDP enviados al punto de conexión remoto, ni tampoco se garantiza que lleguen en la misma secuencia en la que se envían.</span><span class="sxs-lookup"><span data-stu-id="1993c-106">However, because the UDP protocol is a connectionless protocol, UDP datagrams sent to the remote endpoint are not guaranteed to arrive, nor are they guaranteed to arrive in the same sequence in which they are sent.</span></span> <span data-ttu-id="1993c-107">Las aplicaciones que usan UDP deben estar preparadas para controlar los datagramas que faltan, los datagramas duplicados y los datagramas que están fuera de secuencia.</span><span class="sxs-lookup"><span data-stu-id="1993c-107">Applications that use UDP must be prepared to handle missing, duplicate, and out-of-sequence datagrams.</span></span>

<span data-ttu-id="1993c-108">Para enviar un datagrama mediante UDP, debe conocer la dirección de red del dispositivo de red que hospeda el servicio que necesita, así como el número de puerto UDP que usa el servicio para comunicarse.</span><span class="sxs-lookup"><span data-stu-id="1993c-108">To send a datagram using UDP, you must know the network address of the network device hosting the service you need and the UDP port number that the service uses to communicate.</span></span> <span data-ttu-id="1993c-109">Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para más información, vea [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro del nombre de servicio y del número de puerto del protocolo de transporte).</span><span class="sxs-lookup"><span data-stu-id="1993c-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="1993c-110">Los servicios que no están en la lista de Iana pueden tener números de puerto en el intervalo comprendido entre 1024 y 65 535.</span><span class="sxs-lookup"><span data-stu-id="1993c-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="1993c-111">Se usan direcciones de red especiales para admitir mensajes de difusión de UDP en redes basadas en IP.</span><span class="sxs-lookup"><span data-stu-id="1993c-111">Special network addresses are used to support UDP broadcast messages on IP-based networks.</span></span> <span data-ttu-id="1993c-112">En la siguiente explicación se usa como ejemplo la versión 4 de la familia de direcciones IP, usada en Internet.</span><span class="sxs-lookup"><span data-stu-id="1993c-112">The following discussion uses the IP version 4 address family used on the Internet as an example.</span></span>

<span data-ttu-id="1993c-113">Las direcciones IP de la versión 4 usan 32 bits para especificar una dirección de red.</span><span class="sxs-lookup"><span data-stu-id="1993c-113">IP version 4 addresses use 32 bits to specify a network address.</span></span> <span data-ttu-id="1993c-114">Para las direcciones de clase C que usan una máscara de red de 255.255.255.0, estos bits se dividen en cuatro octetos.</span><span class="sxs-lookup"><span data-stu-id="1993c-114">For class C addresses using a netmask of 255.255.255.0, these bits are separated into four octets.</span></span> <span data-ttu-id="1993c-115">Cuando se expresa en formato decimal, los cuatro octetos forman la conocida notación de cuatro dígitos separados por puntos, como 192.168.100.2.</span><span class="sxs-lookup"><span data-stu-id="1993c-115">When expressed in decimal, the four octets form the familiar dotted-quad notation, such as 192.168.100.2.</span></span> <span data-ttu-id="1993c-116">Los dos primeros octetos (192.168 en este ejemplo) forman el número de red, el tercer octeto (100) define la subred y el último octeto (2) es el identificador de host.</span><span class="sxs-lookup"><span data-stu-id="1993c-116">The first two octets (192.168 in this example) form the network number, the third octet (100) defines the subnet, and the final octet (2) is the host identifier.</span></span>

<span data-ttu-id="1993c-117">Al establecer todos los bits de una dirección IP en uno, o 255.255.255.255, se crea la dirección de difusión limitada.</span><span class="sxs-lookup"><span data-stu-id="1993c-117">Setting all the bits of an IP address to one, or 255.255.255.255, forms the limited broadcast address.</span></span> <span data-ttu-id="1993c-118">El envío de un datagrama UDP a esta dirección entrega el mensaje a todos los hosts del segmento de red local.</span><span class="sxs-lookup"><span data-stu-id="1993c-118">Sending a UDP datagram to this address delivers the message to any host on the local network segment.</span></span> <span data-ttu-id="1993c-119">Dado que los enrutadores nunca reenvían los mensajes enviados a esta dirección, solo los hosts del segmento de red recibirán el mensaje de difusión.</span><span class="sxs-lookup"><span data-stu-id="1993c-119">Because routers never forward messages sent to this address, only hosts on the network segment receive the broadcast message.</span></span>

<span data-ttu-id="1993c-120">Las difusiones se pueden dirigir a partes específicas de una red estableciendo todos los bits del identificador de host.</span><span class="sxs-lookup"><span data-stu-id="1993c-120">Broadcasts can be directed to specific portions of a network by setting all bits of the host identifier.</span></span> <span data-ttu-id="1993c-121">Por ejemplo, para enviar una difusión a todos los hosts de la red identificada por las direcciones IP que empiezan por 192.168.1, use la dirección 192.168.1.255.</span><span class="sxs-lookup"><span data-stu-id="1993c-121">For example, to send a broadcast to all hosts on the network identified by IP addresses starting with 192.168.1, use the address 192.168.1.255.</span></span>

<span data-ttu-id="1993c-122">En el ejemplo de código siguiente se usa un elemento <xref:System.Net.Sockets.UdpClient> para realizar escuchas de los datagramas UDP en el puerto 11 000.</span><span class="sxs-lookup"><span data-stu-id="1993c-122">The following code example uses a <xref:System.Net.Sockets.UdpClient> to listen for UDP datagrams on port 11,000.</span></span> <span data-ttu-id="1993c-123">El cliente recibe una cadena de mensaje y escribe el mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="1993c-123">The client receives a message string and writes the message to the console.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class UDPListener
   Private Const listenPort As Integer = 11000

   Private Shared Sub StartListener()
      Dim listener As New UdpClient(listenPort)
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)
      Try
         While True
            Console.WriteLine("Waiting for broadcast")
            Dim bytes As Byte() = listener.Receive(groupEP)
            Console.WriteLine("Received broadcast from {0} :", groupEP)
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytes.Length))
         End While
      Catch e As SocketException
         Console.WriteLine(e)
      Finally
         listener.Close()
      End Try
   End Sub 'StartListener

   Public Shared Sub Main()
      StartListener()
   End Sub 'Main
End Class 'UDPListener
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class UDPListener
{
    private const int listenPort = 11000;

    private static void StartListener()
    {
        UdpClient listener = new UdpClient(listenPort);
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any, listenPort);

        try
        {
            while (true)
            {
                Console.WriteLine("Waiting for broadcast");
                byte[] bytes = listener.Receive(ref groupEP);

                Console.WriteLine($"Received broadcast from {groupEP} :");
                Console.WriteLine($" {Encoding.ASCII.GetString(bytes, 0, bytes.Length)}");
            }
        }
        catch (SocketException e)
        {
            Console.WriteLine(e);
        }
        finally
        {
            listener.Close();
        }
    }

    public static void Main()
    {
        StartListener();
    }
}
```

<span data-ttu-id="1993c-124">En el siguiente ejemplo de código se usa <xref:System.Net.Sockets.Socket> para enviar datagramas UDP a la dirección de difusión dirigida 192.168.1.255 mediante el puerto 11.000.</span><span class="sxs-lookup"><span data-stu-id="1993c-124">The following code example uses a <xref:System.Net.Sockets.Socket> to send UDP datagrams to the directed broadcast address 192.168.1.255, using port 11,000.</span></span> <span data-ttu-id="1993c-125">El cliente envía la cadena de mensaje especificada en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="1993c-125">The client sends the message string specified on the command line.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class Program
    Public Shared Sub Main(args() As [String])
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp)
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))
      Dim ep As New IPEndPoint(broadcast, 11000)
      s.SendTo(sendbuf, ep)
      Console.WriteLine("Message sent to the broadcast address")
   End Sub 'Main
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

class Program
{
    static void Main(string[] args)
    {
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp);

        IPAddress broadcast = IPAddress.Parse("192.168.1.255");

        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);

        s.SendTo(sendbuf, ep);

        Console.WriteLine("Message sent to the broadcast address");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="1993c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1993c-126">See also</span></span>

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
