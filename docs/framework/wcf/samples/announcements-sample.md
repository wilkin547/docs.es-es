---
title: Ejemplo de anuncios
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 045807df433d519b00969812afb0ae2feac94b75
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="announcements-sample"></a><span data-ttu-id="5ad93-102">Ejemplo de anuncios</span><span class="sxs-lookup"><span data-stu-id="5ad93-102">Announcements Sample</span></span>
<span data-ttu-id="5ad93-103">En este ejemplo se muestra cómo utilizar la funcionalidad de anuncio de la característica de detección.</span><span class="sxs-lookup"><span data-stu-id="5ad93-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="5ad93-104">Los anuncios permiten a los servicios enviar mensajes de anuncio que contienen metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="5ad93-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="5ad93-105">De forma predeterminada, se envía un anuncio de saludo cuando el servicio se inicia y otro de despedida al cerrarse.</span><span class="sxs-lookup"><span data-stu-id="5ad93-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="5ad93-106">Estos anuncios pueden ser de multidifusión o se pueden enviar de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="5ad93-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="5ad93-107">Este ejemplo está compuesto de dos proyectos: servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="5ad93-107">This sample consists of two projects service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="5ad93-108">Servicio</span><span class="sxs-lookup"><span data-stu-id="5ad93-108">Service</span></span>  
 <span data-ttu-id="5ad93-109">Este proyecto contiene un servicio de calculadora autohospedado.</span><span class="sxs-lookup"><span data-stu-id="5ad93-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="5ad93-110">En el método `Main`, se crea un host de servicio y se le agrega un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="5ad93-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="5ad93-111">Después, se crea un <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5ad93-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="5ad93-112">Para habilitar los anuncios, se debe agregar un extremo de anuncio a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5ad93-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="5ad93-113">En este caso, se agrega como extremo del anuncio un extremo estándar que usa multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="5ad93-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="5ad93-114">De esta forma se difunden los anuncios a través de una dirección UDP conocida.</span><span class="sxs-lookup"><span data-stu-id="5ad93-114">This broadcasts the announcements over a well-known UDP address.</span></span>  
  
```  
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
  
## <a name="client"></a><span data-ttu-id="5ad93-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="5ad93-115">Client</span></span>  
 <span data-ttu-id="5ad93-116">En este proyecto, observe que el cliente hospeda un <xref:System.ServiceModel.Discovery.AnnouncementService>.</span><span class="sxs-lookup"><span data-stu-id="5ad93-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="5ad93-117">Además, se registran dos delegados con eventos.</span><span class="sxs-lookup"><span data-stu-id="5ad93-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="5ad93-118">Estos eventos dictan lo que el cliente hace cuando se reciben anuncios en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="5ad93-118">These events dictate what the client does when online and offline announcements are received.</span></span>  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 <span data-ttu-id="5ad93-119">Los métodos `OnOnlineEvent` y `OnOfflineEvent` administran los mensajes de anuncio de saludo y despedida, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5ad93-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>  
  
```  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5ad93-120">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ad93-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="5ad93-121">Este ejemplo utiliza los extremos HTTP y para ejecutar este ejemplo, correcto ACL de dirección URL debe agregarse vea [configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5ad93-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="5ad93-122">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="5ad93-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="5ad93-123">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="5ad93-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  <span data-ttu-id="5ad93-124">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="5ad93-124">Build the solution.</span></span>  
  
3.  <span data-ttu-id="5ad93-125">Ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="5ad93-125">Run the client.exe application.</span></span>  
  
4.  <span data-ttu-id="5ad93-126">Ejecute la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="5ad93-126">Run the service.exe application.</span></span> <span data-ttu-id="5ad93-127">Observe que el cliente recibe un anuncio en línea.</span><span class="sxs-lookup"><span data-stu-id="5ad93-127">Note the client receives an online announcement.</span></span>  
  
5.  <span data-ttu-id="5ad93-128">Cierre la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="5ad93-128">Close the service.exe application.</span></span> <span data-ttu-id="5ad93-129">Observe que el cliente recibe un anuncio sin conexión.</span><span class="sxs-lookup"><span data-stu-id="5ad93-129">Note the client receives an offline announcement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ad93-130">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5ad93-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5ad93-131">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5ad93-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5ad93-132">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ad93-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5ad93-133">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5ad93-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## <a name="see-also"></a><span data-ttu-id="5ad93-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ad93-134">See Also</span></span>
