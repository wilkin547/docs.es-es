---
title: 'Cómo: Importar metadatos en puntos de conexión de servicio'
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: 88b48b95a62c000d88b302589ebc489089e77602
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492549"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="11964-102">Cómo: Importar metadatos en puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="11964-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="11964-103">Este tema explica cómo importar metadatos en una colección de extremos de servicio y usar el servicio definido en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="11964-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="11964-104">En este tema se muestra cómo crear una aplicación cliente que importa los metadatos desde el servicio y, a continuación, llama al método `Add` en el servicio.</span><span class="sxs-lookup"><span data-stu-id="11964-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="11964-105">Para importar metadatos a extremos de servicio</span><span class="sxs-lookup"><span data-stu-id="11964-105">To import metadata into service endpoints</span></span>  
  
1.  <span data-ttu-id="11964-106">Declare un objeto <xref:System.ServiceModel.EndpointAddress> e inicialícelo con el Identificador uniforme de recursos (URI) para la dirección del servicio de intercambio de metadatos (MEX).</span><span class="sxs-lookup"><span data-stu-id="11964-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  <span data-ttu-id="11964-107">Cree <xref:System.ServiceModel.Description.MetadataExchangeClient>, pasando la dirección de MEX y llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="11964-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="11964-108">Esto recupera los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="11964-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  <span data-ttu-id="11964-109">Cree <xref:System.ServiceModel.Description.WsdlImporter>, pasando los metadatos previamente recuperados y llame <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="11964-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="11964-110">Esto genera una colección de los objetos <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="11964-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="11964-111">También podría llamar <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> o <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, dependiendo de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="11964-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="11964-112">Después de haber importado los metadatos, no podrá crear un canal de cliente o exportar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="11964-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="11964-113">Esto es porque ninguna información de tipo está disponible en este punto.</span><span class="sxs-lookup"><span data-stu-id="11964-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="11964-114">Se exige información de tipo para interactuar realmente con el servicio o exportar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="11964-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="11964-115">Para generar la información de tipo, necesita generar el código, tal como se muestra en los pasos 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="11964-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="11964-116">También podría utilizar la clase auxiliar <xref:System.ServiceModel.Description.MetadataResolver>.</span><span class="sxs-lookup"><span data-stu-id="11964-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> <span data-ttu-id="11964-117">Para obtener más información, consulte [Cómo: utilizar MetadataResolver para obtener dinámicamente metadatos de enlace](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="11964-117">For more information, see [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4.  <span data-ttu-id="11964-118">Genere información de tipo para cada contrato.</span><span class="sxs-lookup"><span data-stu-id="11964-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  <span data-ttu-id="11964-119">Ahora puede utilizar esta información.</span><span class="sxs-lookup"><span data-stu-id="11964-119">Now you can use this information.</span></span> <span data-ttu-id="11964-120">El ejemplo siguiente genera el código fuente C#:</span><span class="sxs-lookup"><span data-stu-id="11964-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="11964-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="11964-121">See Also</span></span>  
 [<span data-ttu-id="11964-122">Metadatos</span><span class="sxs-lookup"><span data-stu-id="11964-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="11964-123">Introducción</span><span class="sxs-lookup"><span data-stu-id="11964-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
