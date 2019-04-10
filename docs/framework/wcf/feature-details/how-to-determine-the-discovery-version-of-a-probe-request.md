---
title: 'Cómo: determinar la versión de detección de una solicitud de sondeo'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 6bd112be311eb9397ad89801be5358d67c7499fd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332279"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Cómo: determinar la versión de detección de una solicitud de sondeo
Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección. Cuando llega una solicitud de sondeo multidifusión UDP al proxy, este debe responder con un mensaje de supresión de multidifusión. Para ello, se debe conocer la versión de detección de la solicitud.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Para determinar la versión de detección de una solicitud de sondeo  
  
1. En el método que responda a una solicitud de sondeo (por ejemplo, el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use la propiedad estática <xref:System.ServiceModel.OperationContext.Current%2A> para buscar una extensión <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> como se muestra en el código siguiente.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementar un proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
