---
title: Procedimientos recomendados para las clases System.Net
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
ms.openlocfilehash: c7324dcbc27c95c7d799592700d46c195e7d952b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048891"
---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="03fb8-102">Procedimientos recomendados para las clases System.Net</span><span class="sxs-lookup"><span data-stu-id="03fb8-102">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="03fb8-103">Las siguientes recomendaciones le ayudarán a usar las clases incluidas en <xref:System.Net> para su beneficio:</span><span class="sxs-lookup"><span data-stu-id="03fb8-103">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
- <span data-ttu-id="03fb8-104">Para más información sobre los procedimientos recomendados sobre la Seguridad de la capa de transporte (TLS), vea [Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework](tls.md).</span><span class="sxs-lookup"><span data-stu-id="03fb8-104">For Transport Layer Security (TLS) best practices, see [Transport Layer Security (TLS) best practices with .NET Framework](tls.md).</span></span>

- <span data-ttu-id="03fb8-105">Use <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> siempre que sea posible en lugar de la conversión de tipos en clases descendientes.</span><span class="sxs-lookup"><span data-stu-id="03fb8-105">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="03fb8-106">Las aplicaciones que usan **WebRequest** y **WebResponse** pueden aprovechar los nuevos protocolos de Internet sin necesidad de grandes cambios de código.</span><span class="sxs-lookup"><span data-stu-id="03fb8-106">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
- <span data-ttu-id="03fb8-107">Al escribir aplicaciones ASP.NET que se ejecutan en un servidor mediante las clases **System.Net**, a menudo es mejor, desde la perspectiva del rendimiento, usar los métodos asincrónicos de <xref:System.Net.WebRequest.GetResponse%2A> y <xref:System.Net.WebResponse.GetResponseStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="03fb8-107">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
- <span data-ttu-id="03fb8-108">El número de conexiones abiertas a un recurso de Internet puede tener un impacto considerable en el rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="03fb8-108">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="03fb8-109">**System.Net** usa dos conexiones por aplicación y por host de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03fb8-109">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="03fb8-110">El establecimiento de la propiedad <xref:System.Net.ServicePoint.ConnectionLimit%2A> en el <xref:System.Net.ServicePoint> de la aplicación puede aumentar este número para un host determinado.</span><span class="sxs-lookup"><span data-stu-id="03fb8-110">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="03fb8-111">El establecimiento de la propiedad <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> puede aumentar este valor predeterminado para todos los hosts.</span><span class="sxs-lookup"><span data-stu-id="03fb8-111">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> property can increase this default for all hosts.</span></span>  
  
- <span data-ttu-id="03fb8-112">Cuando escriba protocolos de nivel de socket, procure usar <xref:System.Net.Sockets.TcpClient> o <xref:System.Net.Sockets.UdpClient> siempre que sea posible en lugar de escribir directamente en un <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="03fb8-112">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="03fb8-113">Estas dos clases de cliente encapsulan la creación de sockets TCP y UDP sin que sea necesario controlar los detalles de la conexión.</span><span class="sxs-lookup"><span data-stu-id="03fb8-113">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
- <span data-ttu-id="03fb8-114">Al acceder a sitios que requieren credenciales, use la clase <xref:System.Net.CredentialCache> para crear una memoria caché de credenciales en lugar de proporcionarlas con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="03fb8-114">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="03fb8-115">La clase **CredentialCache** busca en la memoria caché para encontrar la credencial adecuada que debe presentar con una solicitud, lo cual elimina la responsabilidad de crear y presentar credenciales según la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="03fb8-115">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03fb8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="03fb8-116">See also</span></span>

- [<span data-ttu-id="03fb8-117">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="03fb8-117">Network Programming in the .NET Framework</span></span>](index.md)
