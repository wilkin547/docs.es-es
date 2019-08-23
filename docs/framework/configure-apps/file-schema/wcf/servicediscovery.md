---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936271"
---
# <a name="servicediscovery"></a><span data-ttu-id="32a69-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="32a69-101">\<serviceDiscovery></span></span>
<span data-ttu-id="32a69-102">Especifica la detectabilidad de extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="32a69-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="32a69-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="32a69-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="32a69-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="32a69-104">\<behaviors></span></span>  
<span data-ttu-id="32a69-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="32a69-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="32a69-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="32a69-106">\<behavior></span></span>  
<span data-ttu-id="32a69-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="32a69-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a69-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32a69-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32a69-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32a69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="32a69-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32a69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32a69-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="32a69-111">Attributes</span></span>  
 <span data-ttu-id="32a69-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="32a69-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32a69-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32a69-113">Child Elements</span></span>  
  
|<span data-ttu-id="32a69-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="32a69-114">Element</span></span>|<span data-ttu-id="32a69-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="32a69-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32a69-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="32a69-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="32a69-117">Colección de puntos de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="32a69-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="32a69-118">Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="32a69-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="32a69-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="32a69-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="32a69-120">Colección de extremos de detección.</span><span class="sxs-lookup"><span data-stu-id="32a69-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="32a69-121">Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="32a69-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32a69-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32a69-122">Parent Elements</span></span>  
  
|<span data-ttu-id="32a69-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="32a69-123">Element</span></span>|<span data-ttu-id="32a69-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="32a69-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32a69-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="32a69-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="32a69-126">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="32a69-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32a69-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32a69-127">Remarks</span></span>  
 <span data-ttu-id="32a69-128">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables.</span><span class="sxs-lookup"><span data-stu-id="32a69-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="32a69-129">Puede seguir configurando las características de detección de estos puntos de conexión [ \<](discoveryendpoint.md) mediante los elementos secundarios discoveryEndpoint > o [ \<announcementEndpoint >](announcementendpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="32a69-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="32a69-130">Use la [ \<sección > announcementEndpoint](announcementendpoint.md) para configurar los anuncios especificando la configuración del punto de conexión que se va a usar para enviar anuncios de servicio (en línea/Hola y sin conexión/adiós).</span><span class="sxs-lookup"><span data-stu-id="32a69-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="32a69-131">Use la [ \<sección > discoveryEndpoint](discoveryendpoint.md) para especificar manualmente el punto de conexión en el que se van a escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="32a69-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32a69-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32a69-132">Example</span></span>  
 <span data-ttu-id="32a69-133">El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="32a69-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32a69-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="32a69-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
