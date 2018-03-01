---
title: "Configuración de servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 857ec77e54d6a55bde1a94fd9fd5758ef7a24309
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-services"></a><span data-ttu-id="bebf5-102">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="bebf5-102">Configuring Services</span></span>
<span data-ttu-id="bebf5-103">Cuando haya diseñado e implementado su contrato de servicios, usted está listo para configurar su servicio.</span><span class="sxs-lookup"><span data-stu-id="bebf5-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="bebf5-104">En este momento define y personaliza cómo se expone su servicio a los clientes, además de especificar la dirección donde se puede encontrar, el transporte y codificación de mensajes que utiliza para enviar y recibir mensajes y el tipo de seguridad que requiere.</span><span class="sxs-lookup"><span data-stu-id="bebf5-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="bebf5-105">La configuración tal y como se utiliza aquí incluye todas las maneras, imperativamente en código o utilizando un archivo de configuración, en el que puede definir y personalizar los diferentes aspectos de un servicio, como especificar sus direcciones de extremo, los transportes utilizados y sus esquemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bebf5-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="bebf5-106">En la práctica, escribir la configuración es una parte principal de la programación de aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bebf5-106">In practice, writing configuration is a major part of programming [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bebf5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bebf5-107">In This Section</span></span>  
 [<span data-ttu-id="bebf5-108">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="bebf5-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="bebf5-109">A partir de [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bebf5-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] comes with a new default configuration model that simplifies [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration requirements.</span></span> <span data-ttu-id="bebf5-110">Si no se proporciona ninguna configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para un servicio concreto, el tiempo de ejecución lo configurará automáticamente con extremos, enlaces y comportamientos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bebf5-110">If you do not provide any [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="bebf5-111">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bebf5-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="bebf5-112">Se puede configurar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] mediante la tecnología de configuración [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bebf5-112">A [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="bebf5-113">Por lo general, los elementos XML se agregan al archivo Web.config para un sitio de Internet Information Services (IIS) que hospeda un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bebf5-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="bebf5-114">Los elementos le permiten cambiar los datos, como las direcciones de punto de conexión (las direcciones reales utilizadas para comunicarse con el servicio) en una base equipo por equipo.</span><span class="sxs-lookup"><span data-stu-id="bebf5-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="bebf5-115">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bebf5-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="bebf5-116">Además, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye varias configuraciones comunes proporcionadas por el sistema en forma de enlaces que le permiten seleccionar rápidamente las características más básicas sobre cómo se comunican un cliente y el servicio, como los transportes, seguridad y codificación de mensajes utilizadas.</span><span class="sxs-lookup"><span data-stu-id="bebf5-116">In addition, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="bebf5-117">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="bebf5-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="bebf5-118">Toda la comunicación con un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio se produce a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="bebf5-118">All communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="bebf5-119">Los puntos de conexión contienen el contrato, la información de configuración que se especifica en los enlaces, y las direcciones que indican dónde encontrar el servicio o dónde obtener información sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="bebf5-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="bebf5-120">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="bebf5-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="bebf5-121">Utilizando [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y mecanismos de seguridad existentes, puede implementar confidencialidad, integridad, autenticación y autorización en cualquier servicio.</span><span class="sxs-lookup"><span data-stu-id="bebf5-121">Using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="bebf5-122">También puede revisar los éxitos de seguridad y errores.</span><span class="sxs-lookup"><span data-stu-id="bebf5-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="bebf5-123">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="bebf5-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="bebf5-124">Los requisitos para implementar un servicio interoperable con servicios y clientes en cualquier otra plataforma o sistema operativo se describen en la especificación WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="bebf5-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bebf5-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="bebf5-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="bebf5-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bebf5-126">Related Sections</span></span>  
 [<span data-ttu-id="bebf5-127">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="bebf5-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="bebf5-128">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="bebf5-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="bebf5-129">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bebf5-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="bebf5-130">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="bebf5-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="bebf5-131">Introducción a la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="bebf5-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="bebf5-132">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="bebf5-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="bebf5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bebf5-133">See Also</span></span>  
 [<span data-ttu-id="bebf5-134">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="bebf5-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="bebf5-135">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="bebf5-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="bebf5-136">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="bebf5-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
