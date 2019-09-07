---
title: <routing> de <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397732"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="07f74-102">\<> de enrutamiento \<de ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="07f74-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="07f74-103">Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="07f74-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="07f74-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07f74-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07f74-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="07f74-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="07f74-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="07f74-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="07f74-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="07f74-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="07f74-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="07f74-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="07f74-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="07f74-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f74-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07f74-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07f74-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="07f74-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07f74-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="07f74-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07f74-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="07f74-113">Attributes</span></span>  
  
|<span data-ttu-id="07f74-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="07f74-114">Attribute</span></span>|<span data-ttu-id="07f74-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="07f74-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07f74-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="07f74-116">filterTable</span></span>|<span data-ttu-id="07f74-117">Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="07f74-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="07f74-118">Este valor debe coincidir `name` con el atributo de un [ \<elemento > de filterTable](filtertable.md) en la [ \<sección filterTables >](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="07f74-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="07f74-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="07f74-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="07f74-120">Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado.</span><span class="sxs-lookup"><span data-stu-id="07f74-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="07f74-121">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="07f74-121">The default is `true`.</span></span>|  
|<span data-ttu-id="07f74-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="07f74-122">soapProcessingEnabled</span></span>|<span data-ttu-id="07f74-123">Valor booleano que especifica si se debe producir el procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="07f74-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07f74-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07f74-124">Child Elements</span></span>  
 <span data-ttu-id="07f74-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="07f74-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07f74-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07f74-126">Parent Elements</span></span>  
  
|<span data-ttu-id="07f74-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="07f74-127">Element</span></span>|<span data-ttu-id="07f74-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="07f74-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07f74-129">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="07f74-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="07f74-130">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="07f74-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07f74-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07f74-131">Remarks</span></span>  
 <span data-ttu-id="07f74-132">Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio.</span><span class="sxs-lookup"><span data-stu-id="07f74-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="07f74-133">Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.</span><span class="sxs-lookup"><span data-stu-id="07f74-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="07f74-134">Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación.</span><span class="sxs-lookup"><span data-stu-id="07f74-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="07f74-135">En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio del enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron.</span><span class="sxs-lookup"><span data-stu-id="07f74-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="07f74-136">Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="07f74-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
