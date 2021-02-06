---
description: Más información acerca de cómo extender WCF
title: Extensión de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: e243e03a72e6530716959499c311bfe37a39b054
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644156"
---
# <a name="extending-wcf"></a><span data-ttu-id="4c02b-103">Extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="4c02b-103">Extending WCF</span></span>

<span data-ttu-id="4c02b-104">Windows Communication Foundation (WCF) permite modificar y extender los componentes en tiempo de ejecución para controlar y ampliar con precisión las aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="4c02b-104">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="4c02b-105">Los temas de esta sección hacen profundizan en la arquitectura de la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4c02b-105">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="4c02b-106">Para obtener más información sobre la programación básica, vea [programación básica de WCF](../basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="4c02b-106">For more information about basic programming, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c02b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4c02b-107">In This Section</span></span>  

 [<span data-ttu-id="4c02b-108">Extensión de ServiceHost y la capa de modelos de servicios</span><span class="sxs-lookup"><span data-stu-id="4c02b-108">Extending ServiceHost and the Service Model Layer</span></span>](extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="4c02b-109">El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="4c02b-109">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="4c02b-110">Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4c02b-110">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="4c02b-111">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4c02b-111">Extending Bindings</span></span>](extending-bindings.md)  
 <span data-ttu-id="4c02b-112">Los enlaces son los objetos que describen los datos de comunicación exigidos para conectar a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4c02b-112">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="4c02b-113">Las extensiones de enlace o enlaces personalizados implementan la funcionalidad de la comunicación personalizada exigida para admitir las características de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c02b-113">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="4c02b-114">Extensión de la capa de canales</span><span class="sxs-lookup"><span data-stu-id="4c02b-114">Extending the Channel Layer</span></span>](extending-the-channel-layer.md)  
 <span data-ttu-id="4c02b-115">El nivel del canal se encuentra bajo el nivel de modelo de servicio y es responsable para el intercambio de mensajes entre los clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="4c02b-115">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="4c02b-116">Las extensiones de canal pueden implementar la nueva funcionalidad de protocolo, como la seguridad.</span><span class="sxs-lookup"><span data-stu-id="4c02b-116">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="4c02b-117">Las extensiones del canal también transportan la funcionalidad, como implementar un nuevo transporte de red para llevar los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="4c02b-117">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="4c02b-118">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="4c02b-118">Extending Security</span></span>](extending-security.md)  
 <span data-ttu-id="4c02b-119">La seguridad en WCF se compone de la seguridad de la transferencia (integridad, confidencialidad y autenticación), control de acceso (autorización) y auditoría.</span><span class="sxs-lookup"><span data-stu-id="4c02b-119">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="4c02b-120">WCF usa las clases que se encuentran en el `IdentityModel` espacio de nombres para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="4c02b-120">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="4c02b-121">Entender la arquitectura de seguridad le permite crear tipos de notificación personalizados para alojar los sistemas de control de acceso personalizados.</span><span class="sxs-lookup"><span data-stu-id="4c02b-121">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="4c02b-122">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="4c02b-122">Extending the Metadata System</span></span>](extending-the-metadata-system.md)  
 <span data-ttu-id="4c02b-123">El sistema de metadatos de WCF es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="4c02b-123">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="4c02b-124">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="4c02b-124">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="4c02b-125">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="4c02b-125">Extending Encoders and Serializers</span></span>](extending-encoders-and-serializers.md)  
 <span data-ttu-id="4c02b-126">Los codificadores y serializadores traducen los datos de un formulario a otro.</span><span class="sxs-lookup"><span data-stu-id="4c02b-126">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="4c02b-127">Los temas de esta sección exponen cómo extender las clases proporcionadas para cumplir los requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="4c02b-127">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c02b-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="4c02b-128">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="4c02b-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c02b-129">Related Sections</span></span>  

 [<span data-ttu-id="4c02b-130">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="4c02b-130">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="4c02b-131">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="4c02b-131">WCF Feature Details</span></span>](../feature-details/index.md)  
  
 [<span data-ttu-id="4c02b-132">Instrucciones y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="4c02b-132">Guidelines and Best Practices</span></span>](../guidelines-and-best-practices.md)
