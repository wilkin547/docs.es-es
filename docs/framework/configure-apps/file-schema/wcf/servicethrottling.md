---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399561"
---
# \<serviceThrottling>
<span data-ttu-id="967f2-101">Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="967f2-101">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="967f2-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="967f2-102">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="967f2-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="967f2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="967f2-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="967f2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="967f2-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="967f2-105">Attributes</span></span>  
  
|<span data-ttu-id="967f2-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="967f2-106">Attribute</span></span>|<span data-ttu-id="967f2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="967f2-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="967f2-108">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="967f2-108">maxConcurrentCalls</span></span>|<span data-ttu-id="967f2-109">Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="967f2-109">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="967f2-110">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="967f2-110">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="967f2-111">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="967f2-111">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="967f2-112">El valor predeterminado es 16 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="967f2-112">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="967f2-113">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="967f2-113">maxConcurrentInstances</span></span>|<span data-ttu-id="967f2-114">Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="967f2-114">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="967f2-115">Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="967f2-115">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="967f2-116">El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="967f2-116">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="967f2-117">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="967f2-117">maxConcurrentSessions</span></span>|<span data-ttu-id="967f2-118">Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="967f2-118">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="967f2-119">El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos (los mensajes se leen desde el canal).</span><span class="sxs-lookup"><span data-stu-id="967f2-119">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="967f2-120">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="967f2-120">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="967f2-121">El valor predeterminado es 100 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="967f2-121">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="967f2-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="967f2-122">Child Elements</span></span>  
 <span data-ttu-id="967f2-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="967f2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="967f2-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="967f2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="967f2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="967f2-125">Element</span></span>|<span data-ttu-id="967f2-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="967f2-126">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="967f2-127">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="967f2-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="967f2-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="967f2-128">Remarks</span></span>  
 <span data-ttu-id="967f2-129">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="967f2-129">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="967f2-130">Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="967f2-130">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="967f2-131">El primer seguimiento se escribe como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="967f2-131">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="967f2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="967f2-132">Example</span></span>  
 <span data-ttu-id="967f2-133">El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="967f2-133">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="967f2-134">Para obtener un ejemplo detallado de cómo ejecutar este ejemplo, vea [limitación](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="967f2-134">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="967f2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="967f2-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="967f2-136">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="967f2-136">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
