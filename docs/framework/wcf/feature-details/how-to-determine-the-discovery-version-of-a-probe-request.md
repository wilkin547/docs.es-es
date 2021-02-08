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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="2deb3-103">Cómo: determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="2deb3-103">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="2deb3-104">Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección.</span><span class="sxs-lookup"><span data-stu-id="2deb3-104">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="2deb3-105">Cuando llega una solicitud de sondeo de multidifusión UDP en el proxy, el proxy debe responder con un mensaje de supresión de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="2deb3-105">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="2deb3-106">Para ello, tendría que conocer la versión de detección de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2deb3-106">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="2deb3-107">Para determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="2deb3-107">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="2deb3-108">En el método que responde a una solicitud de sondeo (por ejemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> ,) Use la <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> propiedad estática para buscar un <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2deb3-108">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="2deb3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2deb3-109">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="2deb3-110">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="2deb3-110">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
