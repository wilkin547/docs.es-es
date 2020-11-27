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
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a>Procedimiento para escribir una extensión para ServiceContractGenerator

En este tema se describe cómo escribir una extensión para <xref:System.ServiceModel.Description.ServiceContractGenerator>. Esto se puede hacer implementando la interfaz <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> en un comportamiento de la operación o implementando la interfaz <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> en un comportamiento del contrato. En este tema se muestra cómo implementar la interfaz <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> en un comportamiento de contrato.  
  
 <xref:System.ServiceModel.Description.ServiceContractGenerator> genera contratos de servicio, tipos de cliente y configuraciones de cliente a partir de instancias de <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> y <xref:System.ServiceModel.Channels.Binding>. Normalmente, importa <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, y <xref:System.ServiceModel.Channels.Binding> crea instancias a partir de los metadatos del servicio y, a continuación, utiliza estas instancias para generar el código para llamar al servicio. En este ejemplo, se usa una implementación <xref:System.ServiceModel.Description.IWsdlImportExtension> para procesar las anotaciones WSDL y después agregar las extensiones de generación de código a los contratos importados para generar comentarios en el código generado.  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a>Escribir una extensión para ServiceContractGenerator  
  
1. Implemente <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>. Para modificar el contrato de servicio generado, use la instancia <xref:System.ServiceModel.Description.ServiceContractGenerationContext> pasada al método <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>.  
  
    ```csharp
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
        context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2. Implemente <xref:System.ServiceModel.Description.IWsdlImportExtension> en la misma clase. El método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> puede procesar una extensión WSDL concreta (anotaciones WSDL en este caso) agregando una extensión de generación de código a la instancia <xref:System.ServiceModel.Description.ContractDescription> importada.  
  
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
  
3. Agregue el importador de WSDL a su configuración de cliente.  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4. En el código de cliente, cree un `MetadataExchangeClient` y llame a `GetMetadata`:  
  
    ```csharp
    var mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5. Cree un `WsdlImporter` y llame a `ImportAllContracts`:  
  
    ```csharp
    var importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6. Cree un `ServiceContractGenerator` y llame a `GenerateServiceContractType` para cada contrato.  
  
    ```csharp
    var generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7. Se llama a <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> automáticamente para cada comportamiento del contrato en un contrato determinado que implementa <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>. Este método puede modificar el <xref:System.ServiceModel.Description.ServiceContractGenerationContext> pasado. En este ejemplo se agregan comentarios.  
  
## <a name="see-also"></a>Vea también

- [Metadata](../feature-details/metadata.md)
- [Procedimiento para importar el WSDL personalizado](how-to-import-custom-wsdl.md)
