---
description: 'Más información sobre: Cómo: usar MetadataResolver para obtener metadatos de enlace dinámicamente'
title: Procedimiento para usar MetadataResolver para obtener dinámicamente metadatos de enlace
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: 00f33b31504ede6868113040ba83b6f9462ee808
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734287"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="6f00e-103">Procedimiento para usar MetadataResolver para obtener dinámicamente metadatos de enlace</span><span class="sxs-lookup"><span data-stu-id="6f00e-103">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>

<span data-ttu-id="6f00e-104">En este tema se muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataResolver> para obtener dinámicamente los metadatos del enlace.</span><span class="sxs-lookup"><span data-stu-id="6f00e-104">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="6f00e-105">Para obtener dinámicamente los metadatos del enlace</span><span class="sxs-lookup"><span data-stu-id="6f00e-105">To dynamically obtain binding metadata</span></span>  
  
1. <span data-ttu-id="6f00e-106">Cree un objeto <xref:System.ServiceModel.EndpointAddress> con la dirección del extremo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6f00e-106">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. <span data-ttu-id="6f00e-107">Llame a <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, que pasa el tipo de servicio y la dirección del punto de conexión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6f00e-107">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="6f00e-108">Esto devuelve una colección de puntos de conexión que implementan el contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="6f00e-108">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="6f00e-109">Solo la información de enlace se importa desde los metadatos; la información del contrato no se importa.</span><span class="sxs-lookup"><span data-stu-id="6f00e-109">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="6f00e-110">Se utiliza el contrato proporcionado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6f00e-110">The supplied contract is used instead.</span></span>  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. <span data-ttu-id="6f00e-111">A continuación, puede recorrer en iteración la colección de extremos de servicio para extraer la información de enlace que necesite.</span><span class="sxs-lookup"><span data-stu-id="6f00e-111">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="6f00e-112">El siguiente código recorre en iteración a través de los extremos, crea un objeto de cliente de servicio que pasa el enlace y la dirección asociada al extremo actual y, a continuación, llama a un método en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6f00e-112">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```csharp  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6f00e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f00e-113">See also</span></span>

- [<span data-ttu-id="6f00e-114">Metadata</span><span class="sxs-lookup"><span data-stu-id="6f00e-114">Metadata</span></span>](metadata.md)
