---
title: Administrar conexiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
ms.openlocfilehash: 11c17c6893800fce8bbff8f49b3a207c161bcdfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047645"
---
# <a name="managing-connections"></a><span data-ttu-id="67738-102">Administrar conexiones</span><span class="sxs-lookup"><span data-stu-id="67738-102">Managing Connections</span></span>
<span data-ttu-id="67738-103">Las aplicaciones que usan HTTP para conectarse a los recursos de datos pueden usar las clases <xref:System.Net.ServicePoint> y <xref:System.Net.ServicePointManager> de .NET Framework para administrar las conexiones a Internet y lograr una escala y un rendimiento óptimos.</span><span class="sxs-lookup"><span data-stu-id="67738-103">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  
  
 <span data-ttu-id="67738-104">La clase **ServicePoint** proporciona una aplicación con un punto de conexión al que la aplicación puede conectarse para tener acceso a recursos de Internet.</span><span class="sxs-lookup"><span data-stu-id="67738-104">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="67738-105">Cada **ServicePoint** contiene información que ayuda a optimizar las conexiones con un servidor de Internet mediante el uso compartido de información de optimización entre las conexiones para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="67738-105">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="67738-106">Cada **ServicePoint** se identifica mediante un identificador uniforme de recursos (URI) y se clasifica por categorías según el identificador de esquema y los fragmentos de host del URI.</span><span class="sxs-lookup"><span data-stu-id="67738-106">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="67738-107">Por ejemplo, la propia instancia de **ServicePoint** proporcionaría solicitudes a los URI `http://www.contoso.com/index.htm` y `http://www.contoso.com/news.htm?date=today`, ya que tienen los mismos fragmentos de identificador de esquema (http) y host (`www.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="67738-107">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="67738-108">Si la aplicación ya tiene una conexión persistente con el servidor `www.contoso.com`, la usa para recuperar ambas solicitudes, con lo que evita la necesidad de crear dos conexiones.</span><span class="sxs-lookup"><span data-stu-id="67738-108">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="67738-109">**ServicePointManager** es una clase estática que administra la creación y la destrucción de instancias **ServicePoint**.</span><span class="sxs-lookup"><span data-stu-id="67738-109">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="67738-110">**ServicePointManager** crea una instancia **ServicePoint** cuando la aplicación solicita un recurso de Internet que no se encuentra en la colección de las instancias **ServicePoint** existentes.</span><span class="sxs-lookup"><span data-stu-id="67738-110">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="67738-111">Las instancias **ServicePoint** se destruyen cuando han superado su tiempo de inactividad máximo o cuando el número de instancias **ServicePoint** existentes supera el número máximo de instancias **ServicePoint** para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67738-111">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="67738-112">Para controlar el tiempo de inactividad máximo predeterminado y el número máximo de instancias **ServicePoint**, establezca las propiedades <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> y <xref:System.Net.ServicePointManager.MaxServicePoints%2A> en **ServicePointManager**.</span><span class="sxs-lookup"><span data-stu-id="67738-112">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="67738-113">El número de conexiones entre un cliente y un servidor puede afectar considerablemente al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67738-113">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="67738-114">De forma predeterminada, una aplicación que usa la clase <xref:System.Net.HttpWebRequest> emplea un máximo de dos conexiones persistentes con un servidor determinado, pero es posible establecer el número máximo de conexiones según la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67738-114">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67738-115">La especificación HTTP/1.1 limita el número de conexiones desde una aplicación a dos conexiones por servidor.</span><span class="sxs-lookup"><span data-stu-id="67738-115">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="67738-116">El número óptimo de conexiones depende de las condiciones reales en las que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67738-116">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="67738-117">Si aumenta el número de conexiones disponibles para la aplicación, el rendimiento de la aplicación podría no verse afectado.</span><span class="sxs-lookup"><span data-stu-id="67738-117">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="67738-118">Para determinar el impacto de más conexiones, ejecute pruebas de rendimiento al variar el número de conexiones.</span><span class="sxs-lookup"><span data-stu-id="67738-118">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="67738-119">Puede cambiar el número de conexiones que usa una aplicación. Para ello, cambie la propiedad estática <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> en la clase **ServicePointManager** durante la inicialización de la aplicación, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="67738-119">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="67738-120">El hecho de cambiar la propiedad **ServicePointManager.DefaultConnectionLimit** no afecta a las instancias **ServicePoint** ya inicializadas.</span><span class="sxs-lookup"><span data-stu-id="67738-120">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="67738-121">En el siguiente código se muestra cómo cambiar el límite de conexiones en una instancia de **ServicePoint** existente para el servidor `http://www.contoso.com` al valor almacenado en `newLimit`.</span><span class="sxs-lookup"><span data-stu-id="67738-121">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="67738-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="67738-122">See also</span></span>

- [<span data-ttu-id="67738-123">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="67738-123">Connection Grouping</span></span>](connection-grouping.md)
- [<span data-ttu-id="67738-124">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="67738-124">Using Application Protocols</span></span>](using-application-protocols.md)
