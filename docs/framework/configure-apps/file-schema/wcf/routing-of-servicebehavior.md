---
description: 'Más información sobre: <routing> de <serviceBehavior>'
title: <routing> de <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 1d8a056d708b3c42aeccf3e46a0703b3fc78a17d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786894"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="a5149-103">\<routing> de \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="a5149-103">\<routing> of \<serviceBehavior></span></span>

<span data-ttu-id="a5149-104">Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a5149-104">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="a5149-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5149-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5149-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5149-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a5149-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5149-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5149-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5149-108">Attributes</span></span>  
  
|<span data-ttu-id="a5149-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a5149-109">Attribute</span></span>|<span data-ttu-id="a5149-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5149-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5149-111">filterTable</span><span class="sxs-lookup"><span data-stu-id="a5149-111">filterTable</span></span>|<span data-ttu-id="a5149-112">Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a5149-112">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="a5149-113">Este valor debe coincidir con el `name` atributo de un [\<filterTable>](filtertable.md) elemento de la [\<filterTables>](filtertables.md) sección.</span><span class="sxs-lookup"><span data-stu-id="a5149-113">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="a5149-114">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="a5149-114">routeOnHeaderOnly</span></span>|<span data-ttu-id="a5149-115">Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado.</span><span class="sxs-lookup"><span data-stu-id="a5149-115">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="a5149-116">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="a5149-116">The default is `true`.</span></span>|  
|<span data-ttu-id="a5149-117">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="a5149-117">soapProcessingEnabled</span></span>|<span data-ttu-id="a5149-118">Valor booleano que especifica si se debe producir el procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="a5149-118">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5149-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a5149-119">Child Elements</span></span>  

 <span data-ttu-id="a5149-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a5149-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5149-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5149-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5149-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5149-122">Element</span></span>|<span data-ttu-id="a5149-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5149-123">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a5149-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a5149-124">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5149-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5149-125">Remarks</span></span>  

 <span data-ttu-id="a5149-126">Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio.</span><span class="sxs-lookup"><span data-stu-id="a5149-126">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="a5149-127">Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.</span><span class="sxs-lookup"><span data-stu-id="a5149-127">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="a5149-128">Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación.</span><span class="sxs-lookup"><span data-stu-id="a5149-128">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="a5149-129">En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio del enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron.</span><span class="sxs-lookup"><span data-stu-id="a5149-129">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="a5149-130">Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5149-130">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
