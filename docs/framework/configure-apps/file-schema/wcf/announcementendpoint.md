---
title: '&lt;announcementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae03b5d4a82c08978a3456e80428ba6ad8ac532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="b818d-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="b818d-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="b818d-103">Este elemento de configuración define un punto de conexión estándar con un contrato del anuncio fijo.</span><span class="sxs-lookup"><span data-stu-id="b818d-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="b818d-104">Un servicio puede anunciar su disponibilidad opcionalmente enviando un mensaje del anuncio en línea y sin conexión cuando se abre o se cierra respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b818d-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="b818d-105">A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] servicio especifica los extremos de anuncio en el [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento y se utiliza el AnnouncementClient para realizar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="b818d-105">A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="b818d-106">Un cliente que desea realizar escuchas para el anuncio de otro servicio realmente está actuando como un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servicio; por tanto, tendrá que configurar los extremos de anuncio para el cliente en el [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sección.</span><span class="sxs-lookup"><span data-stu-id="b818d-106">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="b818d-107">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b818d-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="b818d-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b818d-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b818d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b818d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b818d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b818d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b818d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b818d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b818d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b818d-112">Attributes</span></span>  
  
|<span data-ttu-id="b818d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b818d-113">Attribute</span></span>|<span data-ttu-id="b818d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b818d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b818d-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="b818d-115">discoveryVersion</span></span>|<span data-ttu-id="b818d-116">Cadena que especifica una de las dos versiones del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="b818d-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="b818d-117">Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="b818d-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="b818d-118">Este valor es del tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="b818d-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="b818d-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="b818d-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="b818d-120">Valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar un mensaje de saludo.</span><span class="sxs-lookup"><span data-stu-id="b818d-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="b818d-121">Los mensajes esperarán un valor de tiempo aleatorio entre 0 y el valor de este atributo antes de enviarse.</span><span class="sxs-lookup"><span data-stu-id="b818d-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="b818d-122">Este atributo se utiliza para establecer un retraso pequeño y aleatorio con el fin de evitar las tormentas de red cuando se pierde la conexión de una red y todos los servicios vuelven a estar en línea al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b818d-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="b818d-123">name</span><span class="sxs-lookup"><span data-stu-id="b818d-123">name</span></span>|<span data-ttu-id="b818d-124">Cadena que especifica el nombre de la configuración del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="b818d-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="b818d-125">El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="b818d-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b818d-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b818d-126">Child Elements</span></span>  
 <span data-ttu-id="b818d-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b818d-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b818d-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b818d-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b818d-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="b818d-129">Element</span></span>|<span data-ttu-id="b818d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="b818d-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b818d-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b818d-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b818d-132">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="b818d-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b818d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b818d-133">Example</span></span>  
 <span data-ttu-id="b818d-134">En el siguiente ejemplo se muestra un cliente que escucha mensajes de anuncios sobre http y peernet.</span><span class="sxs-lookup"><span data-stu-id="b818d-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b818d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b818d-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
