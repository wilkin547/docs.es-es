---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: 180763404ee9070e9ed6e5476d4568a0a018dcb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788159"
---
# <a name="udpdiscoveryendpoint"></a><span data-ttu-id="088fb-101">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="088fb-101">\<udpDiscoveryEndpoint></span></span>
<span data-ttu-id="088fb-102">Este elemento de configuración define un extremo estándar que está preconfigurado para las operaciones de detección sobre un enlace de multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="088fb-102">This configuration element defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="088fb-103">Este punto de conexión tiene un contrato fijo y admite dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="088fb-103">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="088fb-104">Además, tiene un enlace de UDP fijo y una dirección predeterminada según se indica en las especificaciones de WS-Discovery (WS-Discovery April 2005 o WS-Discovery V1.1).</span><span class="sxs-lookup"><span data-stu-id="088fb-104">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>  
  
 <span data-ttu-id="088fb-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="088fb-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="088fb-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="088fb-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088fb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="088fb-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="088fb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="088fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="088fb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="088fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="088fb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="088fb-110">Attributes</span></span>  
  
|<span data-ttu-id="088fb-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="088fb-111">Attribute</span></span>|<span data-ttu-id="088fb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="088fb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="088fb-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="088fb-113">discoveryMode</span></span>|<span data-ttu-id="088fb-114">Cadena que especifica el modo del protocolo de detección.</span><span class="sxs-lookup"><span data-stu-id="088fb-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="088fb-115">Los valores válidos son "Adhoc" y "Administrado".</span><span class="sxs-lookup"><span data-stu-id="088fb-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="088fb-116">En modo administrado, el protocolo se basa en un proxy de detección, que actúa como un repositorio de servicios detectables.</span><span class="sxs-lookup"><span data-stu-id="088fb-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="088fb-117">El modo Adhoc requiere que el protocolo utilice el mecanismo de multidifusión UDP para buscar servicios disponibles.</span><span class="sxs-lookup"><span data-stu-id="088fb-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="088fb-118">Este valor es del tipo <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span><span class="sxs-lookup"><span data-stu-id="088fb-118">This value is of type <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.</span></span>|  
|<span data-ttu-id="088fb-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="088fb-119">discoveryVersion</span></span>|<span data-ttu-id="088fb-120">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="088fb-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="088fb-121">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="088fb-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="088fb-122">Este valor es del tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="088fb-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="088fb-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="088fb-123">maxResponseDelay</span></span>|<span data-ttu-id="088fb-124">Un valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar ciertos mensajes como Probe Match o Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="088fb-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="088fb-125">Si se envían todos los ProbeMatches al mismo tiempo, puede producirse una tormenta de la red.</span><span class="sxs-lookup"><span data-stu-id="088fb-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="088fb-126">Para evitar que esto se produzca, ProbeMatches se envía con un retraso aleatorio entre cada ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="088fb-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="088fb-127">El retraso aleatorio se encuentra en el intervalo entre 0 y el valor establecido por este atributo.</span><span class="sxs-lookup"><span data-stu-id="088fb-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="088fb-128">Si este atributo está establecido en 0, los mensajes ProbeMatches se envían en un bucle ajustado sin ningún retraso.</span><span class="sxs-lookup"><span data-stu-id="088fb-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="088fb-129">En caso contrario, los mensajes ProbeMatches se envían con cierto retraso aleatorio de modo que el tiempo total empleado en enviar todos los mensajes ProbeMatches no supere maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="088fb-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="088fb-130">Este valor solo es pertinente para los servicios, clientes no lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="088fb-130">This value is only relevant for services, it is not used by clients.</span></span>|  
|<span data-ttu-id="088fb-131">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="088fb-131">multicastAddress</span></span>|<span data-ttu-id="088fb-132">Uri que especifica una dirección de multidifusión que se va a usar para enviar y recibir los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="088fb-132">A Uri that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="088fb-133">El valor predeterminado es la dirección de multidifusión como compatible con la especificación de protocolo.</span><span class="sxs-lookup"><span data-stu-id="088fb-133">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|`name`|<span data-ttu-id="088fb-134">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="088fb-134">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="088fb-135">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="088fb-135">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="088fb-136">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="088fb-136">Child Elements</span></span>  
  
|<span data-ttu-id="088fb-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="088fb-137">Element</span></span>|<span data-ttu-id="088fb-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="088fb-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="088fb-139">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="088fb-139">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="088fb-140">Colección de valores que le permite configurar el transporte UDP para el punto de conexión UDP.</span><span class="sxs-lookup"><span data-stu-id="088fb-140">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="088fb-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="088fb-141">Parent Elements</span></span>  
  
|<span data-ttu-id="088fb-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="088fb-142">Element</span></span>|<span data-ttu-id="088fb-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="088fb-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="088fb-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="088fb-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="088fb-145">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="088fb-145">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="088fb-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="088fb-146">Example</span></span>  
 <span data-ttu-id="088fb-147">En el siguiente ejemplo se muestra un servicio que realiza escuchas de mensajes de detección sobre un transporte de multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="088fb-147">The following example demonstrates a service listening for discovery messages over a UDP multicast transport.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="088fb-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="088fb-148">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
