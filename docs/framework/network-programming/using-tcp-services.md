---
title: Usar Servicios TCP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
ms.openlocfilehash: 3678586647dcf9c47b4494197fbf56cab865b3d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039488"
---
# <a name="using-tcp-services"></a>Usar Servicios TCP

La clase <xref:System.Net.Sockets.TcpClient> solicita datos de un recurso de Internet mediante TCP. Los métodos y propiedades de **TcpClient** abstraen los detalles para crear un <xref:System.Net.Sockets.Socket> a fin de solicitar y recibir datos mediante TCP. Dado que la conexión al dispositivo remoto se representa como una secuencia, los datos se pueden leer y escribir empleando técnicas de control de secuencias de .NET Framework.

El protocolo TCP establece una conexión con un punto de conexión remoto y luego usa esa conexión para enviar y recibir paquetes de datos. El protocolo TCP es responsable de garantizar que los paquetes de datos se envíen al punto de conexión y que se monten en el orden correcto cuando lleguen.

Para establecer una conexión TCP, debe conocer la dirección del dispositivo de red que hospeda el servicio que necesita, así como el puerto TCP que usa el servicio para comunicarse. Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para más información, vea [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro del nombre de servicio y del número de puerto del protocolo de transporte). Los servicios que no están en la lista de Iana pueden tener números de puerto en el intervalo comprendido entre 1024 y 65 535.

En el ejemplo siguiente se muestra cómo configurar un objeto **TcpClient** para conectarse a un servidor horario en el puerto TCP 13:

```vb
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeClient
    Private const portNum As Integer = 13
    Private const hostName As String = "host.contoso.com"

    ' Entry point  that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Try
            Dim client As New TcpClient(hostName, portNum)

            Dim ns As NetworkStream = client.GetStream()

            Dim bytes(1024) As Byte
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)

            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))

        Catch e As Exception
            Console.WriteLine(e.ToString())
        End Try

        client.Close()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<xref:System.Net.Sockets.TcpListener> se usa para supervisar un puerto TCP para las solicitudes entrantes y para luego crear un **Socket** o un **TcpClient** que administre la conexión al cliente. El método <xref:System.Net.Sockets.TcpListener.Start%2A> habilita las escuchas, mientras que el método <xref:System.Net.Sockets.TcpListener.Stop%2A> deshabilita las escuchas en el puerto. El método <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> acepta las solicitudes de conexión entrantes y crea un **TcpClient** para gestionar la solicitud, mientras que el método <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> acepta las solicitudes de conexión entrantes y crea un **Socket** para gestionar la solicitud.

En el ejemplo siguiente se muestra cómo crear un servidor horario de red mediante un **TcpListener** para supervisar el puerto TCP 13. Cuando se acepta una solicitud de conexión entrante, el servidor horario responde con la fecha y hora actuales del servidor host.

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

        listener.Start()

        While Not done
            Console.Write("Waiting for connection...")
            Dim client As TcpClient = listener.AcceptTcpClient()

            Console.WriteLine("Connection accepted.")
            Dim ns As NetworkStream = client.GetStream()

            Dim byteTime As Byte() = _
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())

            Try
                ns.Write(byteTime, 0, byteTime.Length)
                ns.Close()
                client.Close()
            Catch e As Exception
                Console.WriteLine(e.ToString())
            End Try
        End While

        listener.Stop()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
