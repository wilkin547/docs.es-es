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
ms.openlocfilehash: 8f0c34b2226863bc04800ac4558c07e969f02154
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "50191134"
---
# <a name="using-udp-services"></a>Usar servicios UDP
La clase <xref:System.Net.Sockets.UdpClient> se comunica con los servicios de red mediante UDP. Las propiedades y métodos de la clase <xref:System.Net.Sockets.UdpClient> abstraen los detalles de la creación de un <xref:System.Net.Sockets.Socket> para solicitar y recibir datos mediante UDP.  
  
 El Protocolo de datagramas de usuario (UDP) es un protocolo simple que hace todo lo posible para entregar datos a un host remoto. Pero como el protocolo UDP es un protocolo sin conexión, no se garantiza que lleguen los datagramas de UDP enviados al punto de conexión remoto, ni tampoco se garantiza que lleguen en la misma secuencia en la que se envían. Las aplicaciones que usan UDP deben estar preparadas para controlar los datagramas que faltan, los datagramas duplicados y los datagramas que están fuera de secuencia.  
  
 Para enviar un datagrama mediante UDP, debe conocer la dirección de red del dispositivo de red que hospeda el servicio que necesita, así como el número de puerto UDP que usa el servicio para comunicarse. Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para más información, vea [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro del nombre de servicio y del número de puerto del protocolo de transporte). Los servicios que no están en la lista de Iana pueden tener números de puerto en el intervalo comprendido entre 1024 y 65 535.  
  
 Se usan direcciones de red especiales para admitir mensajes de difusión de UDP en redes basadas en IP. En la siguiente explicación se usa como ejemplo la versión 4 de la familia de direcciones IP, usada en Internet.  
  
 Las direcciones IP de la versión 4 usan 32 bits para especificar una dirección de red. Para las direcciones de clase C que usan una máscara de red de 255.255.255.0, estos bits se dividen en cuatro octetos. Cuando se expresa en formato decimal, los cuatro octetos forman la conocida notación de cuatro dígitos separados por puntos, como 192.168.100.2. Los dos primeros octetos (192.168 en este ejemplo) forman el número de red, el tercer octeto (100) define la subred y el último octeto (2) es el identificador de host.  
  
 Al establecer todos los bits de una dirección IP en uno, o 255.255.255.255, se crea la dirección de difusión limitada. El envío de un datagrama UDP a esta dirección entrega el mensaje a todos los hosts del segmento de red local. Dado que los enrutadores nunca reenvían los mensajes enviados a esta dirección, solo los hosts del segmento de red recibirán el mensaje de difusión.  
  
 Las difusiones se pueden dirigir a partes específicas de una red estableciendo todos los bits del identificador de host. Por ejemplo, para enviar una difusión a todos los hosts de la red identificada por las direcciones IP que empiezan por 192.168.1, use la dirección 192.168.1.255.  
  
 En el siguiente ejemplo de código se usa <xref:System.Net.Sockets.UdpClient> para efectuar escuchas para los datagramas UDP enviados a la dirección de difusión dirigida 192.168.1.255 en el puerto 11.000. El cliente recibe una cadena de mensaje y escribe el mensaje en la consola.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
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
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 En el siguiente ejemplo de código se usa <xref:System.Net.Sockets.UdpClient> para enviar datagramas UDP a la dirección de difusión dirigida 192.168.1.255 mediante el puerto 11.000. El cliente envía la cadena de mensaje especificada en la línea de comandos.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
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
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.Sockets.UdpClient>  
 <xref:System.Net.IPAddress>  
 
