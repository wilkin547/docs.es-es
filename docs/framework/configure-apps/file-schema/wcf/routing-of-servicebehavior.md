---
title: <routing> de <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 73a610056f94efe144705968eaf97c8314c1ae0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934196"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="84911-102">\<> de enrutamiento \<de ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="84911-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="84911-103">Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="84911-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="84911-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="84911-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="84911-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="84911-105">\<behaviors></span></span>  
<span data-ttu-id="84911-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="84911-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="84911-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="84911-107">\<behavior></span></span>  
<span data-ttu-id="84911-108">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="84911-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84911-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84911-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84911-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="84911-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84911-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="84911-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84911-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="84911-112">Attributes</span></span>  
  
|<span data-ttu-id="84911-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="84911-113">Attribute</span></span>|<span data-ttu-id="84911-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="84911-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84911-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="84911-115">filterTable</span></span>|<span data-ttu-id="84911-116">Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="84911-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="84911-117">Este valor debe coincidir `name` con el atributo de un [ \<elemento > de filterTable](filtertable.md) en la [ \<sección filterTables >](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="84911-117">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="84911-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="84911-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="84911-119">Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado.</span><span class="sxs-lookup"><span data-stu-id="84911-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="84911-120">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="84911-120">The default is `true`.</span></span>|  
|<span data-ttu-id="84911-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="84911-121">soapProcessingEnabled</span></span>|<span data-ttu-id="84911-122">Valor booleano que especifica si se debe producir el procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="84911-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84911-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="84911-123">Child Elements</span></span>  
 <span data-ttu-id="84911-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="84911-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84911-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="84911-125">Parent Elements</span></span>  
  
|<span data-ttu-id="84911-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="84911-126">Element</span></span>|<span data-ttu-id="84911-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="84911-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84911-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="84911-128">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="84911-129">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="84911-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84911-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84911-130">Remarks</span></span>  
 <span data-ttu-id="84911-131">Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio.</span><span class="sxs-lookup"><span data-stu-id="84911-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="84911-132">Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.</span><span class="sxs-lookup"><span data-stu-id="84911-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="84911-133">Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación.</span><span class="sxs-lookup"><span data-stu-id="84911-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="84911-134">En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio del enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron.</span><span class="sxs-lookup"><span data-stu-id="84911-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="84911-135">Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="84911-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
