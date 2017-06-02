---
title: "C&#243;mo: determinar la versi&#243;n de detecci&#243;n de una solicitud de sondeo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: determinar la versi&#243;n de detecci&#243;n de una solicitud de sondeo
Un proxy de detección puede exponer varios extremos de detección mediante distintas versiones de detección.  Cuando llega una solicitud de sondeo multidifusión UDP al proxy, este debe responder con un mensaje de supresión de multidifusión.  Para ello, se debe conocer la versión de detección de la solicitud.  
  
### Para determinar la versión de detección de una solicitud de sondeo  
  
1.  En el método que responda a una solicitud de sondeo \(por ejemplo, el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>\) use la propiedad estática <xref:System.ServiceModel.OperationContext.Current%2A> para buscar una extensión <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> como se muestra en el código siguiente.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
  
    ```  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>   
 [Implementar un proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)   
 [Ejemplo de proxy de detección](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)