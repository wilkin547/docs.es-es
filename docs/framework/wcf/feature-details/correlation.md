---
title: "Correlación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc1608cc4e746af56e7d89237f0c1f5e6cc3bc7e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="correlation"></a><span data-ttu-id="bf46a-102">Correlación</span><span class="sxs-lookup"><span data-stu-id="bf46a-102">Correlation</span></span>
<span data-ttu-id="bf46a-103">Cuando las aplicaciones de servicio de flujo de trabajo se comunican con otros servicios, es importante que los mensajes entre ellos se envíen a la instancia de flujo de trabajo adecuada.</span><span class="sxs-lookup"><span data-stu-id="bf46a-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="bf46a-104">La correlación proporciona el mecanismo para ello.</span><span class="sxs-lookup"><span data-stu-id="bf46a-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="bf46a-105">Los temas de esta sección proporcionan información general sobre la correlación y sobre cómo utilizarla en diversos casos de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf46a-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf46a-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bf46a-106">In This Section</span></span>  
 [<span data-ttu-id="bf46a-107">Información general de correlación</span><span class="sxs-lookup"><span data-stu-id="bf46a-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="bf46a-108">Proporciona información general sobre los tipos de correlación disponibles en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf46a-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="bf46a-109">Intercambio de contexto</span><span class="sxs-lookup"><span data-stu-id="bf46a-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="bf46a-110">Describe la correlación de intercambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="bf46a-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="bf46a-111">Dúplex duradero</span><span class="sxs-lookup"><span data-stu-id="bf46a-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="bf46a-112">Describe la correlación dúplex duradera.</span><span class="sxs-lookup"><span data-stu-id="bf46a-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="bf46a-113">En función del contenido</span><span class="sxs-lookup"><span data-stu-id="bf46a-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="bf46a-114">Describe una correlación basada en contenido.</span><span class="sxs-lookup"><span data-stu-id="bf46a-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="bf46a-115">Solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="bf46a-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="bf46a-116">Describe una correlación entre solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf46a-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="bf46a-117">Solución de problemas de correlación</span><span class="sxs-lookup"><span data-stu-id="bf46a-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="bf46a-118">Proporciona métodos para solucionar problemas de la correlación.</span><span class="sxs-lookup"><span data-stu-id="bf46a-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf46a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf46a-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="bf46a-120">Correlación basada en contenido</span><span class="sxs-lookup"><span data-stu-id="bf46a-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="bf46a-121">Calculadora correlacionada</span><span class="sxs-lookup"><span data-stu-id="bf46a-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
