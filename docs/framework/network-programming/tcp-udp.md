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
ms.openlocfilehash: ae6d2f9ced2235aa1b9b8fada8064d7e4be970a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502098"
---
# <a name="tcp-udp"></a><span data-ttu-id="4a25f-103">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="4a25f-103">TCP-UDP</span></span>
<span data-ttu-id="4a25f-104">Las aplicaciones pueden usar servicios de Protocolo de control de transmisión (TCP) y de Protocolo de datagramas de usuario (UDP) con las clases <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> y <xref:System.Net.Sockets.UdpClient>.</span><span class="sxs-lookup"><span data-stu-id="4a25f-104">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="4a25f-105">Estas clases de protocolo se basan en la clase <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> y se encargan de los detalles de la transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="4a25f-105">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="4a25f-106">Las clases de protocolo usan los métodos sincrónicos de la clase **Socket** para proporcionar un acceso sencillo y directo a los servicios de red sin la sobrecarga de mantener la información de estado o de conocer los detalles de la configuración de los sockets específicos del protocolo.</span><span class="sxs-lookup"><span data-stu-id="4a25f-106">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="4a25f-107">Para usar métodos **Socket** asincrónicos, puede usar los métodos asincrónicos proporcionados por la clase <xref:System.Net.Sockets.NetworkStream>.</span><span class="sxs-lookup"><span data-stu-id="4a25f-107">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="4a25f-108">Para obtener acceso a las características de la clase **Socket** no expuestas por las clases de protocolo, debe usar la clase **Socket**.</span><span class="sxs-lookup"><span data-stu-id="4a25f-108">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="4a25f-109">**TcpClient** y **TcpListener** representan la red mediante la clase **NetworkStream**.</span><span class="sxs-lookup"><span data-stu-id="4a25f-109">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="4a25f-110">Use el método <xref:System.Net.Sockets.TcpClient.GetStream%2A> para devolver la secuencia de red y, luego, llame a los métodos <xref:System.Net.Sockets.NetworkStream.Read%2A> y <xref:System.Net.Sockets.NetworkStream.Write%2A> de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4a25f-110">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="4a25f-111">La clase **NetworkStream** no posee el socket subyacente de las clases de protocolo, por lo que si la cierra no afectará al socket.</span><span class="sxs-lookup"><span data-stu-id="4a25f-111">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="4a25f-112">La clase **UdpClient** usa una matriz de bytes para almacenar el datagrama de UDP.</span><span class="sxs-lookup"><span data-stu-id="4a25f-112">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="4a25f-113">Use el método <xref:System.Net.Sockets.UdpClient.Send%2A> para enviar los datos a la red y el método <xref:System.Net.Sockets.UdpClient.Receive%2A> para recibir un datagrama entrante.</span><span class="sxs-lookup"><span data-stu-id="4a25f-113">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a25f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a25f-114">See also</span></span>

- [<span data-ttu-id="4a25f-115">Uso de servicios TCP</span><span class="sxs-lookup"><span data-stu-id="4a25f-115">Using TCP Services</span></span>](using-tcp-services.md)
- [<span data-ttu-id="4a25f-116">Uso de servicios UDP</span><span class="sxs-lookup"><span data-stu-id="4a25f-116">Using UDP Services</span></span>](using-udp-services.md)
- [<span data-ttu-id="4a25f-117">Uso de secuencias en la red</span><span class="sxs-lookup"><span data-stu-id="4a25f-117">Using Streams on the Network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="4a25f-118">Uso de un socket de servidor asincrónico</span><span class="sxs-lookup"><span data-stu-id="4a25f-118">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="4a25f-119">Uso de un socket de cliente asincrónico</span><span class="sxs-lookup"><span data-stu-id="4a25f-119">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="4a25f-120">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4a25f-120">Using Application Protocols</span></span>](using-application-protocols.md)
