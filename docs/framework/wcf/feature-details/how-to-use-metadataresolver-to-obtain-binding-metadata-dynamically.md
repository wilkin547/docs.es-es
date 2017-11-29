---
title: "Cómo: Utilizar MetadataResolver para obtener dinámicamente metadatos de enlace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab95212d0f7b57b2bc076bed862b3d07c3c93df9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="dc33b-102">Cómo: Utilizar MetadataResolver para obtener dinámicamente metadatos de enlace</span><span class="sxs-lookup"><span data-stu-id="dc33b-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>
<span data-ttu-id="dc33b-103">En este tema se muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataResolver> para obtener dinámicamente los metadatos del enlace.</span><span class="sxs-lookup"><span data-stu-id="dc33b-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="dc33b-104">Para obtener dinámicamente los metadatos del enlace</span><span class="sxs-lookup"><span data-stu-id="dc33b-104">To dynamically obtain binding metadata</span></span>  
  
1.  <span data-ttu-id="dc33b-105">Cree un objeto <xref:System.ServiceModel.EndpointAddress> con la dirección del extremo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc33b-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  <span data-ttu-id="dc33b-106">Llame a <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, que pasa el tipo de servicio y la dirección del extremo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc33b-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="dc33b-107">Esto devuelve una colección de extremos que implementan el contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="dc33b-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="dc33b-108">Solo la información de enlace se importa desde los metadatos; la información del contrato no se importa.</span><span class="sxs-lookup"><span data-stu-id="dc33b-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="dc33b-109">Se utiliza el contrato proporcionado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dc33b-109">The supplied contract is used instead.</span></span>  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  <span data-ttu-id="dc33b-110">A continuación, puede recorrer en iteración la colección de extremos de servicio para extraer la información de enlace que necesite.</span><span class="sxs-lookup"><span data-stu-id="dc33b-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="dc33b-111">El siguiente código recorre en iteración a través de los puntos de conexión, crea un objeto de cliente de servicio que pasa el enlace y la dirección asociada al punto de conexión actual y, a continuación, llama a un método en el servicio.</span><span class="sxs-lookup"><span data-stu-id="dc33b-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```  
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
  
## <a name="see-also"></a><span data-ttu-id="dc33b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc33b-112">See Also</span></span>  
 [<span data-ttu-id="dc33b-113">Metadatos</span><span class="sxs-lookup"><span data-stu-id="dc33b-113">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
