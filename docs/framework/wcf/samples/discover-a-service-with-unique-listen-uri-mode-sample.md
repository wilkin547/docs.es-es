---
title: "Ejemplo de detección de un servicio con un modo de URI de escucha único"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48b49def3f8f009eeb4ffa0204e9c616b5acfec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="8930b-102">Ejemplo de detección de un servicio con un modo de URI de escucha único</span><span class="sxs-lookup"><span data-stu-id="8930b-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="8930b-103">En este ejemplo se muestra cómo detectar un servicio que tiene la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span><span class="sxs-lookup"><span data-stu-id="8930b-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="8930b-104">Cuando la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>, se asegura de que ListenUri es único estableciendo el puerto para que sea único o para que la ruta de acceso sea único anexando un GUID.</span><span class="sxs-lookup"><span data-stu-id="8930b-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="8930b-105">Características en el servicio</span><span class="sxs-lookup"><span data-stu-id="8930b-105">Features on the Service</span></span>  
 <span data-ttu-id="8930b-106">La propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> se establece en <xref:System.ServiceModel.Description.ListenUriMode.Unique> para el extremo TCP.</span><span class="sxs-lookup"><span data-stu-id="8930b-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="8930b-107">A continuación, el servicio se puede detectar a través de un extremo de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="8930b-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="8930b-108">Características en el cliente</span><span class="sxs-lookup"><span data-stu-id="8930b-108">Features on the Client</span></span>  
 <span data-ttu-id="8930b-109">Este cliente se conecta al servicio utilizando el `Via.Uri` correcto con el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.</span><span class="sxs-lookup"><span data-stu-id="8930b-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="8930b-110">A continuación, el objeto <xref:System.ServiceModel.Discovery.FindResponse> que devuelve el método se consulta para comprobar si contiene una propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> válida y si es diferente de `Address.Uri`.</span><span class="sxs-lookup"><span data-stu-id="8930b-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="8930b-111">A continuación, la información adecuada se pasa al método `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="8930b-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="8930b-112">En el método `InvokeCalculatorService`, el llamador pasa la propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> y un `ClientViaBehavior` con el `Via.Uri` correcto se agrega al extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="8930b-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="8930b-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="8930b-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="8930b-114">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra UniqueListenUriMode.sln.</span><span class="sxs-lookup"><span data-stu-id="8930b-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="8930b-115">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="8930b-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="8930b-116">Ejecute la aplicación de servicio, que se genera en la carpeta [directorio base de la solución]\service\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="8930b-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="8930b-117">Ejecute la aplicación cliente, que se genera en la carpeta [directorio base de la solución]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="8930b-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="8930b-118">El cliente busca el servicio en ejecución y escribe en la consola los metadatos publicados por el extremo del servicio.</span><span class="sxs-lookup"><span data-stu-id="8930b-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8930b-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8930b-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8930b-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8930b-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8930b-121">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8930b-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8930b-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8930b-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="8930b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8930b-123">See Also</span></span>
