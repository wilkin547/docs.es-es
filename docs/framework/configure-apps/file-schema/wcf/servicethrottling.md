---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 995ff9979096757225c9241e977f86f755955945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158775"
---
# <a name="servicethrottling"></a><span data-ttu-id="c0c13-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="c0c13-101">\<serviceThrottling></span></span>
<span data-ttu-id="c0c13-102">Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c0c13-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="c0c13-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c0c13-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c0c13-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c0c13-104">\<behaviors></span></span>  
<span data-ttu-id="c0c13-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c0c13-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c0c13-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c0c13-106">\<behavior></span></span>  
<span data-ttu-id="c0c13-107">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="c0c13-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c13-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0c13-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0c13-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c0c13-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0c13-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c0c13-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0c13-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0c13-111">Attributes</span></span>  
  
|<span data-ttu-id="c0c13-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c0c13-112">Attribute</span></span>|<span data-ttu-id="c0c13-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0c13-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0c13-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c0c13-114">maxConcurrentCalls</span></span>|<span data-ttu-id="c0c13-115">Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c0c13-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c0c13-116">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="c0c13-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="c0c13-117">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c0c13-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c0c13-118">El valor predeterminado es 16 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="c0c13-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="c0c13-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="c0c13-119">maxConcurrentInstances</span></span>|<span data-ttu-id="c0c13-120">Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c0c13-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c0c13-121">Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="c0c13-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="c0c13-122">El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c0c13-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="c0c13-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="c0c13-123">maxConcurrentSessions</span></span>|<span data-ttu-id="c0c13-124">Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="c0c13-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="c0c13-125">El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos (los mensajes se leen desde el canal).</span><span class="sxs-lookup"><span data-stu-id="c0c13-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="c0c13-126">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c0c13-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c0c13-127">El valor predeterminado es 100 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="c0c13-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0c13-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c0c13-128">Child Elements</span></span>  
 <span data-ttu-id="c0c13-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c0c13-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0c13-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c0c13-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c0c13-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0c13-131">Element</span></span>|<span data-ttu-id="c0c13-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0c13-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c13-133">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c0c13-133">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c0c13-134">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c0c13-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c13-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0c13-135">Remarks</span></span>  
 <span data-ttu-id="c0c13-136">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="c0c13-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="c0c13-137">Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="c0c13-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="c0c13-138">El primer seguimiento se escribe como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c0c13-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0c13-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0c13-139">Example</span></span>  
 <span data-ttu-id="c0c13-140">El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="c0c13-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="c0c13-141">Para obtener un ejemplo detallado de la ejecución de este ejemplo, vea [limitación](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="c0c13-141">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="c0c13-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c13-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="c0c13-143">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="c0c13-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
