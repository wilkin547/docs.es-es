---
title: "Conexión de redes punto a punto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d3ef21d4ab431ea4e1e1ac0392b3f088a7053c80
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="c2215-102">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="c2215-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="c2215-103">El canal del mismo nivel es una tecnología de comunicaciones punto a punto (P2P) entre varias partes de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2215-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="c2215-104">Proporciona un canal de comunicación P2P basado en mensajes seguros y escalables para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c2215-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="c2215-105">Un ejemplo común de una aplicación con varias partes que se puede beneficiar del canal del mismo nivel es el caso de una aplicación de colaboración, como el chat, donde un grupo de personas conversan entre ellas de igual a igual, sin necesidad de servidores.</span><span class="sxs-lookup"><span data-stu-id="c2215-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="c2215-106">Peer Channel habilita la colaboración P2P la distribución del contenido, el equilibrio de la carga y el procesamiento distribuido de los escenarios de consumidor y empresa.</span><span class="sxs-lookup"><span data-stu-id="c2215-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="c2215-107">El canal del mismo nivel está habilitado de forma predeterminada en [!INCLUDE[wv](../../../../includes/wv-md.md)], como lo está también todo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2215-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="c2215-108">Para tener acceso a las clases del canal del mismo nivel, agregue en su proyecto referencias a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="c2215-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="c2215-109">En las secciones siguientes se ofrece información sobre la conexión de red punto a punto y el uso de las clases de canal del mismo nivel para crear aplicaciones de red habilitadas para el mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c2215-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2215-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c2215-110">In This Section</span></span>  
 <span data-ttu-id="c2215-111">[Escenarios de canal de mismo nivel](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): describe los escenarios de implementación admitidos por las API de canal del mismo nivel, como mensajería, colaboración, publicación/suscripción procesamiento distribuido y los juegos.</span><span class="sxs-lookup"><span data-stu-id="c2215-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="c2215-112">[Conceptos del canal del mismo nivel](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): describe las mallas del mismo nivel, nodos del mismo nivel, la seguridad del canal del mismo nivel y resoluciones del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c2215-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="c2215-113">[Creación de una aplicación de canal del mismo nivel](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): proporciona instrucciones sobre cómo desarrollar aplicaciones de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c2215-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="c2215-114">Ejemplos de código del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c2215-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="c2215-115">Resolución personalizada del mismo nivel de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c2215-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/en-us/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="c2215-116">Blog del equipo del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c2215-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="c2215-117">[Blog del equipo de canal del mismo nivel](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="c2215-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
