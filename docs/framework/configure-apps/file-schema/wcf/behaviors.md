---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139692"
---
# <a name="behaviors"></a><span data-ttu-id="d6d50-101">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d6d50-101">\<behaviors></span></span>
<span data-ttu-id="d6d50-102">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="d6d50-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="d6d50-103">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="d6d50-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="d6d50-104">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d6d50-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="d6d50-105">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="d6d50-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d6d50-106">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6d50-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="d6d50-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6d50-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d6d50-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d6d50-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d6d50-109">&nbsp;&nbsp;&nbsp;&nbsp;**comportamientos\<**</span><span class="sxs-lookup"><span data-stu-id="d6d50-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d50-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6d50-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6d50-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6d50-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6d50-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6d50-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6d50-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6d50-113">Attributes</span></span>  
 <span data-ttu-id="d6d50-114">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d6d50-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6d50-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6d50-115">Child Elements</span></span>  
  
|<span data-ttu-id="d6d50-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6d50-116">Element</span></span>|<span data-ttu-id="d6d50-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6d50-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6d50-118">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d6d50-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="d6d50-119">Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.</span><span class="sxs-lookup"><span data-stu-id="d6d50-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="d6d50-120">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d6d50-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="d6d50-121">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="d6d50-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6d50-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6d50-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d6d50-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6d50-123">Element</span></span>|<span data-ttu-id="d6d50-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6d50-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6d50-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d6d50-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="d6d50-126">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d6d50-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6d50-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6d50-127">Remarks</span></span>  
 <span data-ttu-id="d6d50-128">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="d6d50-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="d6d50-129">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="d6d50-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="d6d50-130">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="d6d50-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d50-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6d50-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="d6d50-132">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="d6d50-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="d6d50-133">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="d6d50-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="d6d50-134">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="d6d50-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="d6d50-135">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="d6d50-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="d6d50-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d6d50-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
