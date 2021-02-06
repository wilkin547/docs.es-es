---
description: 'Más información acerca de: <behaviors>'
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 3cb8edea76f6e7af3c3b387e5b04b89e58a28305
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639515"
---
# \<behaviors>

<span data-ttu-id="76323-102">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="76323-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="76323-103">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="76323-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="76323-104">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="76323-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="76323-105">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="76323-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="76323-106">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="76323-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="76323-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76323-107">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76323-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76323-108">Attributes and Elements</span></span>  

 <span data-ttu-id="76323-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76323-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76323-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="76323-110">Attributes</span></span>  

 <span data-ttu-id="76323-111">None</span><span class="sxs-lookup"><span data-stu-id="76323-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76323-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76323-112">Child Elements</span></span>  
  
|<span data-ttu-id="76323-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="76323-113">Element</span></span>|<span data-ttu-id="76323-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="76323-114">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="76323-115">Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.</span><span class="sxs-lookup"><span data-stu-id="76323-115">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="76323-116">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="76323-116">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76323-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76323-117">Parent Elements</span></span>  
  
|<span data-ttu-id="76323-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="76323-118">Element</span></span>|<span data-ttu-id="76323-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="76323-119">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="76323-120">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="76323-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76323-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76323-121">Remarks</span></span>  

 <span data-ttu-id="76323-122">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="76323-122">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="76323-123">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="76323-123">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="76323-124">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="76323-124">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76323-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="76323-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="76323-126">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="76323-126">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="76323-127">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="76323-127">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="76323-128">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="76323-128">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="76323-129">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="76323-129">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="76323-130">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="76323-130">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
