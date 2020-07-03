---
title: escuchas con sockets
description: Obtenga información sobre cómo crear un servicio remoto en el que un socket de servidor abre un puerto en la red y espera a que un cliente se conecte a ese puerto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: 0b6de67772bae397373e307ec02ce69a71b0542e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502319"
---
# <a name="listening-with-sockets"></a>escuchas con sockets
Los sockets de escucha o de servidor abren un puerto en la red y esperan a que un cliente se conecte a ese puerto. Aunque existen otros protocolos y familias de direcciones de red, en este ejemplo se muestra cómo crear un servicio remoto para una red TCP/IP.  
  
 La dirección única de un servicio TCP/IP se define mediante la combinación de la dirección IP del host con el número de puerto del servicio para crear un punto de conexión para el servicio. La clase <xref:System.Net.Dns> proporciona métodos que devuelven información sobre las direcciones de red compatibles con el dispositivo de red local. Cuando el dispositivo de red local tiene más de una dirección de red, o si el sistema local admite más de un dispositivo de red, la clase **Dns** devuelve información sobre todas las direcciones de red y la aplicación debe elegir la dirección correcta para el servicio. Internet Assigned Numbers Authority (Iana) define números de puerto para los servicios comunes; para obtener más información, vea [Registro del nombre de servicio y del número de puerto del protocolo de transporte](https://www.iana.org/assignments/port-numbers) Hay otros servicios que pueden tener registrados números de puerto en el intervalo comprendido entre 1024 y 65 535.  
  
 En el ejemplo siguiente se crea una clase <xref:System.Net.IPEndPoint> para un servidor mediante la combinación de la primera dirección IP devuelta por **Dns** para el equipo host con un número de puerto elegido entre el intervalo de números de puerto registrados.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Una vez que se ha determinado el punto de conexión local, es necesario asociar el <xref:System.Net.Sockets.Socket> con ese punto de conexión mediante el método <xref:System.Net.Sockets.Socket.Bind%2A> y establecerlo de modo que escuche en el punto de conexión mediante el método <xref:System.Net.Sockets.Socket.Listen%2A>. El método **Bind** produce una excepción si la combinación específica de dirección y puerto ya está en uso. En el ejemplo siguiente se muestra cómo asociar un **socket** con una clase **IPEndPoint**.  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp)
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 El método **Listen** toma un único parámetro que especifica cuántas conexiones pendientes con el **socket** se permiten antes de que se devuelva un error de servidor ocupado al cliente que intenta conectarse. En este caso, se colocan en la cola de conexión hasta 100 clientes antes de que se devuelva una respuesta de servidor ocupado al cliente 101.  
  
## <a name="see-also"></a>Vea también

- [Uso de un socket de servidor sincrónico](using-a-synchronous-server-socket.md)
- [Uso de un socket de servidor asincrónico](using-an-asynchronous-server-socket.md)
- [Uso de sockets de cliente](using-client-sockets.md)
- [Cómo: Crear un socket](how-to-create-a-socket.md)
- [Sockets](sockets.md)
