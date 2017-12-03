---
title: "Anuncios de detección y cliente de anuncio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6da9c2e251a6592bb0af039d552d02e7e4fd3fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="1ecad-102">Anuncios de detección y cliente de anuncio</span><span class="sxs-lookup"><span data-stu-id="1ecad-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="1ecad-103">La característica de detección de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite a los componentes anunciar su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1ecad-103">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="1ecad-104">Si se configura para ello, un servicio envía anuncios de hola y de adiós.</span><span class="sxs-lookup"><span data-stu-id="1ecad-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="1ecad-105">Clientes u otros componentes pueden realizar escuchas de dichos mensajes de anuncio y actuar de forma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1ecad-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="1ecad-106">Esto proporciona un método alternativo para que los clientes sean consciente de los servicios.</span><span class="sxs-lookup"><span data-stu-id="1ecad-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="1ecad-107">La funcionalidad de anuncios tiene varios usos. Por ejemplo, si los servicios acceden y dejan una red con frecuencia, los anuncios pueden ser una mejor alternativa que la búsqueda de servicios.</span><span class="sxs-lookup"><span data-stu-id="1ecad-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="1ecad-108">Con este enfoque, el tráfico de red se reduce y el cliente puede obtener información sobre la presencia o salida del servicio en cuanto se reciban los anuncios.</span><span class="sxs-lookup"><span data-stu-id="1ecad-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="1ecad-109">Anuncios de detección</span><span class="sxs-lookup"><span data-stu-id="1ecad-109">Discovery Announcements</span></span>  
 <span data-ttu-id="1ecad-110">Cuando un servicio configurado para anuncios se une a una red y se vuelve reconocible, envía un mensaje de Hola que anuncia su disponibilidad a los clientes que realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="1ecad-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="1ecad-111">El mensaje contiene información relacionada con la detección sobre el servicio, como el contrato, la dirección del extremo y los ámbitos asociados.</span><span class="sxs-lookup"><span data-stu-id="1ecad-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="1ecad-112">Puede especificar dónde se envía el mensaje de anuncio mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="1ecad-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="1ecad-113">Si el extremo del anuncio es una clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, el hola y el adiós se transmiten de forma adecuada o, si el extremo del anuncio es una unidifusión, los mensajes se envían directamente al extremo especificado.</span><span class="sxs-lookup"><span data-stu-id="1ecad-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ecad-114">Los anuncios se envían cuando el host de servicio se abre y se cierra.</span><span class="sxs-lookup"><span data-stu-id="1ecad-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="1ecad-115">Si estas llamadas no finalizan correctamente, no se puede mandar el mensaje del anuncio. Por ejemplo, si el servicio falla, no se envía el mensaje de anuncio de adiós.</span><span class="sxs-lookup"><span data-stu-id="1ecad-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="1ecad-116">Puede personalizar la funcionalidad del anuncio para enviar los anuncios cuando lo desee.</span><span class="sxs-lookup"><span data-stu-id="1ecad-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="1ecad-117"> define <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> como extremos estándar para permitir a los servicios y a los clientes enviar con facilidad anuncios de hola y de adiós.</span><span class="sxs-lookup"><span data-stu-id="1ecad-117"> defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="1ecad-118">Anuncios en el servicio</span><span class="sxs-lookup"><span data-stu-id="1ecad-118">Announcements on the Service</span></span>  
 <span data-ttu-id="1ecad-119">Para configurar el servicio para enviar anuncios, agregue una clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> con un extremo de anuncio.</span><span class="sxs-lookup"><span data-stu-id="1ecad-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="1ecad-120">En el siguiente ejemplo, se muestra cómo agregar este comportamiento al host de servicio mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1ecad-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="1ecad-121">Este ejemplo utiliza `UdpAnnouncementEndpoint`, que implica que los anuncios se envían a través de multidifusión a una ubicación especificada por ese extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="1ecad-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="1ecad-122">El comportamiento también se puede configurar en el archivo de configuración, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ecad-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="1ecad-123">Los ejemplos anteriores configuran un servicio para enviar mensajes de anuncio automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1ecad-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="1ecad-124">También puede enviar mensajes de anuncio explícitamente mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementClient>.</span><span class="sxs-lookup"><span data-stu-id="1ecad-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="1ecad-125">Anuncios en el cliente</span><span class="sxs-lookup"><span data-stu-id="1ecad-125">Announcements on the Client</span></span>  
 <span data-ttu-id="1ecad-126">Una aplicación cliente debe hospedar un servicio de anuncio para responder a los mensajes de hola y de adiós y suscribe a los eventos <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> y <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>.</span><span class="sxs-lookup"><span data-stu-id="1ecad-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="1ecad-127">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1ecad-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="1ecad-128">Cuando se recibe un mensaje de hola o de adiós, puede acceder a los metadatos de detección de extremos a través de <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ecad-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
