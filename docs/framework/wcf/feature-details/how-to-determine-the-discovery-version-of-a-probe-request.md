---
title: 'Cómo: determinar la versión de detección de una solicitud de sondeo'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595419"
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
