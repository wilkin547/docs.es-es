---
title: Configuración de servicios WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 81727adbf985986a71cc9f9e2d42a1de0cb1fd76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608545"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="754ce-102">Configuración de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="754ce-102">Configuring WCF services</span></span>

<span data-ttu-id="754ce-103">Cuando haya diseñado e implementado su contrato de servicios, usted está listo para configurar su servicio.</span><span class="sxs-lookup"><span data-stu-id="754ce-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="754ce-104">En este momento define y personaliza cómo se expone su servicio a los clientes, además de especificar la dirección donde se puede encontrar, el transporte y codificación de mensajes que utiliza para enviar y recibir mensajes y el tipo de seguridad que requiere.</span><span class="sxs-lookup"><span data-stu-id="754ce-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="754ce-105">La configuración tal y como se utiliza aquí incluye todas las maneras, imperativamente en código o utilizando un archivo de configuración, en el que puede definir y personalizar los diferentes aspectos de un servicio, como especificar sus direcciones de extremo, los transportes utilizados y sus esquemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="754ce-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="754ce-106">En la práctica, escribir la configuración es una gran parte de la programación de aplicaciones de WCF.</span><span class="sxs-lookup"><span data-stu-id="754ce-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="754ce-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="754ce-107">In This Section</span></span>  
 [<span data-ttu-id="754ce-108">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="754ce-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="754ce-109">A partir de [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="754ce-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="754ce-110">Si no proporciona ninguna configuración de WCF para un servicio determinado, el tiempo de ejecución configura automáticamente el servicio con los comportamientos, enlaces y puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="754ce-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="754ce-111">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="754ce-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="754ce-112">Un servicio de Windows Communication Foundation (WCF) es configurable utilizando el [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] tecnología de configuración.</span><span class="sxs-lookup"><span data-stu-id="754ce-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="754ce-113">Normalmente, los elementos XML se agregan al archivo Web.config para un sitio de Internet Information Services (IIS) que hospeda un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="754ce-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="754ce-114">Los elementos le permiten cambiar los datos, como las direcciones de punto de conexión (las direcciones reales utilizadas para comunicarse con el servicio) en una base equipo por equipo.</span><span class="sxs-lookup"><span data-stu-id="754ce-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="754ce-115">Enlaces</span><span class="sxs-lookup"><span data-stu-id="754ce-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="754ce-116">Además, WCF incluye varias configuraciones comunes proporcionadas por el sistema en forma de los enlaces que le permiten seleccionar rápidamente las características más básicas para la comunicación entre un cliente y servicio, como los transportes, seguridad y utilizan codificaciones de mensaje.</span><span class="sxs-lookup"><span data-stu-id="754ce-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="754ce-117">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="754ce-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="754ce-118">Se produce toda la comunicación con un servicio WCF a través de la *extremos* del servicio.</span><span class="sxs-lookup"><span data-stu-id="754ce-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="754ce-119">Los puntos de conexión contienen el contrato, la información de configuración que se especifica en los enlaces, y las direcciones que indican dónde encontrar el servicio o dónde obtener información sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="754ce-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="754ce-120">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="754ce-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="754ce-121">Con WCF y existente mecanismos de seguridad, puede implementar confidencialidad, integridad, autenticación y autorización en cualquier servicio.</span><span class="sxs-lookup"><span data-stu-id="754ce-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="754ce-122">También puede revisar los éxitos de seguridad y errores.</span><span class="sxs-lookup"><span data-stu-id="754ce-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="754ce-123">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="754ce-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="754ce-124">Los requisitos para implementar un servicio interoperable con servicios y clientes en cualquier otra plataforma o sistema operativo se describen en la especificación WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="754ce-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="754ce-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="754ce-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="754ce-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="754ce-126">Related Sections</span></span>  
 [<span data-ttu-id="754ce-127">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="754ce-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="754ce-128">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="754ce-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="754ce-129">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="754ce-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="754ce-130">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="754ce-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="754ce-131">Introducción a la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="754ce-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="754ce-132">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="754ce-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="754ce-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="754ce-133">See also</span></span>

- [<span data-ttu-id="754ce-134">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="754ce-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="754ce-135">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="754ce-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="754ce-136">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="754ce-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
