---
title: Comparación de ASP.NET Signalr y ASP.NET Core Signalr
description: ¿Cómo difiere ASP.NET Core Signalr de su predecesor, ASP.NET Signalr?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 89236bd0272c8f20cf9838dddefeb9afee1f3d93
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401695"
---
# <a name="compare-aspnet-signalr-and-aspnet-core-signalr"></a><span data-ttu-id="871d8-103">Comparación de ASP.NET Signalr y ASP.NET Core Signalr</span><span class="sxs-lookup"><span data-stu-id="871d8-103">Compare ASP.NET SignalR and ASP.NET Core SignalR</span></span>

<span data-ttu-id="871d8-104">ASP.NET Core Signalr no es compatible con clientes o servidores que usan ASP.NET Signalr.</span><span class="sxs-lookup"><span data-stu-id="871d8-104">ASP.NET Core SignalR is incompatible with clients or servers using ASP.NET SignalR.</span></span> <span data-ttu-id="871d8-105">Tendrá que actualizar los clientes y el servidor para usar ASP.NET Core Signalr.</span><span class="sxs-lookup"><span data-stu-id="871d8-105">You'll need to update both clients and server to use ASP.NET Core SignalR.</span></span> <span data-ttu-id="871d8-106">En esta sección se describen algunas diferencias, mientras que la lista completa está disponible en los [documentos](/aspnet/core/signalr/version-differences). ASP.NET Core Signalr requiere .NET Core 2,1 o superior.</span><span class="sxs-lookup"><span data-stu-id="871d8-106">Some differences are described in this section, while the full list is available in the [docs](/aspnet/core/signalr/version-differences). ASP.NET Core SignalR requires .NET Core 2.1 or greater.</span></span>

## <a name="feature-differences"></a><span data-ttu-id="871d8-107">Diferencias de características</span><span class="sxs-lookup"><span data-stu-id="871d8-107">Feature differences</span></span>

- <span data-ttu-id="871d8-108">ASP.NET Signalr intenta volver a conectar automáticamente las conexiones quitadas. Este comportamiento es opcional para los clientes de Signalr ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="871d8-108">ASP.NET SignalR automatically attempts to reconnect dropped connections; this behavior is opt-in for ASP.NET Core SignalR clients</span></span>
- <span data-ttu-id="871d8-109">Ambos marcos admiten JSON; ASP.NET Core Signalr también admite un protocolo binario basado en MessagePack y se pueden crear protocolos personalizados.</span><span class="sxs-lookup"><span data-stu-id="871d8-109">Both frameworks support JSON; ASP.NET Core SignalR also supports a binary protocol based on MessagePack, and custom protocols can be created.</span></span>
- <span data-ttu-id="871d8-110">El transporte de tramas Forever, admitido por ASP.NET Signalr, no se admite en ASP.NET Core Signalr.</span><span class="sxs-lookup"><span data-stu-id="871d8-110">The Forever Frame transport, supported by ASP.NET SignalR, isn't supported in ASP.NET Core SignalR.</span></span>
- <span data-ttu-id="871d8-111">ASP.NET Core Signalr se debe configurar agregando `services.AddSignalR()` y `app.UseEndpoints` en `Startup.ConfigureServices` y `Startup.Configure` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="871d8-111">ASP.NET Core SignalR must be configured by adding `services.AddSignalR()` and `app.UseEndpoints` in `Startup.ConfigureServices` and `Startup.Configure`, respectively.</span></span>
- <span data-ttu-id="871d8-112">ASP.NET Core Signalr requiere sesiones permanentes; ASP.NET Signalr no.</span><span class="sxs-lookup"><span data-stu-id="871d8-112">ASP.NET Core SignalR requires sticky sessions; ASP.NET SignalR doesn't.</span></span>
- <span data-ttu-id="871d8-113">ASP.NET Core simplifica el modelo de conexión; las conexiones solo se realizan en un solo concentrador.</span><span class="sxs-lookup"><span data-stu-id="871d8-113">ASP.NET Core simplifies the connection model; connections are only made to a single hub.</span></span>
- <span data-ttu-id="871d8-114">ASP.NET Core Signalr admite el streaming de datos del concentrador al cliente.</span><span class="sxs-lookup"><span data-stu-id="871d8-114">ASP.NET Core SignalR supports streaming data from the hub to the client.</span></span>
- <span data-ttu-id="871d8-115">ASP.NET Core Signalr no permite pasar el estado entre los clientes y el concentrador.</span><span class="sxs-lookup"><span data-stu-id="871d8-115">ASP.NET Core SignalR doesn't support passing state between clients and the hub.</span></span>
- <span data-ttu-id="871d8-116">La `PersistentConnection` clase no existe en ASP.net Core signalr.</span><span class="sxs-lookup"><span data-stu-id="871d8-116">The `PersistentConnection` class doesn't exist in ASP.NET Core SignalR.</span></span>
- <span data-ttu-id="871d8-117">ASP.NET Signalr admite SQL Server y Redis.</span><span class="sxs-lookup"><span data-stu-id="871d8-117">ASP.NET SignalR supports SQL Server and Redis.</span></span> <span data-ttu-id="871d8-118">ASP.NET Core Signalr es compatible con [Azure signalr](/azure/azure-signalr/) y Redis.</span><span class="sxs-lookup"><span data-stu-id="871d8-118">ASP.NET Core SignalR supports [Azure SignalR](/azure/azure-signalr/) and Redis.</span></span>

## <a name="references"></a><span data-ttu-id="871d8-119">Referencias</span><span class="sxs-lookup"><span data-stu-id="871d8-119">References</span></span>

- [<span data-ttu-id="871d8-120">Diferencias entre ASP.NET Signalr y ASP.NET Core Signalr</span><span class="sxs-lookup"><span data-stu-id="871d8-120">Differences between ASP.NET SignalR and ASP.NET Core SignalR</span></span>](/aspnet/core/signalr/version-differences)
- [<span data-ttu-id="871d8-121">Servicio Azure SignalR</span><span class="sxs-lookup"><span data-stu-id="871d8-121">Azure SignalR Service</span></span>](/azure/azure-signalr/)

>[!div class="step-by-step"]
><span data-ttu-id="871d8-122">[Anterior](razor-differences.md)
>[Siguiente](testing-differences.md)</span><span class="sxs-lookup"><span data-stu-id="871d8-122">[Previous](razor-differences.md)
[Next](testing-differences.md)</span></span>
