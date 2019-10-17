---
title: puntos de conexión en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: f11a8198d38a01fe27a84a3e613e1ff066c25b9d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319909"
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="35b73-102">puntos de conexión en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="35b73-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="35b73-103">Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="35b73-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="35b73-104">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="35b73-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="35b73-105">Para obtener información general sobre cómo crear un punto de conexión, consulte [información general](endpoint-creation-overview.md)sobre la creación de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="35b73-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="35b73-106">Cada punto de conexión contiene:</span><span class="sxs-lookup"><span data-stu-id="35b73-106">Each endpoint contains:</span></span>  
  
- <span data-ttu-id="35b73-107">Una dirección que indica dónde buscar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="35b73-107">An address that indicates where to find the endpoint.</span></span>  
  
- <span data-ttu-id="35b73-108">Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="35b73-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="35b73-109">Un contrato que identifica los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="35b73-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="35b73-110">Para obtener descripciones acerca de cómo especificar estas partes individuales de un punto de conexión, consulte:</span><span class="sxs-lookup"><span data-stu-id="35b73-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
- [<span data-ttu-id="35b73-111">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="35b73-111">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)  
  
- [<span data-ttu-id="35b73-112">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="35b73-112">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)  
  
- [<span data-ttu-id="35b73-113">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="35b73-113">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="35b73-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="35b73-114">In This Section</span></span>  
 [<span data-ttu-id="35b73-115">Información general sobre la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="35b73-115">Endpoint Creation Overview</span></span>](endpoint-creation-overview.md)  
 <span data-ttu-id="35b73-116">Describe la estructura de un extremo y detalla cómo definir un extremo en la configuración y el código, así como el uso de los extremos, enlaces y comportamientos predeterminados proporcionados por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35b73-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="35b73-117">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="35b73-117">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)  
 <span data-ttu-id="35b73-118">Describe cómo se produce la comunicación con un servicio WCF a través de los extremos.</span><span class="sxs-lookup"><span data-stu-id="35b73-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="35b73-119">Creación de un punto de conexión de servicio en configuración</span><span class="sxs-lookup"><span data-stu-id="35b73-119">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="35b73-120">Muestra cómo crear un punto de conexión de servicio en configuración.</span><span class="sxs-lookup"><span data-stu-id="35b73-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="35b73-121">Creación de un punto de conexión de servicio en código</span><span class="sxs-lookup"><span data-stu-id="35b73-121">How to: Create a Service Endpoint in Code</span></span>](./feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="35b73-122">Muestra cómo crear un extremo de servicio en código.</span><span class="sxs-lookup"><span data-stu-id="35b73-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="35b73-123">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="35b73-123">Publishing Metadata Endpoints</span></span>](publishing-metadata-endpoints.md)  
 <span data-ttu-id="35b73-124">Muestra cómo publicar los metadatos mediante la publicación de los extremos de metadatos en configuración y en código.</span><span class="sxs-lookup"><span data-stu-id="35b73-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35b73-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="35b73-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="35b73-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="35b73-126">Related Sections</span></span>  
 [<span data-ttu-id="35b73-127">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="35b73-127">Basic Programming Lifecycle</span></span>](basic-programming-lifecycle.md)
