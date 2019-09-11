---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855395"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="1f03b-101">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="1f03b-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="1f03b-102">Este elemento de configuración define un punto de conexión estándar con un contrato de detección fijo.</span><span class="sxs-lookup"><span data-stu-id="1f03b-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="1f03b-103">Cuando se agrega a la configuración de servicio, especifica dónde escuchar los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="1f03b-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="1f03b-104">Cuando se agrega a la configuración del cliente, especifica dónde enviar las consultas de detección.</span><span class="sxs-lookup"><span data-stu-id="1f03b-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="1f03b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1f03b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1f03b-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1f03b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1f03b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1f03b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="1f03b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> discoveryEndpoint**</span><span class="sxs-lookup"><span data-stu-id="1f03b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f03b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f03b-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f03b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1f03b-110">Attributes and elements</span></span>

<span data-ttu-id="1f03b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1f03b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f03b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f03b-112">Attributes</span></span>

| <span data-ttu-id="1f03b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="1f03b-113">Attribute</span></span>        | <span data-ttu-id="1f03b-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1f03b-114">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="1f03b-115">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="1f03b-115">discoveryMode</span></span>    | <span data-ttu-id="1f03b-116">Cadena que especifica el modo del protocolo de detección.</span><span class="sxs-lookup"><span data-stu-id="1f03b-116">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="1f03b-117">Los valores válidos son "Adhoc" y "Managed".</span><span class="sxs-lookup"><span data-stu-id="1f03b-117">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="1f03b-118">En modo administrado, el protocolo se basa en un proxy de detección, que actúa como un repositorio de servicios detectables.</span><span class="sxs-lookup"><span data-stu-id="1f03b-118">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="1f03b-119">El modo Adhoc requiere que el protocolo utilice el mecanismo de multidifusión UDP para buscar servicios disponibles.</span><span class="sxs-lookup"><span data-stu-id="1f03b-119">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="1f03b-120">Para obtener más información sobre la propiedad, <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>vea.</span><span class="sxs-lookup"><span data-stu-id="1f03b-120">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="1f03b-121">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="1f03b-121">discoveryVersion</span></span> | <span data-ttu-id="1f03b-122">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="1f03b-122">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="1f03b-123">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="1f03b-123">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="1f03b-124">Este valor es del tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="1f03b-124">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="1f03b-125">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="1f03b-125">maxResponseDelay</span></span> | <span data-ttu-id="1f03b-126">Un valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar ciertos mensajes como Probe Match o Resolve Match.</span><span class="sxs-lookup"><span data-stu-id="1f03b-126">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="1f03b-127">Si se envían todos los ProbeMatches al mismo tiempo, puede producirse una tormenta de la red.</span><span class="sxs-lookup"><span data-stu-id="1f03b-127">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="1f03b-128">Para evitar que esto se produzca, ProbeMatches se envía con un retraso aleatorio entre cada ProbeMatch.</span><span class="sxs-lookup"><span data-stu-id="1f03b-128">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="1f03b-129">El retraso aleatorio se encuentra en el intervalo entre 0 y el valor establecido por este atributo.</span><span class="sxs-lookup"><span data-stu-id="1f03b-129">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="1f03b-130">Si este atributo está establecido en 0, los mensajes ProbeMatches se envían en un bucle ajustado sin ningún retraso.</span><span class="sxs-lookup"><span data-stu-id="1f03b-130">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="1f03b-131">En caso contrario, los mensajes ProbeMatches se envían con cierto retraso aleatorio de modo que el tiempo total empleado en enviar todos los mensajes ProbeMatches no supere maxResponseDelay.</span><span class="sxs-lookup"><span data-stu-id="1f03b-131">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="1f03b-132">Este valor solo es pertinente para los servicios, clientes no lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="1f03b-132">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="1f03b-133">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="1f03b-133">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1f03b-134">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="1f03b-134">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="1f03b-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1f03b-135">Child elements</span></span>

<span data-ttu-id="1f03b-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1f03b-136">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f03b-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1f03b-137">Parent elements</span></span>

| <span data-ttu-id="1f03b-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f03b-138">Element</span></span> | <span data-ttu-id="1f03b-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1f03b-139">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="1f03b-140">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1f03b-140">\<standardEndpoints></span></span>](standardendpoints.md) | <span data-ttu-id="1f03b-141">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="1f03b-141">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="1f03b-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f03b-142">Example</span></span>

<span data-ttu-id="1f03b-143">En el siguiente ejemplo se muestra un servicio que escucha mensajes de detección a través de un transporte de multidifusión de red del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1f03b-143">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="1f03b-144">El ejemplo especifica explícitamente la versión WS-Discovery April 2005.</span><span class="sxs-lookup"><span data-stu-id="1f03b-144">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="1f03b-145">La configuración del extremo estándar se define por servicio y no se puede compartir a través del servicio.</span><span class="sxs-lookup"><span data-stu-id="1f03b-145">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="1f03b-146">Si otro servicio quisiera tener el mismo extremo de detección, habría que agregar la misma configuración a la sección de dicho servicio.</span><span class="sxs-lookup"><span data-stu-id="1f03b-146">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="1f03b-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f03b-147">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
