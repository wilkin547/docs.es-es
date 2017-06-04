---
title: "Escuchas con sockets | Microsoft Docs"
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
  - "sockets, escuchas con sockets"
  - "solicitudes de datos, sockets"
  - "solicitar datos de Internet, sockets"
  - "recibir datos, sockets"
  - "protocolos, sockets"
  - "escuchas con sockets"
  - "Internet, sockets"
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Escuchas con sockets
Los sockets de agente de escucha o servidor abrir un puerto en la red y después se espera un cliente para conectarse a ese puerto.  Aunque existen otras familias y protocolos de la dirección de red, las presentaciones de este ejemplo cómo crear el servicio remoto para una red TCP\/IP.  
  
 Combinando la dirección IP del host con el número de puerto del servicio define la dirección única de un servicio TCP\/IP para crear un extremo para el servicio.  La clase de <xref:System.Net.Dns> proporciona métodos que devuelven información sobre las direcciones de red admitidos por el dispositivo de red local.  Cuando el dispositivo de red local tiene más de una dirección de red, o si la de sistema locales más de un dispositivo de red, la clase de **Dns** devuelve información sobre todas las direcciones de red, y la aplicación debe elegir el domicilio dirección adecuado de notificaciones.  Internet Assigned Numbers Authority \(Iana\) define los números de puerto para los servicios comunes \(para obtener más información, vea www.iana.org\/assignments\/port\-numbers\).  Otros servicios pueden haber registrado los números de puerto en el intervalo de 1.024 a 65.535.  
  
 El ejemplo siguiente se crea <xref:System.Net.IPEndPoint> para un servidor mediante la combinación de la primera dirección IP devuelta por **Dns** para el equipo host con un número de puerto determinado de los números de puerto registrados se extiende.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Después de que se determina el extremo local, <xref:System.Net.Sockets.Socket> debe estar asociado a ese extremo utilizando el método y el conjunto de <xref:System.Net.Sockets.Socket.Bind%2A> para escuchar en el extremo utilizando el método de <xref:System.Net.Sockets.Socket.Listen%2A> .  **Enlazar** produce una excepción si la combinación de dirección concreta y el puerto ya está en uso.  El ejemplo siguiente se muestra la asociación de **Socket** a **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 El método de **Listen** toma un único parámetro que especifique cuántas conexiones pendientes a **Socket** se permiten antes de que un error No disponible del servidor se devuelve al cliente de conexión.  En este caso, colocan hasta 100 clientes en la cola de la conexión antes de que una respuesta No disponible del servidor se devuelve al cliente número 101.  
  
## Vea también  
 [Usar un socket de servidor sincrónico](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Usar un socket de servidor asincrónico](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Usar sockets de cliente](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Cómo crear un socket](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)