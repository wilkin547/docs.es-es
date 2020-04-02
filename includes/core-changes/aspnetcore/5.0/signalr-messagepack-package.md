---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345215"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="513be-101">SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="513be-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="513be-102">El [protocolo de concentrador de MessagePack](/aspnet/core/signalr/messagepackhubprotocol) de ASP.NET Core SignalR usa el paquete NuGet [MessagePack](https://www.nuget.org/packages/MessagePack) para la serialización de MessagePack.</span><span class="sxs-lookup"><span data-stu-id="513be-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="513be-103">ASP.NET Core 5.0 actualiza el paquete de la versión 1.x a la más reciente de la 2.x.</span><span class="sxs-lookup"><span data-stu-id="513be-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="513be-104">Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="513be-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="513be-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="513be-105">Version introduced</span></span>

<span data-ttu-id="513be-106">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="513be-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="513be-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="513be-107">Old behavior</span></span>

<span data-ttu-id="513be-108">ASP.NET Core SignalR usó el paquete MessagePack 1.x para serializar y deserializar mensajes MessagePack.</span><span class="sxs-lookup"><span data-stu-id="513be-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="513be-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="513be-109">New behavior</span></span>

<span data-ttu-id="513be-110">ASP.NET Core SignalR usó el paquete MessagePack 2.x para serializar y deserializar mensajes MessagePack.</span><span class="sxs-lookup"><span data-stu-id="513be-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="513be-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="513be-111">Reason for change</span></span>

<span data-ttu-id="513be-112">Las mejoras más recientes en el paquete MessagePack 2.x agregan funcionalidad útil.</span><span class="sxs-lookup"><span data-stu-id="513be-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="513be-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="513be-113">Recommended action</span></span>

<span data-ttu-id="513be-114">Este cambio importante se aplica cuando:</span><span class="sxs-lookup"><span data-stu-id="513be-114">This breaking change applies when:</span></span>

* <span data-ttu-id="513be-115">Se establecen o configuran valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="513be-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="513be-116">Se usan las API de MessagePack directamente y el protocolo de concentrador de MessagePack de ASP.NET Core Signalr en el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="513be-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="513be-117">Se cargará la versión más reciente en lugar de la anterior.</span><span class="sxs-lookup"><span data-stu-id="513be-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="513be-118">Para obtener instrucciones sobre la migración de los autores de paquetes, vea el artículo de [migración desde MessagePack v1.x a MessagePack V2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="513be-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="513be-119">Algunos aspectos de la serialización y deserialización de mensajes se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="513be-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="513be-120">En concreto, hay [cambios de comportamiento en la forma en que se serializan los valores DateTime](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="513be-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="513be-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="513be-121">Category</span></span>

<span data-ttu-id="513be-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="513be-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="513be-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="513be-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
