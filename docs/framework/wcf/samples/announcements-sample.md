---
title: Ejemplo de anuncios
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: c3824fb0dc7ab4169c309d1a5154127d6bc3b78f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747003"
---
# <a name="announcements-sample"></a>Ejemplo de anuncios

En este ejemplo se muestra cómo utilizar la funcionalidad de anuncio de la característica de detección. Los anuncios permiten a los servicios enviar mensajes de anuncio que contienen metadatos del servicio. De forma predeterminada, se envía un anuncio de saludo cuando el servicio se inicia y otro de despedida al cerrarse. Estos anuncios pueden ser de multidifusión o se pueden enviar de punto a punto. Este ejemplo está compuesto de dos proyectos: servicio y cliente.

## <a name="service"></a>Servicio

Este proyecto contiene un servicio de calculadora autohospedado. En el método `Main`, se crea un host de servicio y se le agrega un punto de conexión de servicio. Después, se crea un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. Para habilitar los anuncios, se debe agregar un extremo de anuncio a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>. En este caso, se agrega como punto de conexión del anuncio un punto de conexión estándar que usa multidifusión UDP. De esta forma se difunden los anuncios a través de una dirección UDP conocida.

```csharp
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);

     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();

     // Announce the availability of the service over UDP multicast
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());

    // Make the service discoverable over UDP multicast.
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());
    serviceHost.Open();
    // ...
}
```

## <a name="client"></a>Remoto

En este proyecto, observe que el cliente hospeda un <xref:System.ServiceModel.Discovery.AnnouncementService>. Además, se registran dos delegados con eventos. Estos eventos dictan lo que el cliente hace cuando se reciben anuncios en línea y sin conexión.

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

Los métodos `OnOnlineEvent` y `OnOfflineEvent` administran los mensajes de anuncio de saludo y despedida, respectivamente.

```csharp
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}
```

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Para obtener más información, consulte [configuración de http y https](../feature-details/configuring-http-and-https.md). Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas. Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Compile la solución.

3. Ejecute la aplicación client.exe.

4. Ejecute la aplicación service.exe. Observe que el cliente recibe un anuncio en línea.

5. Cierre la aplicación service.exe. Observe que el cliente recibe un anuncio sin conexión.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
