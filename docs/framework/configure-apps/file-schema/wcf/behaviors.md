---
title: '&lt;Comportamientos&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: ca9cf5daa6590c14d4b5fd15c502d67af1f93b52
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745973"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="28ddb-102">&lt;Comportamientos&gt;</span><span class="sxs-lookup"><span data-stu-id="28ddb-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="28ddb-103">Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="28ddb-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="28ddb-104">Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios.</span><span class="sxs-lookup"><span data-stu-id="28ddb-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="28ddb-105">Su atributo de `name` único identifica cada elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="28ddb-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="28ddb-106">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="28ddb-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="28ddb-107">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="28ddb-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="28ddb-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="28ddb-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ddb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28ddb-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28ddb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28ddb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="28ddb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28ddb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28ddb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="28ddb-112">Attributes</span></span>  
 <span data-ttu-id="28ddb-113">Ninguna</span><span class="sxs-lookup"><span data-stu-id="28ddb-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28ddb-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28ddb-114">Child Elements</span></span>  
  
|<span data-ttu-id="28ddb-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="28ddb-115">Element</span></span>|<span data-ttu-id="28ddb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="28ddb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ddb-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="28ddb-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="28ddb-118">Esta sección de configuración representa todos los comportamientos definidos para un punto de conexión concreto.</span><span class="sxs-lookup"><span data-stu-id="28ddb-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="28ddb-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="28ddb-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="28ddb-120">Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="28ddb-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28ddb-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28ddb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="28ddb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="28ddb-122">Element</span></span>|<span data-ttu-id="28ddb-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="28ddb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ddb-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28ddb-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="28ddb-125">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="28ddb-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ddb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28ddb-126">Remarks</span></span>  
 <span data-ttu-id="28ddb-127">Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección.</span><span class="sxs-lookup"><span data-stu-id="28ddb-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="28ddb-128">Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="28ddb-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="28ddb-129">También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.</span><span class="sxs-lookup"><span data-stu-id="28ddb-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ddb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ddb-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="28ddb-131">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="28ddb-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="28ddb-132">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="28ddb-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="28ddb-133">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="28ddb-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="28ddb-134">Especificación del comportamiento en tiempo de ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="28ddb-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="28ddb-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="28ddb-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
