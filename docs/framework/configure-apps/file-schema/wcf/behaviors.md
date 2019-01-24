---
title: '&lt;Comportamientos&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a6786efb289ee66da3f0635e1a86e23f9b7302d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528438"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="96904-102">&lt;Comportamientos&gt;</span><span class="sxs-lookup"><span data-stu-id="96904-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="96904-103">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="96904-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="96904-104">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="96904-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="96904-105">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="96904-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="96904-106">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="96904-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="96904-107">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="96904-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="96904-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="96904-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96904-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96904-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96904-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="96904-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96904-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="96904-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96904-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="96904-112">Attributes</span></span>  
 <span data-ttu-id="96904-113">Ninguna</span><span class="sxs-lookup"><span data-stu-id="96904-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96904-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="96904-114">Child Elements</span></span>  
  
|<span data-ttu-id="96904-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="96904-115">Element</span></span>|<span data-ttu-id="96904-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="96904-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96904-117">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="96904-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="96904-118">Esta sección de configuración representa todos los comportamientos definidos para un punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="96904-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="96904-119">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="96904-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="96904-120">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="96904-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96904-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="96904-121">Parent Elements</span></span>  
  
|<span data-ttu-id="96904-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="96904-122">Element</span></span>|<span data-ttu-id="96904-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="96904-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96904-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="96904-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="96904-125">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="96904-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96904-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96904-126">Remarks</span></span>  
 <span data-ttu-id="96904-127">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="96904-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="96904-128">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="96904-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="96904-129">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="96904-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96904-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="96904-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="96904-131">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="96904-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="96904-132">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="96904-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="96904-133">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="96904-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="96904-134">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="96904-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="96904-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="96904-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
