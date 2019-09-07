---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399641"
---
# <a name="servicediscovery"></a><span data-ttu-id="d432f-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="d432f-101">\<serviceDiscovery></span></span>
<span data-ttu-id="d432f-102">Especifica la detectabilidad de extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="d432f-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="d432f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d432f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d432f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d432f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d432f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d432f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d432f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d432f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d432f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d432f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d432f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceDiscovery**</span><span class="sxs-lookup"><span data-stu-id="d432f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d432f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d432f-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d432f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d432f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d432f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d432f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d432f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d432f-112">Attributes</span></span>  
 <span data-ttu-id="d432f-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d432f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d432f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d432f-114">Child Elements</span></span>  
  
|<span data-ttu-id="d432f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d432f-115">Element</span></span>|<span data-ttu-id="d432f-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d432f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d432f-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="d432f-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="d432f-118">Colección de puntos de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="d432f-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="d432f-119">Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="d432f-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="d432f-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="d432f-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="d432f-121">Colección de extremos de detección.</span><span class="sxs-lookup"><span data-stu-id="d432f-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="d432f-122">Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="d432f-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d432f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d432f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d432f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d432f-124">Element</span></span>|<span data-ttu-id="d432f-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d432f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d432f-126">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d432f-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d432f-127">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d432f-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d432f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d432f-128">Remarks</span></span>  
 <span data-ttu-id="d432f-129">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables.</span><span class="sxs-lookup"><span data-stu-id="d432f-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="d432f-130">Puede seguir configurando las características de detección de estos puntos de conexión [ \<](discoveryendpoint.md) mediante los elementos secundarios discoveryEndpoint > o [ \<announcementEndpoint >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="d432f-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="d432f-131">Use la [ \<sección > announcementEndpoint](announcementendpoint.md) para configurar los anuncios especificando la configuración del punto de conexión que se va a usar para enviar anuncios de servicio (en línea/Hola y sin conexión/adiós).</span><span class="sxs-lookup"><span data-stu-id="d432f-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="d432f-132">Use la [ \<sección > discoveryEndpoint](discoveryendpoint.md) para especificar manualmente el punto de conexión en el que se van a escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="d432f-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d432f-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d432f-133">Example</span></span>  
 <span data-ttu-id="d432f-134">El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="d432f-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="d432f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d432f-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
