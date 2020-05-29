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
ms.openlocfilehash: 5ff40e8759b1732d4ad228b1414f96f9c37e5ac5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209778"
---
# <a name="use-udp-services"></a>Uso de servicios UDP

La clase <xref:System.Net.Sockets.UdpClient> se comunica con los servicios de red mediante UDP. Las propiedades y métodos de la clase <xref:System.Net.Sockets.UdpClient> abstraen los detalles de la creación de un <xref:System.Net.Sockets.Socket> para solicitar y recibir datos mediante UDP.

El Protocolo de datagramas de usuario (UDP) es un protocolo simple que hace todo lo posible para entregar datos a un host remoto. Pero como el protocolo UDP es un protocolo sin conexión, no se garantiza que lleguen los datagramas de UDP enviados al punto de conexión remoto, ni tampoco se garantiza que lleguen en la misma secuencia en la que se envían. Las aplicaciones que usan UDP deben estar preparadas para controlar los datagramas que faltan, los datagramas duplicados y los datagramas que están fuera de secuencia.

Para enviar un datagrama mediante UDP, debe conocer la dirección de red del dispositivo de red que hospeda el servicio que necesita, así como el número de puerto UDP que usa el servicio para comunicarse. Internet Assigned Numbers Authority (LANA) define números de puerto para servicios comunes; para más información, consulte [Registro del nombre de servicio y del número de puerto del protocolo de transporte](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml). Los servicios que no están en la lista de IANA pueden tener números de puerto en el intervalo comprendido entre 1024 y 65 535.

Se usan direcciones de red especiales para admitir mensajes de difusión de UDP en redes basadas en IP. En la siguiente explicación se usa como ejemplo la versión 4 de la familia de direcciones IP, usada en Internet.

Las direcciones IP de la versión 4 usan 32 bits para especificar una dirección de red. Para las direcciones de clase C que usan una máscara de red de 255.255.255.0, estos bits se dividen en cuatro octetos. Cuando se expresa en formato decimal, los cuatro octetos forman la conocida notación de cuatro dígitos separados por puntos, como 192.168.100.2. Los dos primeros octetos (192.168 en este ejemplo) forman el número de red, el tercer octeto (100) define la subred y el último octeto (2) es el identificador de host.

Al establecer todos los bits de una dirección IP en uno, o 255.255.255.255, se crea la dirección de difusión limitada. El envío de un datagrama UDP a esta dirección entrega el mensaje a todos los hosts del segmento de red local. Dado que los enrutadores nunca reenvían los mensajes enviados a esta dirección, solo los hosts del segmento de red recibirán el mensaje de difusión.

Las difusiones se pueden dirigir a partes específicas de una red estableciendo todos los bits del identificador de host. Por ejemplo, para enviar una difusión a todos los hosts de la red identificada por las direcciones IP que empiezan por 192.168.1, use la dirección 192.168.1.255.

En el ejemplo de código siguiente se usa un elemento <xref:System.Net.Sockets.UdpClient> para realizar escuchas de los datagramas UDP en el puerto 11 000. El cliente recibe una cadena de mensaje y escribe el mensaje en la consola.

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

En el siguiente ejemplo de código se usa <xref:System.Net.Sockets.Socket> para enviar datagramas UDP a la dirección de difusión dirigida 192.168.1.255 mediante el puerto 11.000. El cliente envía la cadena de mensaje especificada en la línea de comandos.

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

## <a name="see-also"></a>Vea también

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
