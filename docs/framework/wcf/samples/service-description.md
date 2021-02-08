---
description: 'Más información acerca de: Descripción del servicio'
title: Descripción del servicio
ms.date: 03/30/2017
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
ms.openlocfilehash: 0985933bb48708faac716575f6a95588df1620d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793095"
---
# <a name="service-description"></a><span data-ttu-id="b25c4-103">Descripción del servicio</span><span class="sxs-lookup"><span data-stu-id="b25c4-103">Service Description</span></span>

<span data-ttu-id="b25c4-104">El ejemplo Descripción del servicio muestra cómo un servicio puede recuperar su información de descripción de servicio en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b25c4-104">The Service Description sample demonstrates how a service can retrieve its service description information at runtime.</span></span> <span data-ttu-id="b25c4-105">El ejemplo se basa en el [Introducción](getting-started-sample.md), con una operación de servicio adicional definida para devolver información descriptiva sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-105">The sample is based on the [Getting Started](getting-started-sample.md), with an additional service operation defined to return descriptive information about the service.</span></span> <span data-ttu-id="b25c4-106">La información que se devuelve muestra las direcciones base y puntos de conexión para el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-106">The information that is returned lists the base addresses and endpoints for the service.</span></span> <span data-ttu-id="b25c4-107">El servicio proporciona esta información mediante las clases <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> y <xref:System.ServiceModel.Description.ServiceDescription>.</span><span class="sxs-lookup"><span data-stu-id="b25c4-107">The service provides this information using the <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost>, and <xref:System.ServiceModel.Description.ServiceDescription> classes.</span></span>  
  
 <span data-ttu-id="b25c4-108">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b25c4-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b25c4-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b25c4-110">Este ejemplo tiene una versión modificada del contrato de la calculadora llamado `IServiceDescriptionCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b25c4-110">This sample has a modified version of the calculator contract called `IServiceDescriptionCalculator`.</span></span> <span data-ttu-id="b25c4-111">El contrato define una operación de servicio adicional denominada `GetServiceDescriptionInfo` que devuelve una cadena de varias líneas al cliente que describe la dirección o direcciones base, así como el extremo o extremos para el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-111">The contract defines an additional service operation named `GetServiceDescriptionInfo` that returns a multi-line string to the client that describes the base address or addresses and service endpoint or endpoints for the service.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 <span data-ttu-id="b25c4-112">El código de implementación para `GetServiceDescriptionInfo` utiliza <xref:System.ServiceModel.Description.ServiceDescription> para enumerar los puntos de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-112">The implementation code for `GetServiceDescriptionInfo` uses the <xref:System.ServiceModel.Description.ServiceDescription> to list the service endpoints.</span></span> <span data-ttu-id="b25c4-113">Dado que los puntos de conexión de servicio pueden tener direcciones relativas, muestra primero una lista de direcciones base para el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-113">Because service endpoints can have relative addresses, it first lists the base addresses for the service.</span></span> <span data-ttu-id="b25c4-114">Para obtener toda esta información, el código obtiene su contexto de operación mediante <xref:System.ServiceModel.OperationContext.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="b25c4-114">To get all of this information, the code obtains its operation context using <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="b25c4-115"><xref:System.ServiceModel.ServiceHost> y su objeto <xref:System.ServiceModel.Description.ServiceDescription> se recupera del contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="b25c4-115">The <xref:System.ServiceModel.ServiceHost> and its <xref:System.ServiceModel.Description.ServiceDescription> object are retrieved from the operation context.</span></span> <span data-ttu-id="b25c4-116">Para hacer una lista de los puntos de conexión base para el servicio, el código recorre en iteración la colección <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> del host del servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-116">To list the base endpoints for the service, the code iterates through the service host's <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> collection.</span></span> <span data-ttu-id="b25c4-117">Para hacer una lista de los extremos de servicio para el servicio, el código recorre en iteración la colección de extremos de la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-117">To list the service endpoints for the service, the code iterates through the service description's endpoints collection.</span></span>  
  
```csharp
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 <span data-ttu-id="b25c4-118">Al ejecutar el ejemplo, se ven las operaciones de la calculadora y después la información del servicio devuelta por la operación `GetServiceDescriptionInfo`.</span><span class="sxs-lookup"><span data-stu-id="b25c4-118">When you run the sample, you see the calculator operations and then the service information returned by the `GetServiceDescriptionInfo` operation.</span></span> <span data-ttu-id="b25c4-119">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b25c4-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b25c4-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b25c4-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b25c4-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b25c4-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b25c4-122">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b25c4-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b25c4-123">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b25c4-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b25c4-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b25c4-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b25c4-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b25c4-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b25c4-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b25c4-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b25c4-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b25c4-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
