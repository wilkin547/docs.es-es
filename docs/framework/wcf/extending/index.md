---
title: Extensión de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 037182a3cb105f544e15a05f955c142ba57f62f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795537"
---
# <a name="extending-wcf"></a><span data-ttu-id="896cd-102">Extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="896cd-102">Extending WCF</span></span>
<span data-ttu-id="896cd-103">Windows Communication Foundation (WCF) permite modificar y extender los componentes en tiempo de ejecución para controlar y ampliar con precisión las aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="896cd-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="896cd-104">Los temas de esta sección hacen profundizan en la arquitectura de la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="896cd-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="896cd-105">Para obtener más información sobre la programación básica, vea [programación básica de WCF](../basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="896cd-105">For more information about basic programming, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="896cd-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="896cd-106">In This Section</span></span>  
 [<span data-ttu-id="896cd-107">Extensión de ServiceHost y la capa de modelos de servicios</span><span class="sxs-lookup"><span data-stu-id="896cd-107">Extending ServiceHost and the Service Model Layer</span></span>](extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="896cd-108">El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="896cd-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="896cd-109">Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="896cd-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="896cd-110">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="896cd-110">Extending Bindings</span></span>](extending-bindings.md)  
 <span data-ttu-id="896cd-111">Los enlaces son los objetos que describen los datos de comunicación exigidos para conectar a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="896cd-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="896cd-112">Las extensiones de enlace o enlaces personalizados implementan la funcionalidad de la comunicación personalizada exigida para admitir las características de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="896cd-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="896cd-113">Extensión de la capa de canales</span><span class="sxs-lookup"><span data-stu-id="896cd-113">Extending the Channel Layer</span></span>](extending-the-channel-layer.md)  
 <span data-ttu-id="896cd-114">El nivel del canal se encuentra bajo el nivel de modelo de servicio y es responsable para el intercambio de mensajes entre los clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="896cd-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="896cd-115">Las extensiones de canal pueden implementar la nueva funcionalidad de protocolo, como la seguridad.</span><span class="sxs-lookup"><span data-stu-id="896cd-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="896cd-116">Las extensiones del canal también transportan la funcionalidad, como implementar un nuevo transporte de red para llevar los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="896cd-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="896cd-117">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="896cd-117">Extending Security</span></span>](extending-security.md)  
 <span data-ttu-id="896cd-118">La seguridad en WCF se compone de la seguridad de la transferencia (integridad, confidencialidad y autenticación), control de acceso (autorización) y auditoría.</span><span class="sxs-lookup"><span data-stu-id="896cd-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="896cd-119">WCF usa las clases que `IdentityModel` se encuentran en el espacio de nombres para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="896cd-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="896cd-120">Entender la arquitectura de seguridad le permite crear tipos de notificación personalizados para alojar los sistemas de control de acceso personalizados.</span><span class="sxs-lookup"><span data-stu-id="896cd-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="896cd-121">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="896cd-121">Extending the Metadata System</span></span>](extending-the-metadata-system.md)  
 <span data-ttu-id="896cd-122">El sistema de metadatos de WCF es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="896cd-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="896cd-123">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="896cd-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="896cd-124">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="896cd-124">Extending Encoders and Serializers</span></span>](extending-encoders-and-serializers.md)  
 <span data-ttu-id="896cd-125">Los codificadores y serializadores traducen los datos de un formulario a otro.</span><span class="sxs-lookup"><span data-stu-id="896cd-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="896cd-126">Los temas de esta sección exponen cómo extender las clases proporcionadas para cumplir los requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="896cd-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="896cd-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="896cd-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="896cd-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="896cd-128">Related Sections</span></span>  
 [<span data-ttu-id="896cd-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="896cd-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="896cd-130">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="896cd-130">WCF Feature Details</span></span>](../feature-details/index.md)  
  
 [<span data-ttu-id="896cd-131">Instrucciones y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="896cd-131">Guidelines and Best Practices</span></span>](../guidelines-and-best-practices.md)
