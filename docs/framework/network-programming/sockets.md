---
title: sockets
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: 4a1b18f2c31bf8dad8cf32e2e5205cf3008e7b18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136050"
---
# <a name="sockets"></a><span data-ttu-id="adda1-102">sockets</span><span class="sxs-lookup"><span data-stu-id="adda1-102">Sockets</span></span>
<span data-ttu-id="adda1-103">El espacio de nombres <xref:System.Net.Sockets> contiene una implementación administrada de la interfaz de Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="adda1-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="adda1-104">Las demás clases de acceso a la red del espacio de nombres <xref:System.Net> se basan en esta implementación de sockets.</span><span class="sxs-lookup"><span data-stu-id="adda1-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="adda1-105">La clase <xref:System.Net.Sockets.Socket> de .NET Framework es una versión de código administrado de los servicios de socket proporcionados por la API de Winsock32.</span><span class="sxs-lookup"><span data-stu-id="adda1-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="adda1-106">En la mayoría de los casos, los métodos de la clase **Socket** solo serializan los datos en sus equivalentes nativos de Win32 y controlan las comprobaciones de seguridad necesarias.</span><span class="sxs-lookup"><span data-stu-id="adda1-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="adda1-107">La clase **Socket** admite dos modos básicos, el modo sincrónico y el modo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="adda1-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="adda1-108">En el modo sincrónico, las llamadas a funciones que efectúan operaciones de red (como <xref:System.Net.Sockets.Socket.Send%2A> y <xref:System.Net.Sockets.Socket.Receive%2A>) esperan a que finalice la operación antes de devolver el control al programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="adda1-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="adda1-109">En el modo asincrónico, estas llamadas vuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="adda1-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adda1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="adda1-110">See also</span></span>

- [<span data-ttu-id="adda1-111">Cómo: Crear un socket</span><span class="sxs-lookup"><span data-stu-id="adda1-111">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)

- [<span data-ttu-id="adda1-112">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="adda1-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
