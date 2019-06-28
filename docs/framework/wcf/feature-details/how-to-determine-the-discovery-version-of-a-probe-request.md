---
title: 'Cómo: determinar la versión de detección de una solicitud de sondeo'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425265"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Cómo: determinar la versión de detección de una solicitud de sondeo

Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección. Cuando una multidifusión de UDP solicitud de sondeo llega en el servidor proxy, el proxy debe responder con un mensaje de supresión de multidifusión. Para ello, tendría que conocer la versión de detección de la solicitud.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Para determinar la versión de detección de una solicitud de sondeo

En el método que responda a una solicitud de sondeo (por ejemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) usar estático <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> propiedad para buscar un <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, tal y como se muestra en el código siguiente.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementación de un proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
