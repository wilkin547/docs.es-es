---
description: 'Más información acerca de: <serviceThrottling>'
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: eb65f6d60a266a367789d87e4e6ea10ebfd2c7a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786686"
---
# \<serviceThrottling>

<span data-ttu-id="5357d-102">Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5357d-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="5357d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5357d-103">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5357d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5357d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5357d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5357d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5357d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5357d-106">Attributes</span></span>  
  
|<span data-ttu-id="5357d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="5357d-107">Attribute</span></span>|<span data-ttu-id="5357d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5357d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5357d-109">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="5357d-109">maxConcurrentCalls</span></span>|<span data-ttu-id="5357d-110">Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5357d-110">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="5357d-111">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="5357d-111">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="5357d-112">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="5357d-112">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="5357d-113">El valor predeterminado es 16 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="5357d-113">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="5357d-114">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="5357d-114">maxConcurrentInstances</span></span>|<span data-ttu-id="5357d-115">Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5357d-115">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="5357d-116">Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="5357d-116">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="5357d-117">El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="5357d-117">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="5357d-118">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="5357d-118">maxConcurrentSessions</span></span>|<span data-ttu-id="5357d-119">Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="5357d-119">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="5357d-120">El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos (los mensajes se leen desde el canal).</span><span class="sxs-lookup"><span data-stu-id="5357d-120">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="5357d-121">Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="5357d-121">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="5357d-122">El valor predeterminado es 100 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="5357d-122">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5357d-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5357d-123">Child Elements</span></span>  

 <span data-ttu-id="5357d-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5357d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5357d-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5357d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5357d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="5357d-126">Element</span></span>|<span data-ttu-id="5357d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="5357d-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5357d-128">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5357d-128">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5357d-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5357d-129">Remarks</span></span>  

 <span data-ttu-id="5357d-130">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="5357d-130">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="5357d-131">Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="5357d-131">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="5357d-132">El primer seguimiento se escribe como una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5357d-132">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5357d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5357d-133">Example</span></span>  

 <span data-ttu-id="5357d-134">El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="5357d-134">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="5357d-135">Para obtener un ejemplo detallado de cómo ejecutar este ejemplo, vea [limitación](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="5357d-135">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5357d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5357d-136">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="5357d-137">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="5357d-137">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
