---
title: Usar Servicios TCP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 11
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f462e99ecc78ddd6bcf3f231f712da8b04c71850
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="using-tcp-services"></a>Usar Servicios TCP
La clase <xref:System.Net.Sockets.TcpClient> solicita datos de un recurso de Internet mediante TCP. Los métodos y propiedades de **TcpClient** abstraen los detalles para crear un <xref:System.Net.Sockets.Socket> a fin de solicitar y recibir datos mediante TCP. Dado que la conexión al dispositivo remoto se representa como una secuencia, los datos se pueden leer y escribir empleando técnicas de control de secuencias de .NET Framework.  
  
 El protocolo TCP establece una conexión con un punto de conexión remoto y luego usa esa conexión para enviar y recibir paquetes de datos. El protocolo TCP es responsable de garantizar que los paquetes de datos se envíen al punto de conexión y que se monten en el orden correcto cuando lleguen.  
  
 Para establecer una conexión TCP, debe conocer la dirección del dispositivo de red que hospeda el servicio que necesita, así como el puerto TCP que usa el servicio para comunicarse. Internet Assigned Numbers Authority (Iana) define los números de puerto para los servicios comunes (vea www.iana.org/assignments/port-numbers). Los servicios que no están en la lista de Iana pueden tener números de puerto en el intervalo comprendido entre 1024 y 65 535.  
  
 En el ejemplo siguiente se muestra cómo configurar un **TcpClient** para conectarse a un servidor horario en el puerto TCP 13.  
  
```vb  
Imports System  
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
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
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
    End Function 'Main  
End Class 'TcpTimeClient  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <xref:System.Net.Sockets.TcpListener> se usa para supervisar un puerto TCP para las solicitudes entrantes y para luego crear un **Socket** o un **TcpClient** que administre la conexión al cliente. El método <xref:System.Net.Sockets.TcpListener.Start%2A> habilita las escuchas, mientras que el método <xref:System.Net.Sockets.TcpListener.Stop%2A> deshabilita las escuchas en el puerto. El método <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> acepta las solicitudes de conexión entrantes y crea un **TcpClient** para gestionar la solicitud, mientras que el método <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> acepta las solicitudes de conexión entrantes y crea un **Socket** para gestionar la solicitud.  
  
 En el ejemplo siguiente se muestra cómo crear un servidor horario de red mediante un **TcpListener** para supervisar el puerto TCP 13. Cuando se acepta una solicitud de conexión entrante, el servidor horario responde con la fecha y hora actuales del servidor host.  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
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
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## <a name="see-also"></a>Vea también  
 

