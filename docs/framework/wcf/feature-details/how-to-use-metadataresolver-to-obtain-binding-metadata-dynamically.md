---
title: 'Cómo: Utilizar MetadataResolver para obtener dinámicamente metadatos de enlace'
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: cffe47f301c1943a0d97e3a95a5b7c24979b4f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Cómo: Utilizar MetadataResolver para obtener dinámicamente metadatos de enlace
En este tema se muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataResolver> para obtener dinámicamente los metadatos del enlace.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>Para obtener dinámicamente los metadatos del enlace  
  
1.  Cree un objeto <xref:System.ServiceModel.EndpointAddress> con la dirección del extremo de metadatos.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  Llame a <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, que pasa el tipo de servicio y la dirección del extremo de metadatos. Esto devuelve una colección de extremos que implementan el contrato especificado. Solo la información de enlace se importa desde los metadatos; la información del contrato no se importa. Se utiliza el contrato proporcionado en su lugar.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  A continuación, puede recorrer en iteración la colección de extremos de servicio para extraer la información de enlace que necesite. El siguiente código recorre en iteración a través de los puntos de conexión, crea un objeto de cliente de servicio que pasa el enlace y la dirección asociada al punto de conexión actual y, a continuación, llama a un método en el servicio.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Metadatos](../../../../docs/framework/wcf/feature-details/metadata.md)
