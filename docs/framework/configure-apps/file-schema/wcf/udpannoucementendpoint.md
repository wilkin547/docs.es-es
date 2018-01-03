---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73f4dd1374164a005c600b81dcf4fa558a57c803
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="3cfee-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="3cfee-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="3cfee-103">Este elemento de configuración define un punto de conexión estándar usado por los servicios para enviar los mensajes del anuncio a través de un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="3cfee-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="3cfee-104">Tiene un contrato fijo y admite dos versiones de la detección.</span><span class="sxs-lookup"><span data-stu-id="3cfee-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="3cfee-105">Además, tiene un enlace de UDP fijo y un valor de dirección predeterminado según se indica en las especificaciones de WS-Discovery (WS-Discovery April 2005 o WS-Discovery versión 1.1).</span><span class="sxs-lookup"><span data-stu-id="3cfee-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="3cfee-106">Puede especificar la dirección de multidifusión que se va a usar para enviar y recibir los mensajes del anuncio.</span><span class="sxs-lookup"><span data-stu-id="3cfee-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="3cfee-107">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3cfee-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cfee-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3cfee-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfee-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cfee-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cfee-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3cfee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cfee-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3cfee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cfee-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3cfee-112">Attributes</span></span>  
  
|<span data-ttu-id="3cfee-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3cfee-113">Attribute</span></span>|<span data-ttu-id="3cfee-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cfee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cfee-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="3cfee-115">discoveryVersion</span></span>|<span data-ttu-id="3cfee-116">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="3cfee-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="3cfee-117">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="3cfee-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="3cfee-118">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="3cfee-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="3cfee-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="3cfee-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="3cfee-120">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="3cfee-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="3cfee-121">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="3cfee-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="3cfee-122">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3cfee-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="3cfee-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="3cfee-123">multicastAddress</span></span>|<span data-ttu-id="3cfee-124">URI que especifica una dirección de multidifusión que se va a usar para enviar y recibir los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="3cfee-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="3cfee-125">El valor predeterminado es la dirección de multidifusión como compatible con la especificación de protocolo.</span><span class="sxs-lookup"><span data-stu-id="3cfee-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="3cfee-126">name</span><span class="sxs-lookup"><span data-stu-id="3cfee-126">name</span></span>|<span data-ttu-id="3cfee-127">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="3cfee-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3cfee-128">El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="3cfee-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cfee-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3cfee-129">Child Elements</span></span>  
  
|<span data-ttu-id="3cfee-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cfee-130">Element</span></span>|<span data-ttu-id="3cfee-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cfee-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cfee-132">\<udpTransportSettings ></span><span class="sxs-lookup"><span data-stu-id="3cfee-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="3cfee-133">Colección de valores que le permite configurar el transporte UDP para el punto de conexión UDP.</span><span class="sxs-lookup"><span data-stu-id="3cfee-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cfee-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3cfee-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3cfee-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cfee-135">Element</span></span>|<span data-ttu-id="3cfee-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cfee-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cfee-137">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3cfee-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3cfee-138">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="3cfee-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3cfee-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cfee-139">Example</span></span>  
 <span data-ttu-id="3cfee-140">En el siguiente ejemplo se muestra un cliente que escucha un anuncio a través de un transporte de multidifusión UDP con una dirección de multidifusión predeterminada y transporte de multidifusión UDP con una dirección de multidifusión especificada.</span><span class="sxs-lookup"><span data-stu-id="3cfee-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
      <endpoint name="udpAnnouncementEndpointStandard"  
                kind="udpAnnouncementEndpoint"  
                bindingConfiguration="..." />  
      <endpoint name="udpAnnouncementEndpoint2"  
                kind="udpAnnouncementEndpoint"  
                endpointConfiguration="AnnouncementConfiguration3702"  
                bindingConfiguration="..." />  
...  
  </service>  
</services>  
<standardEndpoints>  
  <udpAnnouncementEndpoint>  
     <standardEndpoint name="AnnouncementConfiguration2"   
          version="WSDiscoveryApril2005"   
          multicastAddress="soap.udp://239.255.255.250:3703"/>          
  </udpAnnouncementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cfee-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cfee-141">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
