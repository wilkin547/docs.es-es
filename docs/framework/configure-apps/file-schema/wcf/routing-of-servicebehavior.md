---
title: '&lt;routing&gt; de &lt;serviceBehavior&gt;'
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 5fb7febe365f73acf09ba74b07215fe9cc659efb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="e9f9c-102">&lt;routing&gt; de &lt;serviceBehavior&gt;</span><span class="sxs-lookup"><span data-stu-id="e9f9c-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="e9f9c-103">Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="e9f9c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9f9c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9f9c-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="e9f9c-105">\<behaviors></span></span>  
<span data-ttu-id="e9f9c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e9f9c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e9f9c-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e9f9c-107">\<behavior></span></span>  
<span data-ttu-id="e9f9c-108">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="e9f9c-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f9c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9f9c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9f9c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e9f9c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9f9c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9f9c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e9f9c-112">Attributes</span></span>  
  
|<span data-ttu-id="e9f9c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e9f9c-113">Attribute</span></span>|<span data-ttu-id="e9f9c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9f9c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9f9c-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="e9f9c-115">filterTable</span></span>|<span data-ttu-id="e9f9c-116">Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="e9f9c-117">Este valor debe coincidir con el `name` atributo de un [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) elemento en el [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) sección.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="e9f9c-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="e9f9c-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="e9f9c-119">Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="e9f9c-120">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-120">The default is `true`.</span></span>|  
|<span data-ttu-id="e9f9c-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="e9f9c-121">soapProcessingEnabled</span></span>|<span data-ttu-id="e9f9c-122">Valor booleano que especifica si se debe producir el procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9f9c-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e9f9c-123">Child Elements</span></span>  
 <span data-ttu-id="e9f9c-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9f9c-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e9f9c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e9f9c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9f9c-126">Element</span></span>|<span data-ttu-id="e9f9c-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9f9c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9f9c-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e9f9c-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e9f9c-129">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9f9c-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9f9c-130">Remarks</span></span>  
 <span data-ttu-id="e9f9c-131">Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="e9f9c-132">Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="e9f9c-133">Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="e9f9c-134">En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio del enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="e9f9c-135">Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e9f9c-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  
