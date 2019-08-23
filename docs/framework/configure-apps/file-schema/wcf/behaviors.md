---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 8fcb5ac0c552d1ac2e849c95a5c0757d0c142f3d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926394"
---
# <a name="behaviors"></a><span data-ttu-id="db81d-101">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="db81d-101">\<behaviors></span></span>
<span data-ttu-id="db81d-102">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="db81d-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="db81d-103">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="db81d-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="db81d-104">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="db81d-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="db81d-105">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="db81d-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="db81d-106">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="db81d-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="db81d-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="db81d-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db81d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db81d-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db81d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db81d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="db81d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="db81d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db81d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="db81d-111">Attributes</span></span>  
 <span data-ttu-id="db81d-112">None</span><span class="sxs-lookup"><span data-stu-id="db81d-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="db81d-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db81d-113">Child Elements</span></span>  
  
|<span data-ttu-id="db81d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="db81d-114">Element</span></span>|<span data-ttu-id="db81d-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="db81d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db81d-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="db81d-116">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="db81d-117">Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.</span><span class="sxs-lookup"><span data-stu-id="db81d-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="db81d-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="db81d-118">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="db81d-119">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="db81d-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db81d-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db81d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="db81d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="db81d-121">Element</span></span>|<span data-ttu-id="db81d-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="db81d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db81d-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="db81d-123">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="db81d-124">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="db81d-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db81d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db81d-125">Remarks</span></span>  
 <span data-ttu-id="db81d-126">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="db81d-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="db81d-127">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="db81d-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="db81d-128">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="db81d-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db81d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="db81d-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="db81d-130">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="db81d-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="db81d-131">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="db81d-131">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="db81d-132">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="db81d-132">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="db81d-133">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="db81d-133">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="db81d-134">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="db81d-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
