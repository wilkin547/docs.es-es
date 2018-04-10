---
title: Extensión de WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c84f25dfd5d3066f9c5d0b62bc0b28bc98c283d
ms.sourcegitcommit: 08684dd61444c2f072b89b926370f750e456fca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2018
---
# <a name="extending-wcf"></a><span data-ttu-id="43e6b-102">Extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="43e6b-102">Extending WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] <span data-ttu-id="43e6b-103">permite modificar y extender los componentes de tiempo de ejecución para controlar con precisión y extender las aplicaciones basadas en servicios.</span><span class="sxs-lookup"><span data-stu-id="43e6b-103">allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="43e6b-104">Los temas de esta sección hacen profundizan en la arquitectura de la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="43e6b-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="43e6b-105">Para obtener más información acerca de la programación básica, consulte [programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="43e6b-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43e6b-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43e6b-106">In This Section</span></span>  
 [<span data-ttu-id="43e6b-107">Extensión de ServiceHost y la capa de modelos de servicios</span><span class="sxs-lookup"><span data-stu-id="43e6b-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="43e6b-108">El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="43e6b-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="43e6b-109">Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="43e6b-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="43e6b-110">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="43e6b-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="43e6b-111">Los enlaces son los objetos que describen los datos de comunicación exigidos para conectar a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="43e6b-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="43e6b-112">Las extensiones de enlace o enlaces personalizados implementan la funcionalidad de la comunicación personalizada exigida para admitir las características de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="43e6b-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="43e6b-113">Extensión de la capa de canales</span><span class="sxs-lookup"><span data-stu-id="43e6b-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="43e6b-114">El nivel del canal se encuentra bajo el nivel de modelo de servicio y es responsable para el intercambio de mensajes entre los clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="43e6b-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="43e6b-115">Las extensiones de canal pueden implementar la nueva funcionalidad de protocolo, como la seguridad.</span><span class="sxs-lookup"><span data-stu-id="43e6b-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="43e6b-116">Las extensiones del canal también transportan la funcionalidad, como implementar un nuevo transporte de red para llevar los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="43e6b-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="43e6b-117">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="43e6b-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="43e6b-118">La seguridad en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste en transferir seguridad (integridad, confidencialidad y autenticación), control de acceso (autorización) y auditoría.</span><span class="sxs-lookup"><span data-stu-id="43e6b-118">Security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="43e6b-119">`IdentityModel` utiliza las clases situadas en el espacio de nombres [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="43e6b-119">The classes found in the `IdentityModel` namespace are used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for access control.</span></span> <span data-ttu-id="43e6b-120">Entender la arquitectura de seguridad le permite crear tipos de notificación personalizados para alojar los sistemas de control de acceso personalizados.</span><span class="sxs-lookup"><span data-stu-id="43e6b-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="43e6b-121">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="43e6b-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="43e6b-122">El sistema de metadatos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es un grupo de clases e interfaces que representan los metadatos requeridos para implementar las aplicaciones basadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="43e6b-122">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="43e6b-123">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="43e6b-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="43e6b-124">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="43e6b-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="43e6b-125">Los codificadores y serializadores traducen los datos de un formulario a otro.</span><span class="sxs-lookup"><span data-stu-id="43e6b-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="43e6b-126">Los temas de esta sección exponen cómo extender las clases proporcionadas para cumplir los requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="43e6b-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="43e6b-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="43e6b-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="43e6b-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="43e6b-128">Related Sections</span></span>  
 [<span data-ttu-id="43e6b-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="43e6b-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="43e6b-130">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="43e6b-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="43e6b-131">Instrucciones y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="43e6b-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
