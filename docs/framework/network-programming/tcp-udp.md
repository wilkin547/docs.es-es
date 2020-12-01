---
title: TCP-UDP
description: Obtenga información sobre las clases TcpClient, TcpListener y UdpClient y el modo en que controlan los servicios TCP y UDP, encargados de los detalles de la transferencia de datos en .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
ms.openlocfilehash: b5b8b5cb3ce38fcff9115b2f9acf23fc5a970adf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239451"
---
# <a name="tcp-udp"></a>TCP-UDP

Las aplicaciones pueden usar servicios de Protocolo de control de transmisión (TCP) y de Protocolo de datagramas de usuario (UDP) con las clases <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> y <xref:System.Net.Sockets.UdpClient>. Estas clases de protocolo se basan en la clase <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> y se encargan de los detalles de la transferencia de datos.  
  
 Las clases de protocolo usan los métodos sincrónicos de la clase **Socket** para proporcionar un acceso sencillo y directo a los servicios de red sin la sobrecarga de mantener la información de estado o de conocer los detalles de la configuración de los sockets específicos del protocolo. Para usar métodos **Socket** asincrónicos, puede usar los métodos asincrónicos proporcionados por la clase <xref:System.Net.Sockets.NetworkStream>. Para obtener acceso a las características de la clase **Socket** no expuestas por las clases de protocolo, debe usar la clase **Socket**.  
  
 **TcpClient** y **TcpListener** representan la red mediante la clase **NetworkStream**. Use el método <xref:System.Net.Sockets.TcpClient.GetStream%2A> para devolver la secuencia de red y, luego, llame a los métodos <xref:System.Net.Sockets.NetworkStream.Read%2A> y <xref:System.Net.Sockets.NetworkStream.Write%2A> de la secuencia. La clase **NetworkStream** no posee el socket subyacente de las clases de protocolo, por lo que si la cierra no afectará al socket.  
  
 La clase **UdpClient** usa una matriz de bytes para almacenar el datagrama de UDP. Use el método <xref:System.Net.Sockets.UdpClient.Send%2A> para enviar los datos a la red y el método <xref:System.Net.Sockets.UdpClient.Receive%2A> para recibir un datagrama entrante.  
  
## <a name="see-also"></a>Vea también

- [Uso de servicios TCP](using-tcp-services.md)
- [Uso de servicios UDP](using-udp-services.md)
- [Uso de secuencias en la red](using-streams-on-the-network.md)
- [Uso de un socket de servidor asincrónico](using-an-asynchronous-server-socket.md)
- [Uso de un socket de cliente asincrónico](using-an-asynchronous-client-socket.md)
- [Usar protocolos de aplicaciones](using-application-protocols.md)
