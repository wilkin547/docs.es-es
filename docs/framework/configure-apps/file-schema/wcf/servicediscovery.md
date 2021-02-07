---
description: 'Más información acerca de: <serviceDiscovery>'
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: d6df5b8d51763429829c2ea3c2593003720b7179
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682857"
---
# \<serviceDiscovery>

<span data-ttu-id="b95aa-102">Especifica la detectabilidad de extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="b95aa-102">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="b95aa-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b95aa-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b95aa-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b95aa-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b95aa-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b95aa-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b95aa-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="b95aa-106">Attributes</span></span>  

 <span data-ttu-id="b95aa-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b95aa-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b95aa-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b95aa-108">Child Elements</span></span>  
  
|<span data-ttu-id="b95aa-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="b95aa-109">Element</span></span>|<span data-ttu-id="b95aa-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b95aa-110">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="b95aa-111">Colección de puntos de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="b95aa-111">A collection of announcement endpoints.</span></span> <span data-ttu-id="b95aa-112">Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="b95aa-112">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="b95aa-113">Colección de extremos de detección.</span><span class="sxs-lookup"><span data-stu-id="b95aa-113">A collection of discovery endpoints.</span></span> <span data-ttu-id="b95aa-114">Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="b95aa-114">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b95aa-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b95aa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b95aa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b95aa-116">Element</span></span>|<span data-ttu-id="b95aa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b95aa-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b95aa-118">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b95aa-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b95aa-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b95aa-119">Remarks</span></span>  

 <span data-ttu-id="b95aa-120">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables.</span><span class="sxs-lookup"><span data-stu-id="b95aa-120">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="b95aa-121">Puede seguir configurando las características de detección de estos puntos de conexión mediante los [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) elementos secundarios o.</span><span class="sxs-lookup"><span data-stu-id="b95aa-121">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="b95aa-122">Use la [\<announcementEndpoint>](announcementendpoint.md) sección para configurar los anuncios especificando la configuración del punto de conexión que se va a usar para enviar anuncios de servicio (en línea/Hola y sin conexión/adiós).</span><span class="sxs-lookup"><span data-stu-id="b95aa-122">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="b95aa-123">Use la [\<discoveryEndpoint>](discoveryendpoint.md) sección para especificar manualmente el punto de conexión en el que se van a escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="b95aa-123">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b95aa-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b95aa-124">Example</span></span>  

 <span data-ttu-id="b95aa-125">El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="b95aa-125">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b95aa-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b95aa-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
