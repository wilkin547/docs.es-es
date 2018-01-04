---
title: "puntos de conexión en Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0725c4f4275853cce958072a57d7f6ca4059e8cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="517ce-102">puntos de conexión en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="517ce-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="517ce-103">Toda la comunicación con un [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] servicio se produce a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="517ce-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="517ce-104">Los extremos proporcionan a los clientes acceso a la funcionalidad que un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ofrece.</span><span class="sxs-lookup"><span data-stu-id="517ce-104">Endpoints provide clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span>  
  
 <span data-ttu-id="517ce-105">Para obtener información general sobre cómo crear un punto de conexión, vea [información general de creación de punto de conexión](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="517ce-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="517ce-106">Cada punto de conexión contiene:</span><span class="sxs-lookup"><span data-stu-id="517ce-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="517ce-107">Una dirección que indica dónde buscar el extremo.</span><span class="sxs-lookup"><span data-stu-id="517ce-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="517ce-108">Un enlace que especifica cómo un se puede comunicar un cliente con el extremo.</span><span class="sxs-lookup"><span data-stu-id="517ce-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="517ce-109">Un contrato que identifica los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="517ce-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="517ce-110">Para obtener descripciones acerca de cómo especificar estas partes individuales de un punto de conexión, consulte:</span><span class="sxs-lookup"><span data-stu-id="517ce-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="517ce-111">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="517ce-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="517ce-112">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="517ce-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="517ce-113">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="517ce-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="517ce-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="517ce-114">In This Section</span></span>  
 [<span data-ttu-id="517ce-115">Información general sobre la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="517ce-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="517ce-116">Describe la estructura de un punto de conexión y detalla cómo definir un punto de conexión en la configuración y el código, así como el uso de los puntos de conexión, enlaces y comportamientos predeterminados proporcionados por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="517ce-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="517ce-117">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="517ce-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="517ce-118">Describe cómo se produce la comunicación con un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a través de los extremos.</span><span class="sxs-lookup"><span data-stu-id="517ce-118">Describes how communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="517ce-119">Creación de un punto de conexión de servicio en configuración</span><span class="sxs-lookup"><span data-stu-id="517ce-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="517ce-120">Muestra cómo crear un punto de conexión de servicio en configuración.</span><span class="sxs-lookup"><span data-stu-id="517ce-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="517ce-121">Creación de un punto de conexión de servicio en código</span><span class="sxs-lookup"><span data-stu-id="517ce-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="517ce-122">Muestra cómo crear un punto de conexión de servicio en código.</span><span class="sxs-lookup"><span data-stu-id="517ce-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="517ce-123">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="517ce-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="517ce-124">Muestra cómo publicar los metadatos mediante la publicación de los puntos de conexión de metadatos en configuración y en código.</span><span class="sxs-lookup"><span data-stu-id="517ce-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="517ce-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="517ce-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="517ce-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="517ce-126">Related Sections</span></span>  
 [<span data-ttu-id="517ce-127">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="517ce-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
