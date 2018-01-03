---
title: '&lt;serviceThrottling&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a059684967af26c72aca48a3fa6bb10c2f26b0c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="ef156-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="ef156-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="ef156-103">Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ef156-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="ef156-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ef156-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef156-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="ef156-105">\<behaviors></span></span>  
<span data-ttu-id="ef156-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ef156-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ef156-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="ef156-107">\<behavior></span></span>  
<span data-ttu-id="ef156-108">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="ef156-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef156-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef156-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef156-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef156-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef156-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef156-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef156-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef156-112">Attributes</span></span>  
  
|<span data-ttu-id="ef156-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef156-113">Attribute</span></span>|<span data-ttu-id="ef156-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef156-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef156-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="ef156-115">maxConcurrentCalls</span></span>|<span data-ttu-id="ef156-116">Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="ef156-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="ef156-117">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="ef156-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="ef156-118">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="ef156-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="ef156-119">El valor predeterminado es 16 * número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="ef156-119">The default is 16 * processor count.</span></span>|  
|<span data-ttu-id="ef156-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="ef156-120">maxConcurrentInstances</span></span>|<span data-ttu-id="ef156-121">Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="ef156-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="ef156-122">Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="ef156-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="ef156-123">El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="ef156-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="ef156-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="ef156-124">maxConcurrentSessions</span></span>|<span data-ttu-id="ef156-125">Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="ef156-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="ef156-126">El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos (los mensajes se leen desde el canal).</span><span class="sxs-lookup"><span data-stu-id="ef156-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="ef156-127">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="ef156-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="ef156-128">El valor predeterminado es 100 * número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="ef156-128">The default is 100 * processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef156-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef156-129">Child Elements</span></span>  
 <span data-ttu-id="ef156-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef156-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef156-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef156-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ef156-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef156-132">Element</span></span>|<span data-ttu-id="ef156-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef156-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef156-134">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="ef156-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ef156-135">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ef156-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef156-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef156-136">Remarks</span></span>  
 <span data-ttu-id="ef156-137">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="ef156-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="ef156-138">Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="ef156-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="ef156-139">El primer seguimiento se escribe como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ef156-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef156-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef156-140">Example</span></span>  
 <span data-ttu-id="ef156-141">El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="ef156-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="ef156-142">Para obtener un ejemplo detallado de la ejecución de este ejemplo, vea [limitación](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="ef156-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef156-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef156-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="ef156-144">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="ef156-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
