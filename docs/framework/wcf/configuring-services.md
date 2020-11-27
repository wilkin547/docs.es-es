---
title: Configuración de servicios WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: a5fe0cabb1a6be7f93bf5f4d753e9bb08a39cea3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253341"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="4d417-102">Configuración de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="4d417-102">Configuring WCF services</span></span>

<span data-ttu-id="4d417-103">Cuando haya diseñado e implementado su contrato de servicios, usted está listo para configurar su servicio.</span><span class="sxs-lookup"><span data-stu-id="4d417-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="4d417-104">En este momento define y personaliza cómo se expone su servicio a los clientes, además de especificar la dirección donde se puede encontrar, el transporte y codificación de mensajes que utiliza para enviar y recibir mensajes y el tipo de seguridad que requiere.</span><span class="sxs-lookup"><span data-stu-id="4d417-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="4d417-105">La configuración tal y como se utiliza aquí incluye todas las maneras, imperativamente en código o utilizando un archivo de configuración, en el que puede definir y personalizar los diferentes aspectos de un servicio, como especificar sus direcciones de extremo, los transportes utilizados y sus esquemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d417-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="4d417-106">En la práctica, escribir la configuración es una parte importante de la programación de aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="4d417-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d417-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d417-107">In This Section</span></span>  

 [<span data-ttu-id="4d417-108">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="4d417-108">Simplified Configuration</span></span>](simplified-configuration.md)  
 <span data-ttu-id="4d417-109">A partir de .NET Framework 4, WCF incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="4d417-109">Starting with .NET Framework 4, WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="4d417-110">Si no proporciona ninguna configuración de WCF para un servicio determinado, el tiempo de ejecución configura automáticamente el servicio con los extremos, enlaces y comportamientos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4d417-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="4d417-111">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d417-111">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
 <span data-ttu-id="4d417-112">Un servicio Windows Communication Foundation (WCF) se puede configurar mediante la tecnología de configuración de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d417-112">A Windows Communication Foundation (WCF) service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="4d417-113">Normalmente, los elementos XML se agregan al archivo Web.config para un sitio Internet Information Services (IIS) que hospeda un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="4d417-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="4d417-114">Los elementos le permiten cambiar los datos, como las direcciones de punto de conexión (las direcciones reales utilizadas para comunicarse con el servicio) en una base equipo por equipo.</span><span class="sxs-lookup"><span data-stu-id="4d417-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="4d417-115">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4d417-115">Bindings</span></span>](bindings.md)  
 <span data-ttu-id="4d417-116">Además, WCF incluye varias configuraciones comunes proporcionadas por el sistema en forma de enlaces que permiten seleccionar rápidamente las características más básicas sobre cómo se comunica un cliente y un servicio, como los transportes, la seguridad y las codificaciones de mensajes que se usan.</span><span class="sxs-lookup"><span data-stu-id="4d417-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="4d417-117">Extremos</span><span class="sxs-lookup"><span data-stu-id="4d417-117">Endpoints</span></span>](endpoints.md)  
 <span data-ttu-id="4d417-118">Todas las comunicaciones con un servicio WCF se producen a través de los *puntos de conexión* del servicio.</span><span class="sxs-lookup"><span data-stu-id="4d417-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="4d417-119">Los puntos de conexión contienen el contrato, la información de configuración que se especifica en los enlaces, y las direcciones que indican dónde encontrar el servicio o dónde obtener información sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="4d417-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="4d417-120">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="4d417-120">Securing Services</span></span>](securing-services.md)  
 <span data-ttu-id="4d417-121">Con WCF y los mecanismos de seguridad existentes, puede implementar la confidencialidad, la integridad, la autenticación y la autorización en cualquier servicio.</span><span class="sxs-lookup"><span data-stu-id="4d417-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="4d417-122">También puede revisar los éxitos de seguridad y errores.</span><span class="sxs-lookup"><span data-stu-id="4d417-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="4d417-123">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="4d417-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="4d417-124">Los requisitos para implementar un servicio interoperable con servicios y clientes en cualquier otra plataforma o sistema operativo se describen en la especificación WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="4d417-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4d417-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="4d417-125">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="4d417-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4d417-126">Related Sections</span></span>  

 [<span data-ttu-id="4d417-127">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="4d417-127">Basic Programming Lifecycle</span></span>](basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="4d417-128">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="4d417-128">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)  
  
 [<span data-ttu-id="4d417-129">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4d417-129">Hosting Services</span></span>](hosting-services.md)  
  
 [<span data-ttu-id="4d417-130">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="4d417-130">Building Clients</span></span>](building-clients.md)  
  
 [<span data-ttu-id="4d417-131">Introducción a la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="4d417-131">Introduction to Extensibility</span></span>](introduction-to-extensibility.md)  
  
 [<span data-ttu-id="4d417-132">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4d417-132">Administration and Diagnostics</span></span>](./diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d417-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d417-133">See also</span></span>

- [<span data-ttu-id="4d417-134">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="4d417-134">Basic WCF Programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="4d417-135">Información general conceptual</span><span class="sxs-lookup"><span data-stu-id="4d417-135">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="4d417-136">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="4d417-136">WCF Feature Details</span></span>](./feature-details/index.md)
