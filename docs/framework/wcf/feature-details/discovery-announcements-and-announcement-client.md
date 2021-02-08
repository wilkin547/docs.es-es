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
# <a name="discovery-announcements-and-announcement-client"></a>Anuncios de detección y cliente de anuncio

La característica de detección de WCF permite a los componentes anunciar su disponibilidad. Si se configura para ello, un servicio envía anuncios de hola y de adiós. Clientes u otros componentes pueden realizar escuchas de dichos mensajes de anuncio y actuar de forma correspondiente. Esto proporciona un método alternativo para que los clientes sean consciente de los servicios. La funcionalidad de anuncios tiene varios usos. Por ejemplo, si los servicios acceden y dejan una red con frecuencia, los anuncios pueden ser una mejor alternativa que la búsqueda de servicios. Con este enfoque, el tráfico de red se reduce y el cliente puede obtener información sobre la presencia o salida del servicio en cuanto se reciban los anuncios.

## <a name="discovery-announcements"></a>Anuncios de detección

Cuando un servicio configurado para anuncios se une a una red y se vuelve reconocible, envía un mensaje de Hola que anuncia su disponibilidad a los clientes que realizan escuchas. El mensaje contiene información relacionada con la detección sobre el servicio, como el contrato, la dirección del punto de conexión y los ámbitos asociados. Puede especificar dónde se envía el mensaje de anuncio mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>. Si el punto de conexión del anuncio es una clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, el hola y el adiós se transmiten de forma adecuada o, si el punto de conexión del anuncio es una unidifusión, los mensajes se envían directamente al punto de conexión especificado.

> [!NOTE]
> Los anuncios se envían cuando el host de servicio se abre y se cierra. Si estas llamadas no finalizan correctamente, es posible que no se envíe el mensaje de anuncio. Por ejemplo, si se produce un error en el servicio, no se envía el mensaje de anuncio adiós.

> [!TIP]
> Puede personalizar la funcionalidad del anuncio para enviar los anuncios cuando lo desee.

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] define <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> y <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> como extremos estándar para permitir a los servicios y a los clientes enviar con facilidad anuncios de hola y de adiós.

### <a name="announcements-on-the-service"></a>Anuncios en el servicio

Para configurar el servicio para enviar anuncios, agregue una clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> con un punto de conexión de anuncio. En el siguiente ejemplo, se muestra cómo agregar este comportamiento al host de servicio mediante programación. Este ejemplo utiliza `UdpAnnouncementEndpoint`, que implica que los anuncios se envían a través de multidifusión a una ubicación especificada por ese extremo estándar.

```csharp
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```

El comportamiento también se puede configurar en el archivo de configuración, tal y como se muestra en el siguiente ejemplo.

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

Los ejemplos anteriores configuran un servicio para enviar mensajes de anuncio automáticamente. También puede enviar mensajes de anuncio explícitamente mediante la clase <xref:System.ServiceModel.Discovery.AnnouncementClient>.

### <a name="announcements-on-the-client"></a>Anuncios en el cliente

Una aplicación cliente debe hospedar un servicio de anuncio para responder a los mensajes de hola y de adiós y suscribe a los eventos <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> y <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived>. El ejemplo siguiente muestra cómo hacerlo.

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

Cuando se recibe un mensaje de hola o de adiós, puede acceder a los metadatos de detección de extremos a través de <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>, tal y como se muestra en el siguiente ejemplo.

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
