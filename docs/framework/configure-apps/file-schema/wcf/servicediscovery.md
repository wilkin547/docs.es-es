---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 73943f5f962a6963809e2c65ce8593f6181559f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587338"
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="12e95-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="12e95-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="12e95-103">Especifica la detectabilidad de puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="12e95-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="12e95-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="12e95-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="12e95-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="12e95-105">\<behaviors></span></span>  
<span data-ttu-id="12e95-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="12e95-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="12e95-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="12e95-107">\<behavior></span></span>  
<span data-ttu-id="12e95-108">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="12e95-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e95-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12e95-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12e95-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="12e95-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12e95-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="12e95-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12e95-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="12e95-112">Attributes</span></span>  
 <span data-ttu-id="12e95-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="12e95-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12e95-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="12e95-114">Child Elements</span></span>  
  
|<span data-ttu-id="12e95-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="12e95-115">Element</span></span>|<span data-ttu-id="12e95-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="12e95-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12e95-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="12e95-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="12e95-118">Colección de puntos de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="12e95-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="12e95-119">Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="12e95-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="12e95-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="12e95-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="12e95-121">Colección de puntos de conexión de detección.</span><span class="sxs-lookup"><span data-stu-id="12e95-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="12e95-122">Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="12e95-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12e95-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="12e95-123">Parent Elements</span></span>  
  
|<span data-ttu-id="12e95-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="12e95-124">Element</span></span>|<span data-ttu-id="12e95-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="12e95-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12e95-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="12e95-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="12e95-127">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="12e95-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12e95-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12e95-128">Remarks</span></span>  
 <span data-ttu-id="12e95-129">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables.</span><span class="sxs-lookup"><span data-stu-id="12e95-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="12e95-130">Puede configurar aún más las características de detección de tales puntos de conexión con el [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) o [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="12e95-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="12e95-131">Utilice la [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) sección para configurar los anuncios especificando la configuración de punto de conexión que debe usarse para enviar anuncios de servicio (en línea/Hola y sin conexión/Adiós).</span><span class="sxs-lookup"><span data-stu-id="12e95-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="12e95-132">Use la [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) sección para especificar manualmente el punto de conexión en el que se va a escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="12e95-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12e95-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12e95-133">Example</span></span>  
 <span data-ttu-id="12e95-134">El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="12e95-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12e95-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="12e95-135">See also</span></span>
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
