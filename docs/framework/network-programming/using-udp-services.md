---
title: "Usar servicios UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "protocolos, UDP"
  - "recursos de red, UDP"
  - "solicitar datos de Internet, UDP"
  - "UDP"
  - "recibir datos, UDP"
  - "Internet, UDP"
  - "difundir mensajes a varias direcciones"
  - "solicitudes de datos, UDP"
  - "UdpClient (clase), acerca de la clase UdpClient"
  - "enviar datos, UDP"
  - "protocolos de aplicaciones, UDP"
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Usar servicios UDP
La clase de <xref:System.Net.Sockets.UdpClient> comunica con servicios de red mediante UDP.  Las propiedades y métodos de la clase de <xref:System.Net.Sockets.UdpClient> resumen los detalles de crear <xref:System.Net.Sockets.Socket> para solicitar y recibir datos mediante UDP.  
  
 El Protocolo de datagramas de usuario \(UDP\) es un protocolo simple que crea un mejor esfuerzo para entregar datos a un host remoto.  Sin embargo, dado que el protocolo UDP es un protocolo sin conexión, los datagramas de UDP enviados al extremo remoto no está garantizado proteger, ni son garantizaron para proteger en la misma secuencia en la que se envían.  Las aplicaciones que utilizan UDP se debe preparar para controlar missing, el duplicado, y datagramas de la hacia fuera\-de\- secuencia.  
  
 Para enviar un datagrama mediante UDP, debe conocer la dirección de red de un dispositivo de red que hospeda el servicio que necesite y el número de puerto UDP que el servicio utiliza para comunicarse.  Internet Assigned Numbers Authority \(Iana\) define los números de puerto para los servicios comunes \(vea www.iana.org\/assignments\/port\-numbers\).  Los servicios no en la lista de IANA pueden tener números de puerto en el intervalo de 1.024 a 65.535.  
  
 Utilizan las direcciones de red especiales para admitir los mensajes de difusión de UDP en redes IP\- basadas en.  La siguiente discusión utiliza la familia de la dirección de la versión 4 de IP utilizada en internet como ejemplo.  
  
 Las direcciones de la versión 4 de IP utilizan 32 bits para especificar una dirección de red.  Para las direcciones de C de la clase mediante una máscara de red de 255.255.255.0, estos bits se dividen en cuatro octetos.  Cuando se expresados en decimal, los cuatro octetos constituyen la notación familiar de puntear\- patio, como 192.168.100.2.  Los dos primeros octetos \(192,168 en este ejemplo\) forman el número de red, el tercer octeto \(100\) definen la subred, y el octeto final que \(2\) es el identificador del host.  
  
 Estableciendo todos los bits de una dirección IP en una, o 255.255.255.255, formularios la dirección de difusión limitada.  El envío de un datagrama de UDP esta dirección entrega el mensaje a cualquier hospedados en el segmento de red local.  Dado que los mensajes nunca hacia delante enviados a esta dirección, sólo los hosts enrutadores en el segmento de red reciben el mensaje de difusión.  
  
 Las difusiones se pueden dirigir a partes específicas de una red estableciendo todos los bits de identificador del host.  Por ejemplo, para enviar una difusión para todos los hosts de la red identificada por Direcciones IP que comienza con 192.168.1, use la dirección 192.168.1.255.  
  
 El ejemplo de código siguiente se utiliza <xref:System.Net.Sockets.UdpClient> para escuchar los datagramas de UDP enviados a la dirección de difusión dirigida 192.168.1.255 en el puerto 11.000.  El cliente recibe una cadena de mensaje y escribe el mensaje en la consola.  
  
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
  
 El ejemplo de código siguiente se utiliza <xref:System.Net.Sockets.UdpClient> para enviar los datagramas de UDP la dirección de difusión dirigida 192.168.1.255, utilizando el puerto 11.000.  El cliente envía la cadena de mensaje especificada en la línea de comandos.  
  
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
  
## Vea también  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)