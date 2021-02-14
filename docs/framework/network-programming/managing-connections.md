---
title: Administrar conexiones
description: Obtenga información sobre cómo las aplicaciones que usan HTTP para los recursos de datos pueden usar las clases ServicePoint y ServicePointManager de .NET Framework para administrar las conexiones.
ms.date: 01/25/2021
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
ms.openlocfilehash: 9ea93c3a9c484fd2a3de58b4d484b1e8445da155
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "99548063"
---
# <a name="managing-connections"></a><span data-ttu-id="14d62-103">Administrar conexiones</span><span class="sxs-lookup"><span data-stu-id="14d62-103">Managing Connections</span></span>

<span data-ttu-id="14d62-104">Las aplicaciones que usan HTTP para conectarse a los recursos de datos pueden usar las clases <xref:System.Net.ServicePoint> y <xref:System.Net.ServicePointManager> de .NET Framework para administrar las conexiones a Internet y lograr una escala y un rendimiento óptimos.</span><span class="sxs-lookup"><span data-stu-id="14d62-104">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="14d62-105">`ServicePoint` y `ServicePointManager` se consideran heredados en .NET Core, .NET 5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="14d62-105">`ServicePoint` and `ServicePointManager` are considered legacy on .NET Core, .NET 5, and later versions.</span></span> <span data-ttu-id="14d62-106">La mayoría de sus propiedades y métodos no se implementan en estas versiones.</span><span class="sxs-lookup"><span data-stu-id="14d62-106">Most of their properties and methods are not implemented in these versions.</span></span> <span data-ttu-id="14d62-107">Cuando se implementan, no afectan a las API de redes de `HttpClient` ni les hacen ningún seguimiento.</span><span class="sxs-lookup"><span data-stu-id="14d62-107">When they are implemented, they don't affect or track anything about `HttpClient` networking APIs.</span></span>
  
 <span data-ttu-id="14d62-108">La clase **ServicePoint** proporciona una aplicación con un punto de conexión al que la aplicación puede conectarse para tener acceso a recursos de Internet.</span><span class="sxs-lookup"><span data-stu-id="14d62-108">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="14d62-109">Cada **ServicePoint** contiene información que ayuda a optimizar las conexiones con un servidor de Internet mediante el uso compartido de información de optimización entre las conexiones para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14d62-109">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="14d62-110">Cada **ServicePoint** se identifica mediante un identificador uniforme de recursos (URI) y se clasifica por categorías según el identificador de esquema y los fragmentos de host del URI.</span><span class="sxs-lookup"><span data-stu-id="14d62-110">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="14d62-111">Por ejemplo, la propia instancia de **ServicePoint** proporcionaría solicitudes a los URI `http://www.contoso.com/index.htm` y `http://www.contoso.com/news.htm?date=today`, ya que tienen los mismos fragmentos de identificador de esquema (http) y host (`www.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="14d62-111">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="14d62-112">Si la aplicación ya tiene una conexión persistente con el servidor `www.contoso.com`, la usa para recuperar ambas solicitudes, con lo que evita la necesidad de crear dos conexiones.</span><span class="sxs-lookup"><span data-stu-id="14d62-112">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="14d62-113">**ServicePointManager** es una clase estática que administra la creación y la destrucción de instancias **ServicePoint**.</span><span class="sxs-lookup"><span data-stu-id="14d62-113">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="14d62-114">**ServicePointManager** crea una instancia **ServicePoint** cuando la aplicación solicita un recurso de Internet que no se encuentra en la colección de las instancias **ServicePoint** existentes.</span><span class="sxs-lookup"><span data-stu-id="14d62-114">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="14d62-115">Las instancias **ServicePoint** se destruyen cuando han superado su tiempo de inactividad máximo o cuando el número de instancias **ServicePoint** existentes supera el número máximo de instancias **ServicePoint** para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d62-115">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="14d62-116">Para controlar el tiempo de inactividad máximo predeterminado y el número máximo de instancias **ServicePoint**, establezca las propiedades <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> y <xref:System.Net.ServicePointManager.MaxServicePoints%2A> en **ServicePointManager**.</span><span class="sxs-lookup"><span data-stu-id="14d62-116">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="14d62-117">El número de conexiones entre un cliente y un servidor puede afectar considerablemente al rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d62-117">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="14d62-118">De forma predeterminada, una aplicación que usa la clase <xref:System.Net.HttpWebRequest> emplea un máximo de dos conexiones persistentes con un servidor determinado, pero es posible establecer el número máximo de conexiones según la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d62-118">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14d62-119">La especificación HTTP/1.1 limita el número de conexiones desde una aplicación a dos conexiones por servidor.</span><span class="sxs-lookup"><span data-stu-id="14d62-119">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="14d62-120">El número óptimo de conexiones depende de las condiciones reales en las que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d62-120">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="14d62-121">Si aumenta el número de conexiones disponibles para la aplicación, el rendimiento de la aplicación podría no verse afectado.</span><span class="sxs-lookup"><span data-stu-id="14d62-121">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="14d62-122">Para determinar el impacto de más conexiones, ejecute pruebas de rendimiento al variar el número de conexiones.</span><span class="sxs-lookup"><span data-stu-id="14d62-122">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="14d62-123">Puede cambiar el número de conexiones que usa una aplicación. Para ello, cambie la propiedad estática <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> en la clase **ServicePointManager** durante la inicialización de la aplicación, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="14d62-123">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="14d62-124">El hecho de cambiar la propiedad **ServicePointManager.DefaultConnectionLimit** no afecta a las instancias **ServicePoint** ya inicializadas.</span><span class="sxs-lookup"><span data-stu-id="14d62-124">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="14d62-125">En el siguiente código se muestra cómo cambiar el límite de conexiones en una instancia de **ServicePoint** existente para el servidor `http://www.contoso.com` al valor almacenado en `newLimit`.</span><span class="sxs-lookup"><span data-stu-id="14d62-125">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14d62-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d62-126">See also</span></span>

- [<span data-ttu-id="14d62-127">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="14d62-127">Connection Grouping</span></span>](connection-grouping.md)
- [<span data-ttu-id="14d62-128">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="14d62-128">Using Application Protocols</span></span>](using-application-protocols.md)
