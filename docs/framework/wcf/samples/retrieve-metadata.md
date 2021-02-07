---
description: Más información acerca de cómo recuperar metadatos
title: Recuperación de metadatos
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 819683452630e6750d839c9922538a6056e2556e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703814"
---
# <a name="retrieve-metadata"></a><span data-ttu-id="9cda6-103">Recuperación de metadatos</span><span class="sxs-lookup"><span data-stu-id="9cda6-103">Retrieve Metadata</span></span>

<span data-ttu-id="9cda6-104">Este ejemplo muestra cómo implementar un cliente que dinámicamente recupere los metadatos de un servicio para elegir un punto de conexión con el que comunicarse.</span><span class="sxs-lookup"><span data-stu-id="9cda6-104">This sample demonstrates how to implement a client that dynamically retrieves metadata from a service to choose an endpoint with which to communicate.</span></span> <span data-ttu-id="9cda6-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9cda6-105">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="9cda6-106">El servicio se ha modificado para exponer dos puntos de conexión: un punto de conexión en la dirección base utilizando el `basicHttpBinding` enlace y un punto de conexión seguro en {*BaseAddress*}/Secure utilizando el `wsHttpBinding` enlace.</span><span class="sxs-lookup"><span data-stu-id="9cda6-106">The service has been modified to expose two endpoints—an endpoint at the base address using the `basicHttpBinding` binding, and a secure endpoint at {*baseaddress*}/secure using the `wsHttpBinding` binding.</span></span> <span data-ttu-id="9cda6-107">En lugar de configurar el cliente con el extremo direcciones y enlaces, el cliente recupera dinámicamente los metadatos para el servicio utilizando la clase <xref:System.ServiceModel.Description.MetadataExchangeClient> y, a continuación, importa los metadatos como <xref:System.ServiceModel.Description.ServiceEndpointCollection> utilizando la clase <xref:System.ServiceModel.Description.WsdlImporter>.</span><span class="sxs-lookup"><span data-stu-id="9cda6-107">Instead of configuring the client with the endpoint addresses and bindings, the client dynamically retrieves the metadata for the service using the <xref:System.ServiceModel.Description.MetadataExchangeClient> class and then imports the metadata as a <xref:System.ServiceModel.Description.ServiceEndpointCollection> using the <xref:System.ServiceModel.Description.WsdlImporter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cda6-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9cda6-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9cda6-109">La aplicación de cliente usa el <xref:System.ServiceModel.Description.ServiceEndpointCollection> importado para crear clientes para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="9cda6-109">The client application uses the imported <xref:System.ServiceModel.Description.ServiceEndpointCollection> to create clients to communicate with the service.</span></span> <span data-ttu-id="9cda6-110">La aplicación cliente procesa una iteración a través de cada punto de conexión recuperado y se comunica con cada punto de conexión que implementa el contrato `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="9cda6-110">The client application iterates through each retrieved endpoint and communicates with each endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="9cda6-111">La dirección y el enlace adecuado se proporcionan con el extremo recuperado, para que el cliente se configure para comunicar con cada extremo, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="9cda6-111">The appropriate address and binding are provided with the retrieved endpoint, so that the client is configured to communicate with each endpoint, as shown in the following sample code.</span></span>  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 <span data-ttu-id="9cda6-112">La ventana de la consola del cliente muestra las operaciones enviadas a cada uno de los extremos, mostrando la ruta de acceso de la dirección y el nombre enlazando.</span><span class="sxs-lookup"><span data-stu-id="9cda6-112">The client console window displays the operations sent to each of the endpoints, displaying the address path and binding name.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9cda6-113">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cda6-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9cda6-114">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9cda6-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9cda6-115">Para compilar la edición de C#, C++ o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9cda6-115">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9cda6-116">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9cda6-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9cda6-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9cda6-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9cda6-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9cda6-118">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="9cda6-119">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9cda6-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9cda6-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9cda6-120">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
