---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2e13fde338075d9ef16c205efcfcb452235f0af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="fe990-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="fe990-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="fe990-103">Este ejemplo muestra cómo insertar metadatos XML personalizados en los metadatos de detección para un punto de conexión detectable expuesto por un servicio.</span><span class="sxs-lookup"><span data-stu-id="fe990-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="fe990-104">A continuación, el ejemplo muestra el modo en que un cliente puede buscar el servicio y extraer estos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="fe990-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="fe990-105">Este ejemplo está compuesto de dos proyectos: servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="fe990-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="fe990-106">Servicio</span><span class="sxs-lookup"><span data-stu-id="fe990-106">Service</span></span>  
 <span data-ttu-id="fe990-107">En el método `main`, el ejemplo muestra que un objeto de tipo <xref:System.Xml.Linq.XElement> se rellena con los campos deseados y se agrega a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="fe990-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="fe990-108">Este <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se agrega a un extremo determinado.</span><span class="sxs-lookup"><span data-stu-id="fe990-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="fe990-109">Cuando se detecta ese extremo en particular, los metadatos de detección contienen los datos personalizados que se agregaron aquí.</span><span class="sxs-lookup"><span data-stu-id="fe990-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="fe990-110">Cliente</span><span class="sxs-lookup"><span data-stu-id="fe990-110">Client</span></span>  
 <span data-ttu-id="fe990-111">En el ejemplo se muestra el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> que se llama en un objeto <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="fe990-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="fe990-112">A continuación, se consultan los elementos XML adecuados y los esperados en el objeto <xref:System.ServiceModel.Discovery.FindResponse> resultante.</span><span class="sxs-lookup"><span data-stu-id="fe990-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="fe990-113">A continuación, estos elementos se imprimen en la consola.</span><span class="sxs-lookup"><span data-stu-id="fe990-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fe990-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe990-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="fe990-115">Cargue la solución de proyecto en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fe990-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="fe990-116">En primer lugar, ejecute la aplicación Servicio, generada en [directorio base de la solución]\service\bin\debug y, a continuación, ejecuta la aplicación Cliente, generada en [directorio base de la solución]\Client\bin\debug</span><span class="sxs-lookup"><span data-stu-id="fe990-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="fe990-117">Observe que el servicio está en línea, el cliente busca el servicio e imprime los metadatos publicados en el extremo.</span><span class="sxs-lookup"><span data-stu-id="fe990-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe990-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="fe990-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe990-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fe990-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe990-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe990-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe990-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="fe990-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="fe990-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe990-122">See Also</span></span>
