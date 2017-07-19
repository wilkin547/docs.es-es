---
title: "Usar Servicios TCP | Microsoft Docs"
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
  - "solicitar datos de Internet, TCP"
  - "recibir datos, TCP"
  - "TcpClient (clase), acerca de la clase TcpClient"
  - "solicitudes de datos, TCP"
  - "protocolos de aplicaciones, TCP"
  - "recursos de red, TCP"
  - "enviar datos, TCP"
  - "TCP"
  - "protocolos, TCP"
  - "Internet, TCP"
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Usar Servicios TCP
La clase de <xref:System.Net.Sockets.TcpClient> solicita los datos de un recurso de internet mediante el TCP.  Los métodos y las propiedades de **TcpClient** resumen los detalles para crear <xref:System.Net.Sockets.Socket> para solicitar y recibir datos mediante TCP.  Dado que la conexión al dispositivo remoto se representa como una secuencia, los datos se pueden leer y escribir con .NET Framework secuencia\- que administra las técnicas.  
  
 El protocolo TCP establece una conexión con un extremo remoto y a las aplicaciones que conexión para enviar y recibir los paquetes de datos.  TCP es responsable de asegurarse de que los paquetes de datos se envían al extremo y se ensambla en el orden correcto cuando llegan.  
  
 Para establecer una conexión TCP, debe conocer la dirección del dispositivo de red que hospeda el servicio que necesite y debe conocer el puerto TCP que el servicio utiliza para comunicarse.  Internet Assigned Numbers Authority \(Iana\) define los números de puerto para los servicios comunes \(vea www.iana.org\/assignments\/port\-numbers\).  Los servicios no en la lista de IANA pueden tener números de puerto en el intervalo de 1.024 a 65.535.  
  
 El ejemplo siguiente se muestra la configuración de **TcpClient** para conectarse a un servidor de en el puerto TCP 13.  
  
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
  
 <xref:System.Net.Sockets.TcpListener> se utiliza para controlar un puerto TCP para las solicitudes entrantes y después para crear **Socket** o **TcpClient** que administra la conexión al cliente.  El método de <xref:System.Net.Sockets.TcpListener.Start%2A> permite escuchar, y el método de <xref:System.Net.Sockets.TcpListener.Stop%2A> deshabilita escuchar en el puerto.  El método de <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> acepta solicitudes de conexión entrante y crea **TcpClient** para controlar la solicitud, y el método de <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> acepta solicitudes de conexión entrante y crea **Socket** para controlar la solicitud.  
  
 El ejemplo siguiente muestra cómo crear un servidor horario de red mediante **TcpListener** al puerto TCP 13 de presentación.  Cuando se acepta una solicitud de conexión entrante, el servidor horario responde con la fecha y hora actual del servidor host.  
  
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
  
## Vea también  
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)