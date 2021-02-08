---
description: 'Más información acerca de cómo: determinar la versión de detección de una solicitud de sondeo'
title: 'Cómo: determinar la versión de detección de una solicitud de sondeo'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: c41283cb84d75dd2dbf7e86da0dec075ab8b6635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793797"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Cómo: determinar la versión de detección de una solicitud de sondeo

Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección. Cuando llega una solicitud de sondeo de multidifusión UDP en el proxy, el proxy debe responder con un mensaje de supresión de multidifusión. Para ello, tendría que conocer la versión de detección de la solicitud.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Para determinar la versión de detección de una solicitud de sondeo

En el método que responde a una solicitud de sondeo (por ejemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> ,) Use la <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> propiedad estática para buscar un <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , como se muestra en el código siguiente.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementar un proxy de detección](implementing-a-discovery-proxy.md)
