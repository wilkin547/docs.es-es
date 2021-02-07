---
description: 'Más información acerca de: <udpAnnouncementEndpoint>'
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: f59e3e5365666835e910249e2cb37c2ce0e465e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749264"
---
# \<udpAnnouncementEndpoint>

<span data-ttu-id="56638-102">Este elemento de configuración define un extremo estándar usado por los servicios para enviar los mensajes del anuncio a través de un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="56638-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="56638-103">Tiene un contrato fijo y admite dos versiones de la detección.</span><span class="sxs-lookup"><span data-stu-id="56638-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="56638-104">Además, tiene un enlace de UDP fijo y un valor de dirección predeterminado según se indica en las especificaciones de WS-Discovery (WS-Discovery April 2005 o WS-Discovery versión 1.1).</span><span class="sxs-lookup"><span data-stu-id="56638-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="56638-105">Puede especificar la dirección de multidifusión que se va a usar para enviar y recibir los mensajes del anuncio.</span><span class="sxs-lookup"><span data-stu-id="56638-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="56638-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56638-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56638-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56638-107">Attributes and Elements</span></span>  

 <span data-ttu-id="56638-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56638-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56638-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="56638-109">Attributes</span></span>  
  
|<span data-ttu-id="56638-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="56638-110">Attribute</span></span>|<span data-ttu-id="56638-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="56638-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56638-112">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="56638-112">discoveryVersion</span></span>|<span data-ttu-id="56638-113">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="56638-113">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="56638-114">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="56638-114">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="56638-115">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="56638-115">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="56638-116">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="56638-116">maxAnnouncementDelay</span></span>|<span data-ttu-id="56638-117">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="56638-117">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="56638-118">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="56638-118">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="56638-119">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="56638-119">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="56638-120">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="56638-120">multicastAddress</span></span>|<span data-ttu-id="56638-121">URI que especifica una dirección de multidifusión que se va a usar para enviar y recibir los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="56638-121">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="56638-122">El valor predeterminado es la dirección de multidifusión como compatible con la especificación de protocolo.</span><span class="sxs-lookup"><span data-stu-id="56638-122">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="56638-123">name</span><span class="sxs-lookup"><span data-stu-id="56638-123">name</span></span>|<span data-ttu-id="56638-124">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="56638-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="56638-125">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="56638-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56638-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56638-126">Child Elements</span></span>  
  
|<span data-ttu-id="56638-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="56638-127">Element</span></span>|<span data-ttu-id="56638-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="56638-128">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="56638-129">Colección de valores que le permite configurar el transporte UDP para el punto de conexión UDP.</span><span class="sxs-lookup"><span data-stu-id="56638-129">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56638-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56638-130">Parent Elements</span></span>  
  
|<span data-ttu-id="56638-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="56638-131">Element</span></span>|<span data-ttu-id="56638-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="56638-132">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="56638-133">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="56638-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56638-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56638-134">Example</span></span>  

 <span data-ttu-id="56638-135">En el siguiente ejemplo se muestra un cliente que escucha un anuncio a través de un transporte de multidifusión UDP con una dirección de multidifusión predeterminada y transporte de multidifusión UDP con una dirección de multidifusión especificada.</span><span class="sxs-lookup"><span data-stu-id="56638-135">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56638-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="56638-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
