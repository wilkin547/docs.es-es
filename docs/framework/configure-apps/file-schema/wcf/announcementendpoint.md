---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: decaaa1cea5345ff971b16cbb20a85dd803a52d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850283"
---
# <a name="announcementendpoint"></a><span data-ttu-id="afa38-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="afa38-101">\<announcementEndpoint></span></span>
<span data-ttu-id="afa38-102">Este elemento de configuración define un punto de conexión estándar con un contrato del anuncio fijo.</span><span class="sxs-lookup"><span data-stu-id="afa38-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="afa38-103">Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.</span><span class="sxs-lookup"><span data-stu-id="afa38-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="afa38-104">Un servicio de Windows Communication Foundation (WCF) especifica los puntos de conexión de [ \<](servicediscovery.md) anuncio en el elemento de > serviceDiscovery y usa AnnouncementClient para realizar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="afa38-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="afa38-105">Un cliente que desea escuchar el anuncio desde otro servicio está actuando realmente como un servicio WCF. por lo tanto, tiene que configurar los extremos de anuncio para ese cliente en la [ \<sección Servicios >](services.md) .</span><span class="sxs-lookup"><span data-stu-id="afa38-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="afa38-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afa38-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afa38-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="afa38-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="afa38-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="afa38-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="afa38-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> announcementEndpoint**</span><span class="sxs-lookup"><span data-stu-id="afa38-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa38-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afa38-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa38-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="afa38-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afa38-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="afa38-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa38-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="afa38-113">Attributes</span></span>  
  
|<span data-ttu-id="afa38-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="afa38-114">Attribute</span></span>|<span data-ttu-id="afa38-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="afa38-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afa38-116">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="afa38-116">discoveryVersion</span></span>|<span data-ttu-id="afa38-117">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="afa38-117">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="afa38-118">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="afa38-118">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="afa38-119">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="afa38-119">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="afa38-120">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="afa38-120">maxAnnouncementDelay</span></span>|<span data-ttu-id="afa38-121">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="afa38-121">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="afa38-122">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="afa38-122">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="afa38-123">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="afa38-123">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="afa38-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="afa38-124">name</span></span>|<span data-ttu-id="afa38-125">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="afa38-125">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="afa38-126">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="afa38-126">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afa38-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="afa38-127">Child Elements</span></span>  
 <span data-ttu-id="afa38-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="afa38-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afa38-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="afa38-129">Parent Elements</span></span>  
  
|<span data-ttu-id="afa38-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="afa38-130">Element</span></span>|<span data-ttu-id="afa38-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="afa38-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa38-132">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="afa38-132">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="afa38-133">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="afa38-133">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="afa38-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afa38-134">Example</span></span>  
 <span data-ttu-id="afa38-135">En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.</span><span class="sxs-lookup"><span data-stu-id="afa38-135">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afa38-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="afa38-136">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
