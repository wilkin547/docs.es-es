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
# <a name="using-client-sockets"></a>Usar sockets de cliente

Antes de poder iniciar una conversación a través de un <xref:System.Net.Sockets.Socket>, debe crear una canalización de datos entre su aplicación y el dispositivo remoto. Aunque existen otros protocolos y familias de direcciones de red, en este ejemplo se muestra cómo crear una conexión TCP/IP a un servicio remoto.  
  
 TCP/IP usa una dirección de red y un número de puerto de servicio para identificar un servicio de forma única. La dirección de red identifica un dispositivo específico en la red; el número de puerto identifica el servicio específico en ese dispositivo al que conectarse. La combinación de puerto de servicio y dirección de red se denomina "punto de conexión", que en .NET Framework se representa mediante la clase <xref:System.Net.EndPoint>. Para cada familia de direcciones compatible se define un descendiente de **EndPoint**; para la familia de direcciones IP, la clase es <xref:System.Net.IPEndPoint>.  
  
 La clase <xref:System.Net.Dns> proporciona servicios de nombre de dominio a las aplicaciones que usan los servicios de Internet de TCP/IP. El método <xref:System.Net.Dns.Resolve%2A> consulta un servidor DNS para asignar un nombre de dominio descriptivo (por ejemplo, "host.contoso.com") a una dirección de Internet numérica (por ejemplo, 192.168.1.1). **Resolve** devuelve un <xref:System.Net.IPHostEntry> que contiene una lista de direcciones y alias para el nombre solicitado. En la mayoría de los casos, puede usar la primera dirección devuelta en la matriz <xref:System.Net.IPHostEntry.AddressList%2A>. El código siguiente obtiene una <xref:System.Net.IPAddress> que contiene la dirección IP para el servidor host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para obtener más información, vea [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro del nombre de servicio y del número de puerto del protocolo de transporte). Hay otros servicios que pueden tener registrados números de puerto en el intervalo comprendido entre 1024 y 65 535. El código siguiente combina la dirección IP para host.contoso.com con un número de puerto para crear un punto de conexión remoto para una conexión.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Una vez determinada la dirección del dispositivo remoto y elegido un puerto que se usará para la conexión, la aplicación puede intentar establecer una conexión con el dispositivo remoto. En el ejemplo siguiente se usa un **IPEndPoint** existente para conectarse a un dispositivo remoto y se detectan todas las excepciones que se generan.  
  
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
  
## <a name="see-also"></a>Vea también

- [Uso de un socket de cliente sincrónico](using-a-synchronous-client-socket.md)
- [Uso de un socket de cliente asincrónico](using-an-asynchronous-client-socket.md)
- [Cómo: Crear un socket](how-to-create-a-socket.md)
- [Sockets](sockets.md)
