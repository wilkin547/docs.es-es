---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 4f3cf2748acc75b0ec83732664c5f97114f3663a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195129"
---
# <a name="announcementendpoint"></a><span data-ttu-id="5fa53-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="5fa53-101">\<announcementEndpoint></span></span>
<span data-ttu-id="5fa53-102">Este elemento de configuración define un punto de conexión estándar con un contrato del anuncio fijo.</span><span class="sxs-lookup"><span data-stu-id="5fa53-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="5fa53-103">Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5fa53-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="5fa53-104">Un servicio de Windows Communication Foundation (WCF) especifica los extremos del anuncio en el [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento y utiliza AnnouncementClient para realizar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="5fa53-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="5fa53-105">Un cliente que desea escuchar el anuncio desde otro servicio realmente está actuando como un servicio WCF; Por tanto, tendrá que configurar los extremos del anuncio para el cliente en el [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección.</span><span class="sxs-lookup"><span data-stu-id="5fa53-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="5fa53-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5fa53-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="5fa53-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5fa53-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa53-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fa53-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fa53-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5fa53-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5fa53-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5fa53-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fa53-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5fa53-111">Attributes</span></span>  
  
|<span data-ttu-id="5fa53-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5fa53-112">Attribute</span></span>|<span data-ttu-id="5fa53-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fa53-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5fa53-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="5fa53-114">discoveryVersion</span></span>|<span data-ttu-id="5fa53-115">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="5fa53-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="5fa53-116">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="5fa53-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="5fa53-117">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="5fa53-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="5fa53-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="5fa53-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="5fa53-119">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="5fa53-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="5fa53-120">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="5fa53-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="5fa53-121">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5fa53-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="5fa53-122">name</span><span class="sxs-lookup"><span data-stu-id="5fa53-122">name</span></span>|<span data-ttu-id="5fa53-123">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="5fa53-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="5fa53-124">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="5fa53-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fa53-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5fa53-125">Child Elements</span></span>  
 <span data-ttu-id="5fa53-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5fa53-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fa53-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5fa53-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5fa53-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="5fa53-128">Element</span></span>|<span data-ttu-id="5fa53-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fa53-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fa53-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5fa53-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5fa53-131">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="5fa53-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5fa53-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fa53-132">Example</span></span>  
 <span data-ttu-id="5fa53-133">En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.</span><span class="sxs-lookup"><span data-stu-id="5fa53-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fa53-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fa53-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
