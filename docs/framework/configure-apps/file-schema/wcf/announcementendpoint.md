---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: aa4cd8f4d7dcfa438ede71c394f1d0b0ac6faa50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926548"
---
# <a name="announcementendpoint"></a><span data-ttu-id="cc482-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="cc482-101">\<announcementEndpoint></span></span>
<span data-ttu-id="cc482-102">Este elemento de configuración define un punto de conexión estándar con un contrato del anuncio fijo.</span><span class="sxs-lookup"><span data-stu-id="cc482-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="cc482-103">Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cc482-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="cc482-104">Un servicio de Windows Communication Foundation (WCF) especifica los puntos de conexión de [ \<](servicediscovery.md) anuncio en el elemento de > serviceDiscovery y usa AnnouncementClient para realizar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="cc482-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="cc482-105">Un cliente que desea escuchar el anuncio desde otro servicio está actuando realmente como un servicio WCF. por lo tanto, tiene que configurar los extremos de anuncio para ese cliente en la [ \<sección Servicios >](services.md) .</span><span class="sxs-lookup"><span data-stu-id="cc482-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="cc482-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cc482-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc482-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cc482-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc482-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc482-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc482-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc482-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc482-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc482-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc482-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc482-111">Attributes</span></span>  
  
|<span data-ttu-id="cc482-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc482-112">Attribute</span></span>|<span data-ttu-id="cc482-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cc482-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc482-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="cc482-114">discoveryVersion</span></span>|<span data-ttu-id="cc482-115">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="cc482-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="cc482-116">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="cc482-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="cc482-117">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="cc482-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="cc482-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="cc482-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="cc482-119">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="cc482-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="cc482-120">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="cc482-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="cc482-121">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="cc482-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="cc482-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="cc482-122">name</span></span>|<span data-ttu-id="cc482-123">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="cc482-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="cc482-124">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="cc482-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc482-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc482-125">Child Elements</span></span>  
 <span data-ttu-id="cc482-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cc482-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc482-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc482-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cc482-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc482-128">Element</span></span>|<span data-ttu-id="cc482-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cc482-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc482-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cc482-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="cc482-131">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="cc482-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cc482-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc482-132">Example</span></span>  
 <span data-ttu-id="cc482-133">En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.</span><span class="sxs-lookup"><span data-stu-id="cc482-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cc482-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc482-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
