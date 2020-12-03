---
title: 'Cambio importante: SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1e666c40d7046233c9fb06af819b901fd1251b06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760267"
---
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="26712-103">SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="26712-103">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="26712-104">El [protocolo de concentrador de MessagePack](/aspnet/core/signalr/messagepackhubprotocol) de ASP.NET Core SignalR usa el paquete NuGet [MessagePack](https://www.nuget.org/packages/MessagePack) para la serialización de MessagePack.</span><span class="sxs-lookup"><span data-stu-id="26712-104">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="26712-105">ASP.NET Core 5.0 actualiza el paquete de la versión 1.x a la más reciente de la 2.x.</span><span class="sxs-lookup"><span data-stu-id="26712-105">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="26712-106">Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="26712-106">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="26712-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="26712-107">Version introduced</span></span>

<span data-ttu-id="26712-108">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="26712-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="26712-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="26712-109">Old behavior</span></span>

<span data-ttu-id="26712-110">ASP.NET Core SignalR usó el paquete MessagePack 1.x para serializar y deserializar mensajes MessagePack.</span><span class="sxs-lookup"><span data-stu-id="26712-110">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="26712-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="26712-111">New behavior</span></span>

<span data-ttu-id="26712-112">ASP.NET Core SignalR usó el paquete MessagePack 2.x para serializar y deserializar mensajes MessagePack.</span><span class="sxs-lookup"><span data-stu-id="26712-112">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="26712-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="26712-113">Reason for change</span></span>

<span data-ttu-id="26712-114">Las mejoras más recientes en el paquete MessagePack 2.x agregan funcionalidad útil.</span><span class="sxs-lookup"><span data-stu-id="26712-114">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="26712-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="26712-115">Recommended action</span></span>

<span data-ttu-id="26712-116">Este cambio importante se aplica cuando:</span><span class="sxs-lookup"><span data-stu-id="26712-116">This breaking change applies when:</span></span>

* <span data-ttu-id="26712-117">Se establecen o configuran valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="26712-117">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="26712-118">Se usan las API de MessagePack directamente y el protocolo de concentrador de MessagePack de ASP.NET Core Signalr en el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="26712-118">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="26712-119">Se cargará la versión más reciente en lugar de la anterior.</span><span class="sxs-lookup"><span data-stu-id="26712-119">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="26712-120">Para obtener instrucciones sobre la migración de los autores de paquetes, vea el artículo de [migración desde MessagePack v1.x a MessagePack V2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="26712-120">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="26712-121">Algunos aspectos de la serialización y deserialización de mensajes se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="26712-121">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="26712-122">En concreto, hay [cambios de comportamiento en la forma en que se serializan los valores DateTime](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="26712-122">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="26712-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="26712-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
