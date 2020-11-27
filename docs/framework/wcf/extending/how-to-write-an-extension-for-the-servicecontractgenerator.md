---
title: Procedimiento para escribir una extensión para ServiceContractGenerator
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: 3a81204ca470b9b94d9e8f048ecccbade74b2e10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254641"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="96727-102">Procedimiento para escribir una extensión para ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="96727-102">How to: Write an Extension for the ServiceContractGenerator</span></span>

<span data-ttu-id="96727-103">En este tema se describe cómo escribir una extensión para <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span><span class="sxs-lookup"><span data-stu-id="96727-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="96727-104">Esto se puede hacer implementando la interfaz <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> en un comportamiento de la operación o implementando la interfaz <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> en un comportamiento del contrato.</span><span class="sxs-lookup"><span data-stu-id="96727-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="96727-105">En este tema se muestra cómo implementar la interfaz <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> en un comportamiento de contrato.</span><span class="sxs-lookup"><span data-stu-id="96727-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="96727-106"><xref:System.ServiceModel.Description.ServiceContractGenerator> genera contratos de servicio, tipos de cliente y configuraciones de cliente a partir de instancias de <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> y <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="96727-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="96727-107">Normalmente, importa <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, y <xref:System.ServiceModel.Channels.Binding> crea instancias a partir de los metadatos del servicio y, a continuación, utiliza estas instancias para generar el código para llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="96727-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="96727-108">En este ejemplo, se usa una implementación <xref:System.ServiceModel.Description.IWsdlImportExtension> para procesar las anotaciones WSDL y después agregar las extensiones de generación de código a los contratos importados para generar comentarios en el código generado.</span><span class="sxs-lookup"><span data-stu-id="96727-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="96727-109">Escribir una extensión para ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="96727-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1. <span data-ttu-id="96727-110">Implemente <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="96727-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="96727-111">Para modificar el contrato de servicio generado, use la instancia <xref:System.ServiceModel.Description.ServiceContractGenerationContext> pasada al método <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="96727-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```csharp
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
        context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2. <span data-ttu-id="96727-112">Implemente <xref:System.ServiceModel.Description.IWsdlImportExtension> en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="96727-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="96727-113">El método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> puede procesar una extensión WSDL concreta (anotaciones WSDL en este caso) agregando una extensión de generación de código a la instancia <xref:System.ServiceModel.Description.ContractDescription> importada.</span><span class="sxs-lookup"><span data-stu-id="96727-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```csharp
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)
    {
        // Contract documentation
        if (context.WsdlPortType.Documentation != null)
        {
            context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));
        }
        // Operation documentation
        foreach (Operation operation in context.WsdlPortType.Operations)
        {
            if (operation.Documentation != null)
            {
                OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);
                if (operationDescription != null)
                {
                    operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));
                }
            }
        }
    }
    public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)
    {
        Console.WriteLine("BeforeImport called.");
    }

    public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)
    {
        Console.WriteLine("ImportEndpoint called.");
    }
    ```  
  
3. <span data-ttu-id="96727-114">Agregue el importador de WSDL a su configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="96727-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4. <span data-ttu-id="96727-115">En el código de cliente, cree un `MetadataExchangeClient` y llame a `GetMetadata`:</span><span class="sxs-lookup"><span data-stu-id="96727-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```csharp
    var mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5. <span data-ttu-id="96727-116">Cree un `WsdlImporter` y llame a `ImportAllContracts`:</span><span class="sxs-lookup"><span data-stu-id="96727-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```csharp
    var importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6. <span data-ttu-id="96727-117">Cree un `ServiceContractGenerator` y llame a `GenerateServiceContractType` para cada contrato.</span><span class="sxs-lookup"><span data-stu-id="96727-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```csharp
    var generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7. <span data-ttu-id="96727-118">Se llama a <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> automáticamente para cada comportamiento del contrato en un contrato determinado que implementa <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="96727-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="96727-119">Este método puede modificar el <xref:System.ServiceModel.Description.ServiceContractGenerationContext> pasado.</span><span class="sxs-lookup"><span data-stu-id="96727-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="96727-120">En este ejemplo se agregan comentarios.</span><span class="sxs-lookup"><span data-stu-id="96727-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96727-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="96727-121">See also</span></span>

- [<span data-ttu-id="96727-122">Metadata</span><span class="sxs-lookup"><span data-stu-id="96727-122">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="96727-123">Procedimiento para importar el WSDL personalizado</span><span class="sxs-lookup"><span data-stu-id="96727-123">How to: Import Custom WSDL</span></span>](how-to-import-custom-wsdl.md)
