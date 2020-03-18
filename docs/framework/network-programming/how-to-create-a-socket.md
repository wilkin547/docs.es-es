---
title: Cómo crear un socket
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
ms.openlocfilehash: e71e7e235048361580c65bdb551919fe3038130b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180831"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="c4d63-102">Cómo crear un socket</span><span class="sxs-lookup"><span data-stu-id="c4d63-102">How to: Create a Socket</span></span>
<span data-ttu-id="c4d63-103">Para poder usar un socket a fin de comunicarse con dispositivos remotos, es necesario inicializarlo con la información del protocolo y de la dirección de red.</span><span class="sxs-lookup"><span data-stu-id="c4d63-103">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="c4d63-104">El constructor para la clase <xref:System.Net.Sockets.Socket> tiene parámetros que especifican la familia de direcciones, el tipo de socket y el tipo de protocolo que el socket usa para establecer conexiones.</span><span class="sxs-lookup"><span data-stu-id="c4d63-104">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d63-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4d63-105">Example</span></span>  
 <span data-ttu-id="c4d63-106">En el ejemplo siguiente se crea un socket que se puede usar para comunicarse en una red basada en TCP/IP, como Internet.</span><span class="sxs-lookup"><span data-stu-id="c4d63-106">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="c4d63-107">Para usar UDP en lugar de TCP, cambie el tipo de protocolo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4d63-107">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="c4d63-108">La enumeración <xref:System.Net.Sockets.AddressFamily> especifica las familias de direcciones estándar usadas por la clase **Socket** para resolver direcciones de red (por ejemplo, el miembro **AddressFamily.InterNetwork** especifica la familia de direcciones IP de versión 4).</span><span class="sxs-lookup"><span data-stu-id="c4d63-108">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="c4d63-109">La enumeración <xref:System.Net.Sockets.SocketType> especifica el tipo de socket (por ejemplo, el miembro **SocketType.Stream** indica un socket estándar para enviar y recibir datos con control de flujo).</span><span class="sxs-lookup"><span data-stu-id="c4d63-109">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="c4d63-110">La enumeración <xref:System.Net.Sockets.ProtocolType> especifica el protocolo de red que se va a usar al comunicarse en el **Socket** (por ejemplo, **ProtocolType.Tcp** indica que el socket usa TCP y **ProtocolType.Udp** indica que el socket usa UDP).</span><span class="sxs-lookup"><span data-stu-id="c4d63-110">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="c4d63-111">Una vez que se ha creado un **socket**, puede iniciar una conexión con un punto de conexión remoto o recibir conexiones procedentes de dispositivos remotos.</span><span class="sxs-lookup"><span data-stu-id="c4d63-111">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d63-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4d63-112">See also</span></span>

- [<span data-ttu-id="c4d63-113">Uso de sockets de cliente</span><span class="sxs-lookup"><span data-stu-id="c4d63-113">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="c4d63-114">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="c4d63-114">Listening with Sockets</span></span>](listening-with-sockets.md)
