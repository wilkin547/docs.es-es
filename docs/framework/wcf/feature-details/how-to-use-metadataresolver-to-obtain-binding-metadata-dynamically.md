---
title: "C&#243;mo: Utilizar MetadataResolver para obtener din&#225;micamente metadatos de enlace | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# C&#243;mo: Utilizar MetadataResolver para obtener din&#225;micamente metadatos de enlace
En este tema se muestra cómo utilizar la clase <xref:System.ServiceModel.Description.MetadataResolver> para obtener dinámicamente los metadatos del enlace.  
  
### Para obtener dinámicamente los metadatos del enlace  
  
1.  Cree un objeto <xref:System.ServiceModel.EndpointAddress> con la dirección del extremo de metadatos.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  Llame a <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, que pasa el tipo de servicio y la dirección del extremo de metadatos.Esto devuelve una colección de extremos que implementan el contrato especificado.Solo la información de enlace se importa desde los metadatos; la información del contrato no se importa.Se utiliza el contrato proporcionado en su lugar.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  A continuación, puede recorrer en iteración la colección de extremos de servicio para extraer la información de enlace que necesite.El siguiente código recorre en iteración a través de los extremos, crea un objeto de cliente de servicio que pasa el enlace y la dirección asociada al extremo actual y, a continuación, llama a un método en el servicio.  
  
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
  
## Vea también  
 [Metadatos](../../../../docs/framework/wcf/feature-details/metadata.md)