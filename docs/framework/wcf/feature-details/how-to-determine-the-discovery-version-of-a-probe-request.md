---
title: "Cómo: determinar la versión de detección de una solicitud de sondeo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2ff5d45997456c12d0292176771ad3c332f6c043
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Cómo: determinar la versión de detección de una solicitud de sondeo
Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección. Cuando llega una solicitud de sondeo multidifusión UDP al proxy, este debe responder con un mensaje de supresión de multidifusión. Para ello, se debe conocer la versión de detección de la solicitud.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Para determinar la versión de detección de una solicitud de sondeo  
  
1.  En el método que responda a una solicitud de sondeo (por ejemplo, el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use la propiedad estática <xref:System.ServiceModel.OperationContext.Current%2A> para buscar una extensión <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> como se muestra en el código siguiente.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [Implementar a un Proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [Ejemplo de Proxy de detección](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
