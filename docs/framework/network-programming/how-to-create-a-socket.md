---
title: Procedimiento para crear un socket
description: Obtenga información sobre cómo inicializar un socket para comunicarse con dispositivos remotos. Use la clase Socket para especificar la familia de direcciones, el tipo de socket y el tipo de protocolo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: 1d56ddea721b54192a7dd47d144b6c41bbb9a5d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502553"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="0ad87-104">Procedimiento para crear un socket</span><span class="sxs-lookup"><span data-stu-id="0ad87-104">How to: Create a Socket</span></span>
<span data-ttu-id="0ad87-105">Para poder usar un socket a fin de comunicarse con dispositivos remotos, es necesario inicializarlo con la información del protocolo y de la dirección de red.</span><span class="sxs-lookup"><span data-stu-id="0ad87-105">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="0ad87-106">El constructor para la clase <xref:System.Net.Sockets.Socket> tiene parámetros que especifican la familia de direcciones, el tipo de socket y el tipo de protocolo que el socket usa para establecer conexiones.</span><span class="sxs-lookup"><span data-stu-id="0ad87-106">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad87-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ad87-107">Example</span></span>  
 <span data-ttu-id="0ad87-108">En el ejemplo siguiente se crea un socket que se puede usar para comunicarse en una red basada en TCP/IP, como Internet.</span><span class="sxs-lookup"><span data-stu-id="0ad87-108">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="0ad87-109">Para usar UDP en lugar de TCP, cambie el tipo de protocolo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ad87-109">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="0ad87-110">La enumeración <xref:System.Net.Sockets.AddressFamily> especifica las familias de direcciones estándar usadas por la clase **Socket** para resolver direcciones de red (por ejemplo, el miembro **AddressFamily.InterNetwork** especifica la familia de direcciones IP de versión 4).</span><span class="sxs-lookup"><span data-stu-id="0ad87-110">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="0ad87-111">La enumeración <xref:System.Net.Sockets.SocketType> especifica el tipo de socket (por ejemplo, el miembro **SocketType.Stream** indica un socket estándar para enviar y recibir datos con control de flujo).</span><span class="sxs-lookup"><span data-stu-id="0ad87-111">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="0ad87-112">La enumeración <xref:System.Net.Sockets.ProtocolType> especifica el protocolo de red que se va a usar al comunicarse en el **Socket** (por ejemplo, **ProtocolType.Tcp** indica que el socket usa TCP y **ProtocolType.Udp** indica que el socket usa UDP).</span><span class="sxs-lookup"><span data-stu-id="0ad87-112">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="0ad87-113">Una vez que se ha creado un **socket**, puede iniciar una conexión con un punto de conexión remoto o recibir conexiones procedentes de dispositivos remotos.</span><span class="sxs-lookup"><span data-stu-id="0ad87-113">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad87-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad87-114">See also</span></span>

- [<span data-ttu-id="0ad87-115">Uso de sockets de cliente</span><span class="sxs-lookup"><span data-stu-id="0ad87-115">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="0ad87-116">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="0ad87-116">Listening with Sockets</span></span>](listening-with-sockets.md)
