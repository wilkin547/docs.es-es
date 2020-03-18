---
title: Permisos de web y socket
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: d1b993acbf20eac244e596075c3f826bba3211a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71046863"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="d4d84-102">Permisos de web y socket</span><span class="sxs-lookup"><span data-stu-id="d4d84-102">Web and Socket Permissions</span></span>
<span data-ttu-id="d4d84-103">La seguridad de Internet para las aplicaciones que usan el espacio de nombres <xref:System.Net> se proporciona con las clases <xref:System.Net.WebPermission> y <xref:System.Net.SocketPermission>.</span><span class="sxs-lookup"><span data-stu-id="d4d84-103">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="d4d84-104">La clase **WebPermission** controla el derecho de una aplicación a solicitar datos de un identificador URI o de servir un identificador URI en Internet.</span><span class="sxs-lookup"><span data-stu-id="d4d84-104">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="d4d84-105">La clase **SocketPermission** controla el derecho de una aplicación a usar un <xref:System.Net.Sockets.Socket> para aceptar los datos en un puerto local o de ponerse en contacto con dispositivos remotos mediante un protocolo de transporte en otra dirección, en función del host, el número de puerto y el protocolo de transporte del socket.</span><span class="sxs-lookup"><span data-stu-id="d4d84-105">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="d4d84-106">La clase de permiso que se use dependerá del tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4d84-106">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="d4d84-107">Las aplicaciones que utilizan <xref:System.Net.WebRequest> y sus descendientes deben usar la clase **WebPermission** para administrar los permisos.</span><span class="sxs-lookup"><span data-stu-id="d4d84-107">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="d4d84-108">Las aplicaciones que utilizan el acceso de nivel de socket deben usar la clase **SocketPermission** para administrar los permisos.</span><span class="sxs-lookup"><span data-stu-id="d4d84-108">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="d4d84-109">**WebPermission** y **SocketPermission** definen dos permisos: el de aceptación y el de conexión.</span><span class="sxs-lookup"><span data-stu-id="d4d84-109">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="d4d84-110">El permiso de aceptación permite a la aplicación responder a una conexión entrante desde otra entidad.</span><span class="sxs-lookup"><span data-stu-id="d4d84-110">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="d4d84-111">El permiso de conexión permite a la aplicación iniciar una conexión con otra entidad.</span><span class="sxs-lookup"><span data-stu-id="d4d84-111">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="d4d84-112">Para las instancias **SocketPermission**, el permiso de aceptación implica que una aplicación puede aceptar conexiones entrantes en una dirección de transporte local, mientras que el permiso de conexión implica que una aplicación puede conectarse a alguna dirección de transporte remota (o local).</span><span class="sxs-lookup"><span data-stu-id="d4d84-112">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="d4d84-113">Para las instancias **WebPermission**, el permiso de aceptación implica que una aplicación puede exportar al mundo el identificador URI controlado por **WebPermission**, mientras que el permiso de conexión implica que una aplicación puede obtener acceso a ese URI (ya sea local o remoto).</span><span class="sxs-lookup"><span data-stu-id="d4d84-113">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d84-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4d84-114">See also</span></span>

- [<span data-ttu-id="d4d84-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d4d84-115">Security</span></span>](../../standard/security/index.md)
- [<span data-ttu-id="d4d84-116">Seguridad en la programación para redes</span><span class="sxs-lookup"><span data-stu-id="d4d84-116">Security in Network Programming</span></span>](security-in-network-programming.md)
