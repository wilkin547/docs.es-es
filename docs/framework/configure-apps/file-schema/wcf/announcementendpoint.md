---
description: 'Más información acerca de: <announcementEndpoint>'
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: d010abb789a4401e9f0591f34edb29ec2036f16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749927"
---
# \<announcementEndpoint>

<span data-ttu-id="6ad2c-102">Este elemento de configuración define un punto de conexión estándar con un contrato del anuncio fijo.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="6ad2c-103">Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="6ad2c-104">Un servicio Windows Communication Foundation (WCF) especifica los puntos de conexión del anuncio en el [\<serviceDiscovery>](servicediscovery.md) elemento y usa AnnouncementClient para realizar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="6ad2c-105">Un cliente que desea escuchar el anuncio desde otro servicio está actuando realmente como un servicio WCF. por lo tanto, tiene que configurar los extremos de anuncio para ese cliente en la [\<services>](services.md) sección.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="6ad2c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad2c-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ad2c-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ad2c-107">Attributes and Elements</span></span>  

 <span data-ttu-id="6ad2c-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ad2c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ad2c-109">Attributes</span></span>  
  
|<span data-ttu-id="6ad2c-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ad2c-110">Attribute</span></span>|<span data-ttu-id="6ad2c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ad2c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ad2c-112">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="6ad2c-112">discoveryVersion</span></span>|<span data-ttu-id="6ad2c-113">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-113">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="6ad2c-114">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-114">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="6ad2c-115">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-115">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="6ad2c-116">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="6ad2c-116">maxAnnouncementDelay</span></span>|<span data-ttu-id="6ad2c-117">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-117">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="6ad2c-118">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-118">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="6ad2c-119">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-119">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="6ad2c-120">name</span><span class="sxs-lookup"><span data-stu-id="6ad2c-120">name</span></span>|<span data-ttu-id="6ad2c-121">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-121">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="6ad2c-122">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-122">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ad2c-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ad2c-123">Child Elements</span></span>  

 <span data-ttu-id="6ad2c-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ad2c-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ad2c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6ad2c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2c-126">Element</span></span>|<span data-ttu-id="6ad2c-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ad2c-127">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6ad2c-128">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-128">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6ad2c-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ad2c-129">Example</span></span>  

 <span data-ttu-id="6ad2c-130">En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-130">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="6ad2c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ad2c-131">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
