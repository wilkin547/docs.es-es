---
title: Recuperación de metadatos
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 48cac2b4b5a625546ab0c8ac9662fde01c7074b4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329679"
---
# <a name="retrieve-metadata"></a><span data-ttu-id="b0821-102">Recuperación de metadatos</span><span class="sxs-lookup"><span data-stu-id="b0821-102">Retrieve Metadata</span></span>
<span data-ttu-id="b0821-103">Este ejemplo muestra cómo implementar un cliente que dinámicamente recupere los metadatos de un servicio para elegir un punto de conexión con el que comunicarse.</span><span class="sxs-lookup"><span data-stu-id="b0821-103">This sample demonstrates how to implement a client that dynamically retrieves metadata from a service to choose an endpoint with which to communicate.</span></span> <span data-ttu-id="b0821-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b0821-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="b0821-105">El servicio se ha modificado para exponer dos puntos: un punto de conexión en la dirección base utilizando el `basicHttpBinding` enlace y un extremo seguro en {*baseaddress*} / usando el `wsHttpBinding` enlace.</span><span class="sxs-lookup"><span data-stu-id="b0821-105">The service has been modified to expose two endpoints—an endpoint at the base address using the `basicHttpBinding` binding, and a secure endpoint at {*baseaddress*}/secure using the `wsHttpBinding` binding.</span></span> <span data-ttu-id="b0821-106">En lugar de configurar el cliente con el extremo direcciones y enlaces, el cliente recupera dinámicamente los metadatos para el servicio utilizando la clase <xref:System.ServiceModel.Description.MetadataExchangeClient> y, a continuación, importa los metadatos como <xref:System.ServiceModel.Description.ServiceEndpointCollection> utilizando la clase <xref:System.ServiceModel.Description.WsdlImporter>.</span><span class="sxs-lookup"><span data-stu-id="b0821-106">Instead of configuring the client with the endpoint addresses and bindings, the client dynamically retrieves the metadata for the service using the <xref:System.ServiceModel.Description.MetadataExchangeClient> class and then imports the metadata as a <xref:System.ServiceModel.Description.ServiceEndpointCollection> using the <xref:System.ServiceModel.Description.WsdlImporter> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0821-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b0821-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b0821-108">La aplicación de cliente usa el <xref:System.ServiceModel.Description.ServiceEndpointCollection> importado para crear clientes para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b0821-108">The client application uses the imported <xref:System.ServiceModel.Description.ServiceEndpointCollection> to create clients to communicate with the service.</span></span> <span data-ttu-id="b0821-109">La aplicación cliente procesa una iteración a través de cada punto de conexión recuperado y se comunica con cada punto de conexión que implementa el contrato `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="b0821-109">The client application iterates through each retrieved endpoint and communicates with each endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="b0821-110">La dirección y el enlace adecuado se proporcionan con el extremo recuperado, para que el cliente se configure para comunicar con cada extremo, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0821-110">The appropriate address and binding are provided with the retrieved endpoint, so that the client is configured to communicate with each endpoint, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="b0821-111">La ventana de la consola del cliente muestra las operaciones enviadas a cada uno de los extremos, mostrando la ruta de acceso de la dirección y el nombre enlazando.</span><span class="sxs-lookup"><span data-stu-id="b0821-111">The client console window displays the operations sent to each of the endpoints, displaying the address path and binding name.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0821-112">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0821-112">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b0821-113">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0821-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b0821-114">Para compilar la edición de la solución de C#, C++ o Visual Basic. NET, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0821-114">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b0821-115">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0821-115">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0821-116">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b0821-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0821-117">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b0821-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b0821-118">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b0821-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0821-119">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b0821-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
