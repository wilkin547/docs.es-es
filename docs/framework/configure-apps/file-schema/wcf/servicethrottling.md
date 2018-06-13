---
title: '&lt;serviceThrottling&gt;'
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: b0f5197bf4e9017007f29f86048756b43e3b15fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750172"
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="97175-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="97175-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="97175-103">Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="97175-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="97175-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="97175-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="97175-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="97175-105">\<behaviors></span></span>  
<span data-ttu-id="97175-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="97175-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="97175-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97175-107">\<behavior></span></span>  
<span data-ttu-id="97175-108">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="97175-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97175-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97175-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97175-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97175-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97175-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97175-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97175-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="97175-112">Attributes</span></span>  
  
|<span data-ttu-id="97175-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="97175-113">Attribute</span></span>|<span data-ttu-id="97175-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="97175-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97175-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="97175-115">maxConcurrentCalls</span></span>|<span data-ttu-id="97175-116">Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="97175-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="97175-117">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="97175-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="97175-118">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="97175-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="97175-119">El valor predeterminado es 16 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="97175-119">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="97175-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="97175-120">maxConcurrentInstances</span></span>|<span data-ttu-id="97175-121">Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="97175-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="97175-122">Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="97175-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="97175-123">El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="97175-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="97175-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="97175-124">maxConcurrentSessions</span></span>|<span data-ttu-id="97175-125">Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="97175-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="97175-126">El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos (los mensajes se leen desde el canal).</span><span class="sxs-lookup"><span data-stu-id="97175-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="97175-127">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="97175-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="97175-128">El valor predeterminado es 100 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="97175-128">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97175-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97175-129">Child Elements</span></span>  
 <span data-ttu-id="97175-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97175-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97175-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97175-131">Parent Elements</span></span>  
  
|<span data-ttu-id="97175-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="97175-132">Element</span></span>|<span data-ttu-id="97175-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="97175-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97175-134">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97175-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="97175-135">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="97175-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97175-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97175-136">Remarks</span></span>  
 <span data-ttu-id="97175-137">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="97175-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="97175-138">Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="97175-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="97175-139">El primer seguimiento se escribe como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="97175-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97175-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97175-140">Example</span></span>  
 <span data-ttu-id="97175-141">El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="97175-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="97175-142">Para obtener un ejemplo detallado de la ejecución de este ejemplo, vea [limitación](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="97175-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97175-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="97175-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="97175-144">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="97175-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
