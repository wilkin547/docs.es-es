---
title: Ejemplo de detección de un servicio con un modo de URI de escucha único
ms.date: 03/30/2017
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
ms.openlocfilehash: 7e1c5ae0cb1a44c72a27566035b4bc20acbf1614
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077049"
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="60c2a-102">Ejemplo de detección de un servicio con un modo de URI de escucha único</span><span class="sxs-lookup"><span data-stu-id="60c2a-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="60c2a-103">En este ejemplo se muestra cómo detectar un servicio que tiene la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span><span class="sxs-lookup"><span data-stu-id="60c2a-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="60c2a-104">Cuando la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>, se asegura de que ListenUri es único estableciendo el puerto para que sea único o para que la ruta de acceso sea único anexando un GUID.</span><span class="sxs-lookup"><span data-stu-id="60c2a-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="60c2a-105">Características en el servicio</span><span class="sxs-lookup"><span data-stu-id="60c2a-105">Features on the Service</span></span>  
 <span data-ttu-id="60c2a-106">La propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> se establece en <xref:System.ServiceModel.Description.ListenUriMode.Unique> para el extremo TCP.</span><span class="sxs-lookup"><span data-stu-id="60c2a-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="60c2a-107">A continuación, el servicio se puede detectar a través de un extremo de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="60c2a-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="60c2a-108">Características en el cliente</span><span class="sxs-lookup"><span data-stu-id="60c2a-108">Features on the Client</span></span>  
 <span data-ttu-id="60c2a-109">Este cliente se conecta al servicio utilizando el `Via.Uri` correcto con el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.</span><span class="sxs-lookup"><span data-stu-id="60c2a-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="60c2a-110">A continuación, el objeto <xref:System.ServiceModel.Discovery.FindResponse> que devuelve el método se consulta para comprobar si contiene una propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> válida y si es diferente de `Address.Uri`.</span><span class="sxs-lookup"><span data-stu-id="60c2a-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="60c2a-111">A continuación, la información adecuada se pasa al método `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="60c2a-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="60c2a-112">En el método `InvokeCalculatorService`, el llamador pasa la propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> y un `ClientViaBehavior` con el `Via.Uri` correcto se agrega al extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2a-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="60c2a-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="60c2a-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="60c2a-114">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra UniqueListenUriMode.sln.</span><span class="sxs-lookup"><span data-stu-id="60c2a-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="60c2a-115">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="60c2a-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="60c2a-116">Ejecute la aplicación de servicio, que se genera en la carpeta [directorio base de la solución]\service\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="60c2a-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="60c2a-117">Ejecute la aplicación cliente, que se genera en la carpeta [directorio base de la solución]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="60c2a-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="60c2a-118">El cliente busca el servicio en ejecución y escribe en la consola los metadatos publicados por el extremo del servicio.</span><span class="sxs-lookup"><span data-stu-id="60c2a-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60c2a-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="60c2a-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="60c2a-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="60c2a-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="60c2a-121">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="60c2a-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="60c2a-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="60c2a-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="60c2a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="60c2a-123">See Also</span></span>
