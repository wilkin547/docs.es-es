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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="dce0e-102">Cómo: determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="dce0e-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="dce0e-103">Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección.</span><span class="sxs-lookup"><span data-stu-id="dce0e-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="dce0e-104">Cuando llega una solicitud de sondeo de multidifusión UDP en el proxy, el proxy debe responder con un mensaje de supresión de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="dce0e-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="dce0e-105">Para ello, tendría que conocer la versión de detección de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dce0e-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="dce0e-106">Para determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="dce0e-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="dce0e-107">En el método que responde a una solicitud de sondeo (por ejemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> ,) Use la <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> propiedad estática para buscar un <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="dce0e-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="dce0e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="dce0e-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="dce0e-109">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="dce0e-109">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
