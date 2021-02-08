---
description: 'Más información sobre: anuncios de detección y cliente de anuncio'
title: Anuncios de detección y cliente de anuncio
ms.date: 03/30/2017
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
ms.openlocfilehash: 2076b4dbdc57bd3de47fccdb4a51ef9e6fc48366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802975"
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="01de7-103">Anuncios de detección y cliente de anuncio</span><span class="sxs-lookup"><span data-stu-id="01de7-103">Discovery Announcements and Announcement Client</span></span>

<span data-ttu-id="01de7-104">La característica de detección de WCF permite a los componentes anunciar su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="01de7-104">The WCF discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="01de7-105">Si se configura para ello, un servicio envía anuncios de hola y de adiós.</span><span class="sxs-lookup"><span data-stu-id="01de7-105">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="01de7-106">Clientes u otros componentes pueden realizar escuchas de dichos mensajes de anuncio y actuar de forma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="01de7-106">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="01de7-107">Esto proporciona un método alternativo para que los clientes sean consciente de los servicios.</span><span class="sxs-lookup"><span data-stu-id="01de7-107">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="01de7-108">La funcionalidad de anuncios tiene varios usos. Por ejemplo, si los servicios acceden y dejan una red con frecuencia, los anuncios pueden ser una mejor alternativa que la búsqueda de servicios.</span><span class="sxs-lookup"><span data-stu-id="01de7-108">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="01de7-109">Con este enfoque, el tráfico de red se reduce y el cliente puede obtener información sobre la presencia o salida del servicio en cuanto se reciban los anuncios.</span><span class="sxs-lookup"><span data-stu-id="01de7-109">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>

## <a name="discovery-announcements"></a><span data-ttu-id="01de7-110">Anuncios de detección</span><span class="sxs-lookup"><span data-stu-id="01de7-110">Discovery Announcements</span></span>

<span data-ttu-id="01de7-111">Cuando un servicio configurado para anuncios se une a una red y se vuelve reconocible, envía un mensaje de Hola que anuncia su disponibilidad a los clientes que realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="01de7-111">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="01de7-112">El mensaje contiene información relacionada con la detección sobre el servicio, como el contrato, la dirección del punto de conexión y los ámbitos asociados.</span><span class="sxs-lookup"><span data-stu-id="01de7-112">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="01de7-113">Puede especificar dónde se envía el mensaje de anuncio mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="01de7-113">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="01de7-114">Si el punto de conexión del anuncio es una clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, el hola y el adiós se transmiten de forma adecuada o, si el punto de conexión del anuncio es una unidifusión, los mensajes se envían directamente al punto de conexión especificado.</span><span class="sxs-lookup"><span data-stu-id="01de7-114">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="01de7-115">Los anuncios se envían cuando el host de servicio se abre y se cierra.</span><span class="sxs-lookup"><span data-stu-id="01de7-115">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="01de7-116">Si estas llamadas no finalizan correctamente, es posible que no se envíe el mensaje de anuncio. Por ejemplo, si se produce un error en el servicio, no se envía el mensaje de anuncio adiós.</span><span class="sxs-lookup"><span data-stu-id="01de7-116">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>

> [!TIP]
> <span data-ttu-id="01de7-117">Puede personalizar la funcionalidad del anuncio para enviar los anuncios cuando lo desee.</span><span class="sxs-lookup"><span data-stu-id="01de7-117">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="01de7-118">define <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> como extremos estándar para permitir a los servicios y a los clientes enviar con facilidad anuncios de hola y de adiós.</span><span class="sxs-lookup"><span data-stu-id="01de7-118">defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>

### <a name="announcements-on-the-service"></a><span data-ttu-id="01de7-119">Anuncios en el servicio</span><span class="sxs-lookup"><span data-stu-id="01de7-119">Announcements on the Service</span></span>

<span data-ttu-id="01de7-120">Para configurar el servicio para enviar anuncios, agregue una clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> con un punto de conexión de anuncio.</span><span class="sxs-lookup"><span data-stu-id="01de7-120">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="01de7-121">En el siguiente ejemplo, se muestra cómo agregar este comportamiento al host de servicio mediante programación.</span><span class="sxs-lookup"><span data-stu-id="01de7-121">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="01de7-122">Este ejemplo utiliza `UdpAnnouncementEndpoint`, que implica que los anuncios se envían a través de multidifusión a una ubicación especificada por ese extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="01de7-122">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>

```csharp
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```

<span data-ttu-id="01de7-123">El comportamiento también se puede configurar en el archivo de configuración, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="01de7-123">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>

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

<span data-ttu-id="01de7-124">Los ejemplos anteriores configuran un servicio para enviar mensajes de anuncio automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01de7-124">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="01de7-125">También puede enviar mensajes de anuncio explícitamente mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementClient>.</span><span class="sxs-lookup"><span data-stu-id="01de7-125">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>

### <a name="announcements-on-the-client"></a><span data-ttu-id="01de7-126">Anuncios en el cliente</span><span class="sxs-lookup"><span data-stu-id="01de7-126">Announcements on the Client</span></span>

<span data-ttu-id="01de7-127">Una aplicación cliente debe hospedar un servicio de anuncio para responder a los mensajes de hola y de adiós y suscribe a los eventos <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> y <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>.</span><span class="sxs-lookup"><span data-stu-id="01de7-127">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="01de7-128">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="01de7-128">The following example shows how to do this.</span></span>

```csharp
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

<span data-ttu-id="01de7-129">Cuando se recibe un mensaje de hola o de adiós, puede acceder a los metadatos de detección de extremos a través de <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="01de7-129">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>

```csharp
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
