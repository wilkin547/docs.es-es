---
title: '&lt;comportamientos&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b38b27a7b196026e2ff873c7748ed46b96ba9b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="46713-102">&lt;comportamientos&gt;</span><span class="sxs-lookup"><span data-stu-id="46713-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="46713-103">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="46713-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="46713-104">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="46713-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="46713-105">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="46713-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="46713-106">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="46713-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="46713-107">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="46713-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="46713-108">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="46713-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46713-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46713-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46713-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46713-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46713-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46713-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46713-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="46713-112">Attributes</span></span>  
 <span data-ttu-id="46713-113">Ninguna</span><span class="sxs-lookup"><span data-stu-id="46713-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46713-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="46713-114">Child Elements</span></span>  
  
|<span data-ttu-id="46713-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="46713-115">Element</span></span>|<span data-ttu-id="46713-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="46713-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46713-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="46713-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="46713-118">Esta sección de configuración representa todos los comportamientos definidos para un punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="46713-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="46713-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="46713-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="46713-120">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="46713-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46713-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="46713-121">Parent Elements</span></span>  
  
|<span data-ttu-id="46713-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="46713-122">Element</span></span>|<span data-ttu-id="46713-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="46713-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46713-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="46713-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="46713-125">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="46713-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46713-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46713-126">Remarks</span></span>  
 <span data-ttu-id="46713-127">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="46713-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="46713-128">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="46713-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="46713-129">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="46713-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46713-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="46713-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="46713-131">Configurar y extender el tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="46713-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="46713-132">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="46713-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="46713-133">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="46713-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="46713-134">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="46713-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="46713-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="46713-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
