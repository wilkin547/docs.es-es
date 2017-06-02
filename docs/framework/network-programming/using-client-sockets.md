---
title: "Usar sockets de cliente | Microsoft Docs"
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
  - "protocolos de aplicaciones, sockets"
  - "enviar datos, sockets"
  - "solicitudes de datos, sockets"
  - "solicitar datos de Internet, sockets"
  - "recibir datos, sockets"
  - "Socket (clase), sockets de cliente"
  - "protocolos, sockets"
  - "Internet, sockets"
  - "sockets, sockets de cliente"
  - "sockets de cliente"
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Usar sockets de cliente
Antes de poder iniciar una conversación con <xref:System.Net.Sockets.Socket>, debe crear una canalización de datos entre la aplicación y el dispositivo remoto.  Aunque existen otras familias y protocolos de la dirección de red, las presentaciones de este ejemplo cómo crear una conexión de TCP\/IP a un servicio remoto.  
  
 TCP\/IP utiliza una dirección de red y un número de puerto de servicio para identificar un servicio.  La dirección de red identifica un dispositivo concreto en la red; el número de puerto identifica el servicio específico en el dispositivo para conectarse a.  Se llama a la combinación de dirección de red y de puerto de servicio un extremo, que se representa en .NET Framework para la clase de <xref:System.Net.EndPoint> .  Definen un descendiente de **EndPoint** para cada familia compatible de la dirección; para la familia de dirección IP, la clase es <xref:System.Net.IPEndPoint>.  
  
 La clase de <xref:System.Net.Dns> proporciona servicios de nombres de dominio\) a las aplicaciones que utilizan servicios Internet de TCP\/IP.  El método de <xref:System.Net.Dns.Resolve%2A> consulta a un servidor DNS para asignar un nombre de dominio descriptivo \(como “host.contoso.com”\) a una dirección de Internet numérica \(como 192.168.1.1\).  **Resolver** devuelve [IPHostEnty](frlrfsystemnetiphostentryclasstopic) que contiene una lista de direcciones y alias para el nombre solicitado.  En la mayoría de los casos, puede utilizar la primera dirección devuelta en la matriz de <xref:System.Net.IPHostEntry.AddressList%2A> .  El código siguiente obtiene <xref:System.Net.IPAddress> que contiene la dirección IP del servidor host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Internet Assigned Numbers Authority \(Iana\) define los números de puerto para los servicios comunes \(para obtener más información, vea www.iana.org\/assignments\/port\-numbers\).  Otros servicios pueden haber registrado los números de puerto en el intervalo de 1.024 a 65.535.  El código siguiente combina la dirección IP de host.contoso.com con un número de puerto para crear un extremo remoto para una conexión.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Después de determinar la dirección del dispositivo remoto y elegir un puerto para utilizar para la conexión, la aplicación puede intentar establecer una conexión con el dispositivo remoto.  El ejemplo siguiente utiliza **IPEndPoint** existente para conectarse a un dispositivo remoto y detecta cualquier excepción que se produce.  
  
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
  
## Vea también  
 [Usar un Socket de cliente sincrónico](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Usar un socket de cliente asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Cómo crear un socket](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)