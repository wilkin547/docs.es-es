---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210001"
---
# <a name="servicediscovery"></a><span data-ttu-id="c9bad-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="c9bad-101">\<serviceDiscovery></span></span>
<span data-ttu-id="c9bad-102">Especifica la detectabilidad de extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="c9bad-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="c9bad-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9bad-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9bad-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c9bad-104">\<behaviors></span></span>  
<span data-ttu-id="c9bad-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c9bad-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c9bad-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c9bad-106">\<behavior></span></span>  
<span data-ttu-id="c9bad-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="c9bad-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bad-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9bad-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9bad-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c9bad-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c9bad-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c9bad-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9bad-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c9bad-111">Attributes</span></span>  
 <span data-ttu-id="c9bad-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c9bad-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9bad-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c9bad-113">Child Elements</span></span>  
  
|<span data-ttu-id="c9bad-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9bad-114">Element</span></span>|<span data-ttu-id="c9bad-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9bad-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9bad-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="c9bad-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="c9bad-117">Colección de puntos de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="c9bad-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="c9bad-118">Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="c9bad-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="c9bad-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="c9bad-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="c9bad-120">Colección de extremos de detección.</span><span class="sxs-lookup"><span data-stu-id="c9bad-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="c9bad-121">Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="c9bad-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9bad-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c9bad-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c9bad-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9bad-123">Element</span></span>|<span data-ttu-id="c9bad-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9bad-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9bad-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c9bad-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c9bad-126">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c9bad-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9bad-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9bad-127">Remarks</span></span>  
 <span data-ttu-id="c9bad-128">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables.</span><span class="sxs-lookup"><span data-stu-id="c9bad-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="c9bad-129">Puede configurar aún más las características de detección de tales puntos de conexión con el [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) o [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c9bad-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="c9bad-130">Utilice la [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) sección para configurar los anuncios especificando la configuración de punto de conexión que debe usarse para enviar anuncios de servicio (en línea/Hola y sin conexión/Adiós).</span><span class="sxs-lookup"><span data-stu-id="c9bad-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="c9bad-131">Use la [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) sección para especificar manualmente el punto de conexión en el que se va a escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="c9bad-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9bad-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9bad-132">Example</span></span>  
 <span data-ttu-id="c9bad-133">El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="c9bad-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9bad-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9bad-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
