---
description: 'Más información acerca de cómo: importar metadatos en puntos de conexión de servicio'
title: Procedimiento para importar metadatos a puntos de conexión de servicio
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: d6e69b64c5f70a8e49ed6ee7c9ff319f5a639a30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793745"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="953bd-103">Procedimiento para importar metadatos a puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="953bd-103">How to: Import Metadata into Service Endpoints</span></span>

<span data-ttu-id="953bd-104">En este tema se explica cómo importar metadatos en una colección de puntos de conexión de servicio y usar el servicio definido en el [Introducción](../samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="953bd-104">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../samples/getting-started-sample.md).</span></span> <span data-ttu-id="953bd-105">En este tema se muestra cómo crear una aplicación cliente que importa los metadatos desde el servicio y, a continuación, llama al método `Add` en el servicio.</span><span class="sxs-lookup"><span data-stu-id="953bd-105">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="953bd-106">Para importar metadatos a puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="953bd-106">To import metadata into service endpoints</span></span>  
  
1. <span data-ttu-id="953bd-107">Declare un objeto <xref:System.ServiceModel.EndpointAddress> e inicialícelo con el Identificador uniforme de recursos (URI) para la dirección del servicio de intercambio de metadatos (MEX).</span><span class="sxs-lookup"><span data-stu-id="953bd-107">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2. <span data-ttu-id="953bd-108">Cree <xref:System.ServiceModel.Description.MetadataExchangeClient>, pasando la dirección de MEX y llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="953bd-108">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="953bd-109">Esto recupera los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="953bd-109">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3. <span data-ttu-id="953bd-110">Cree <xref:System.ServiceModel.Description.WsdlImporter>, pasando los metadatos previamente recuperados y llame <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="953bd-110">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="953bd-111">Esto genera una colección de los objetos <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="953bd-111">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="953bd-112">También podría llamar <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> o <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, dependiendo de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="953bd-112">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="953bd-113">Después de haber importado los metadatos, no podrá crear un canal de cliente o exportar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="953bd-113">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="953bd-114">Esto es porque ninguna información de tipo está disponible en este punto.</span><span class="sxs-lookup"><span data-stu-id="953bd-114">This is because no type information is available at this point.</span></span> <span data-ttu-id="953bd-115">Se exige información de tipo para interactuar realmente con el servicio o exportar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="953bd-115">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="953bd-116">Para generar la información de tipo, necesita generar el código, tal como se muestra en los pasos 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="953bd-116">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="953bd-117">También podría utilizar la clase del asistente <xref:System.ServiceModel.Description.MetadataResolver>.</span><span class="sxs-lookup"><span data-stu-id="953bd-117">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> <span data-ttu-id="953bd-118">Para obtener más información, vea [Cómo: usar MetadataResolver para obtener dinámicamente metadatos de enlace](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="953bd-118">For more information, see [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4. <span data-ttu-id="953bd-119">Genere información de tipo para cada contrato.</span><span class="sxs-lookup"><span data-stu-id="953bd-119">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5. <span data-ttu-id="953bd-120">Ahora puede utilizar esta información.</span><span class="sxs-lookup"><span data-stu-id="953bd-120">Now you can use this information.</span></span> <span data-ttu-id="953bd-121">El ejemplo siguiente genera el código fuente C#:</span><span class="sxs-lookup"><span data-stu-id="953bd-121">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="953bd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="953bd-122">See also</span></span>

- [<span data-ttu-id="953bd-123">Metadata</span><span class="sxs-lookup"><span data-stu-id="953bd-123">Metadata</span></span>](metadata.md)
- [<span data-ttu-id="953bd-124">Introducción</span><span class="sxs-lookup"><span data-stu-id="953bd-124">Getting Started</span></span>](../samples/getting-started-sample.md)
