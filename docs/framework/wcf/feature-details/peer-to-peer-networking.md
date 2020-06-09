---
title: Conexión de redes punto a punto
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 42bda754afa58354c087e587e500bebfe72169f4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600768"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="e5c14-102">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="e5c14-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="e5c14-103">El canal del mismo nivel es una tecnología de comunicación punto a punto (P2P) en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e5c14-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="e5c14-104">Proporciona un canal de comunicación P2P basado en mensajes seguros y escalables para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e5c14-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="e5c14-105">Un ejemplo común de una aplicación con varias partes que se puede beneficiar del canal del mismo nivel es el caso de una aplicación de colaboración, como el chat, donde un grupo de personas conversan entre ellas de igual a igual, sin necesidad de servidores.</span><span class="sxs-lookup"><span data-stu-id="e5c14-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="e5c14-106">Peer Channel habilita la colaboración P2P la distribución del contenido, el equilibrio de la carga y el procesamiento distribuido de los escenarios de consumidor y empresa.</span><span class="sxs-lookup"><span data-stu-id="e5c14-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="e5c14-107">El canal del mismo nivel está habilitado de forma predeterminada en Windows Vista, como es todo WCF.</span><span class="sxs-lookup"><span data-stu-id="e5c14-107">Peer Channel is enabled by default on Windows Vista, as is all of WCF.</span></span> <span data-ttu-id="e5c14-108">Para tener acceso a las clases del canal del mismo nivel, agregue en su proyecto referencias a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="e5c14-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="e5c14-109">En las secciones siguientes se ofrece información sobre la conexión de red punto a punto y el uso de las clases de canal del mismo nivel para crear aplicaciones de red habilitadas para el mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e5c14-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5c14-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e5c14-110">In This Section</span></span>  
 <span data-ttu-id="e5c14-111">[Escenarios de canal del mismo nivel](peer-channel-scenarios.md): describe los escenarios de desarrollo admitidos por las API de canal del mismo nivel, como la mensajería de publicación/suscripción, la colaboración, el procesamiento distribuido y los juegos.</span><span class="sxs-lookup"><span data-stu-id="e5c14-111">[Peer Channel Scenarios](peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="e5c14-112">[Conceptos de canal del mismo nivel](peer-channel-concepts.md): describe las mallas del mismo nivel, los nodos del mismo nivel, la seguridad del canal del mismo nivel y las resoluciones del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e5c14-112">[Peer Channel Concepts](peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="e5c14-113">[Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md): proporciona instrucciones sobre el desarrollo de aplicaciones de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e5c14-113">[Building a Peer Channel Application](building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="e5c14-114">Ejemplos de código del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e5c14-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="e5c14-115">[Resolución personalizada del mismo nivel de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e5c14-115">[Peer Channel Custom Peer Resolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="e5c14-116">Blog del equipo del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e5c14-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="e5c14-117">Blog del equipo de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e5c14-117">Peer Channel Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/peerchan/)
