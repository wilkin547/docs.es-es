---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139692"
---
# \<behaviors>
<span data-ttu-id="751bb-101">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="751bb-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="751bb-102">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="751bb-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="751bb-103">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="751bb-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="751bb-104">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="751bb-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="751bb-105">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="751bb-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="751bb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="751bb-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="751bb-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="751bb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="751bb-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="751bb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="751bb-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="751bb-109">Attributes</span></span>  
 <span data-ttu-id="751bb-110">None</span><span class="sxs-lookup"><span data-stu-id="751bb-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="751bb-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="751bb-111">Child Elements</span></span>  
  
|<span data-ttu-id="751bb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="751bb-112">Element</span></span>|<span data-ttu-id="751bb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="751bb-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="751bb-114">Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.</span><span class="sxs-lookup"><span data-stu-id="751bb-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="751bb-115">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="751bb-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="751bb-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="751bb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="751bb-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="751bb-117">Element</span></span>|<span data-ttu-id="751bb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="751bb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="751bb-119">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="751bb-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="751bb-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="751bb-120">Remarks</span></span>  
 <span data-ttu-id="751bb-121">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="751bb-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="751bb-122">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="751bb-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="751bb-123">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="751bb-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751bb-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="751bb-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="751bb-125">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="751bb-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="751bb-126">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="751bb-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="751bb-127">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="751bb-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="751bb-128">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="751bb-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="751bb-129">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="751bb-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
