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
# <a name="announcements-sample"></a><span data-ttu-id="7e1df-102">Ejemplo de anuncios</span><span class="sxs-lookup"><span data-stu-id="7e1df-102">Announcements Sample</span></span>

<span data-ttu-id="7e1df-103">En este ejemplo se muestra cómo utilizar la funcionalidad de anuncio de la característica de detección.</span><span class="sxs-lookup"><span data-stu-id="7e1df-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="7e1df-104">Los anuncios permiten a los servicios enviar mensajes de anuncio que contienen metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="7e1df-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="7e1df-105">De forma predeterminada, se envía un anuncio de saludo cuando el servicio se inicia y otro de despedida al cerrarse.</span><span class="sxs-lookup"><span data-stu-id="7e1df-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="7e1df-106">Estos anuncios pueden ser de multidifusión o se pueden enviar de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="7e1df-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="7e1df-107">Este ejemplo está compuesto de dos proyectos: servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="7e1df-107">This sample consists of two projects service and client.</span></span>

## <a name="service"></a><span data-ttu-id="7e1df-108">Servicio</span><span class="sxs-lookup"><span data-stu-id="7e1df-108">Service</span></span>

<span data-ttu-id="7e1df-109">Este proyecto contiene un servicio de calculadora autohospedado.</span><span class="sxs-lookup"><span data-stu-id="7e1df-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="7e1df-110">En el método `Main`, se crea un host de servicio y se le agrega un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="7e1df-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="7e1df-111">Después, se crea un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="7e1df-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="7e1df-112">Para habilitar los anuncios, se debe agregar un extremo de anuncio a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="7e1df-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="7e1df-113">En este caso, se agrega como punto de conexión del anuncio un punto de conexión estándar que usa multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="7e1df-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="7e1df-114">De esta forma se difunden los anuncios a través de una dirección UDP conocida.</span><span class="sxs-lookup"><span data-stu-id="7e1df-114">This broadcasts the announcements over a well-known UDP address.</span></span>

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

## <a name="client"></a><span data-ttu-id="7e1df-115">Client</span><span class="sxs-lookup"><span data-stu-id="7e1df-115">Client</span></span>

<span data-ttu-id="7e1df-116">En este proyecto, observe que el cliente hospeda un <xref:System.ServiceModel.Discovery.AnnouncementService>.</span><span class="sxs-lookup"><span data-stu-id="7e1df-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="7e1df-117">Además, se registran dos delegados con eventos.</span><span class="sxs-lookup"><span data-stu-id="7e1df-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="7e1df-118">Estos eventos dictan lo que el cliente hace cuando se reciben anuncios en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="7e1df-118">These events dictate what the client does when online and offline announcements are received.</span></span>

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

<span data-ttu-id="7e1df-119">Los métodos `OnOnlineEvent` y `OnOfflineEvent` administran los mensajes de anuncio de saludo y despedida, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="7e1df-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>

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

#### <a name="to-use-this-sample"></a><span data-ttu-id="7e1df-120">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e1df-120">To use this sample</span></span>

1. <span data-ttu-id="7e1df-121">Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="7e1df-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="7e1df-122">Para obtener más información, consulte [configuración de http y https](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="7e1df-122">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="7e1df-123">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7e1df-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="7e1df-124">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="7e1df-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="7e1df-125">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="7e1df-125">Build the solution.</span></span>

3. <span data-ttu-id="7e1df-126">Ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="7e1df-126">Run the client.exe application.</span></span>

4. <span data-ttu-id="7e1df-127">Ejecute la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="7e1df-127">Run the service.exe application.</span></span> <span data-ttu-id="7e1df-128">Observe que el cliente recibe un anuncio en línea.</span><span class="sxs-lookup"><span data-stu-id="7e1df-128">Note the client receives an online announcement.</span></span>

5. <span data-ttu-id="7e1df-129">Cierre la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="7e1df-129">Close the service.exe application.</span></span> <span data-ttu-id="7e1df-130">Observe que el cliente recibe un anuncio sin conexión.</span><span class="sxs-lookup"><span data-stu-id="7e1df-130">Note the client receives an offline announcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e1df-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7e1df-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7e1df-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7e1df-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="7e1df-133">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e1df-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e1df-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7e1df-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
