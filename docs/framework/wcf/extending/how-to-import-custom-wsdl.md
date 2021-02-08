---
description: 'Más información acerca de cómo: importar WSDL personalizado'
title: Procedimiento para importar el WSDL personalizado
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: f21e5cace532bd6d20d409f297480f65bb23cbf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780744"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="1a19d-103">Procedimiento para importar el WSDL personalizado</span><span class="sxs-lookup"><span data-stu-id="1a19d-103">How to: Import Custom WSDL</span></span>

<span data-ttu-id="1a19d-104">En este tema se describe cómo importar WSDL personalizado.</span><span class="sxs-lookup"><span data-stu-id="1a19d-104">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="1a19d-105">Para administrar el WSDL personalizado, debe implementar la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="1a19d-105">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="1a19d-106">Para importar el WSDL personalizado</span><span class="sxs-lookup"><span data-stu-id="1a19d-106">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="1a19d-107">Implemente <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="1a19d-107">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="1a19d-108">Implemente el método <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> para modificar los metadatos antes de que se importen.</span><span class="sxs-lookup"><span data-stu-id="1a19d-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="1a19d-109">Implemente los métodos <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> y <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> para modificar contratos y extremos importados de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="1a19d-109">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="1a19d-110">Para tener acceso al contrato o punto de conexión importados, utilice el objeto de contexto (<xref:System.ServiceModel.Description.WsdlContractConversionContext> correspondiente o <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="1a19d-110">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```csharp
    public class WsdlDocumentationImporter : IWsdlImportExtension
    {
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
    }
    ```
  
2. <span data-ttu-id="1a19d-111">Configure la aplicación de cliente para utilizar el importador de WSDL personalizado.</span><span class="sxs-lookup"><span data-stu-id="1a19d-111">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="1a19d-112">Tenga en cuenta que si está utilizando Svcutil.exe, debería agregar esta configuración al archivo de configuración para Svcutil.exe (Svcutil.exe.config):</span><span class="sxs-lookup"><span data-stu-id="1a19d-112">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint
              address="http://localhost:8000/Fibonacci"
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3. <span data-ttu-id="1a19d-113">Cree una nueva instancia <xref:System.ServiceModel.Description.WsdlImporter> (pasar la instancia <xref:System.ServiceModel.Description.MetadataSet> que contiene los documentos WSDL que desea importar) y llame a <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span><span class="sxs-lookup"><span data-stu-id="1a19d-113">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a19d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a19d-114">See also</span></span>

- [<span data-ttu-id="1a19d-115">Metadata</span><span class="sxs-lookup"><span data-stu-id="1a19d-115">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="1a19d-116">Exportación e importación de metadatos</span><span class="sxs-lookup"><span data-stu-id="1a19d-116">Exporting and Importing Metadata</span></span>](../feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="1a19d-117">Publicación de WSDL personalizada</span><span class="sxs-lookup"><span data-stu-id="1a19d-117">Custom WSDL Publication</span></span>](../samples/custom-wsdl-publication.md)
