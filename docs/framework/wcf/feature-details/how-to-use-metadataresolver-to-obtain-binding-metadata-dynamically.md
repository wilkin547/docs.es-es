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
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Procedimiento para usar MetadataResolver para obtener dinámicamente metadatos de enlace

En este tema se muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataResolver> para obtener dinámicamente los metadatos del enlace.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>Para obtener dinámicamente los metadatos del enlace  
  
1. Cree un objeto <xref:System.ServiceModel.EndpointAddress> con la dirección del extremo de metadatos.  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. Llame a <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, que pasa el tipo de servicio y la dirección del punto de conexión de metadatos. Esto devuelve una colección de puntos de conexión que implementan el contrato especificado. Solo la información de enlace se importa desde los metadatos; la información del contrato no se importa. Se utiliza el contrato proporcionado en su lugar.  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. A continuación, puede recorrer en iteración la colección de extremos de servicio para extraer la información de enlace que necesite. El siguiente código recorre en iteración a través de los extremos, crea un objeto de cliente de servicio que pasa el enlace y la dirección asociada al extremo actual y, a continuación, llama a un método en el servicio.  
  
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
  
## <a name="see-also"></a>Vea también

- [Metadata](metadata.md)
