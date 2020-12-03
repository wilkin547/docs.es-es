---
title: 'Cambio importante: SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b75dbec834699472f18b3058052274476bd9751d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760268"
---
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="6969c-103">SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack</span><span class="sxs-lookup"><span data-stu-id="6969c-103">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="6969c-104">El tipo de opciones del protocolo de concentrador de MessagePack de ASP.NET Core SignalR ha cambiado de `IList<MessagePack.IFormatterResolver>` al tipo de `MessagePackSerializerOptions` de la biblioteca de [MessagePack](https://www.nuget.org/packages/MessagePack).</span><span class="sxs-lookup"><span data-stu-id="6969c-104">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="6969c-105">Para obtener información sobre este cambio, vea [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span><span class="sxs-lookup"><span data-stu-id="6969c-105">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6969c-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6969c-106">Version introduced</span></span>

<span data-ttu-id="6969c-107">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="6969c-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6969c-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="6969c-108">Old behavior</span></span>

<span data-ttu-id="6969c-109">Puede agregar a las opciones como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6969c-109">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="6969c-110">Reemplace las opciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6969c-110">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

## <a name="new-behavior"></a><span data-ttu-id="6969c-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="6969c-111">New behavior</span></span>

<span data-ttu-id="6969c-112">Puede agregar a las opciones como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6969c-112">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="6969c-113">Reemplace las opciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6969c-113">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

## <a name="reason-for-change"></a><span data-ttu-id="6969c-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6969c-114">Reason for change</span></span>

<span data-ttu-id="6969c-115">Este cambio forma parte de la migración a MessagePack v2.x, que se anunció en [ASPNET/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span><span class="sxs-lookup"><span data-stu-id="6969c-115">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="6969c-116">La biblioteca v2.x ha agregado una API de opciones que es más fácil de usar y proporciona más características que la lista de `MessagePack.IFormatterResolver` que se expuso previamente.</span><span class="sxs-lookup"><span data-stu-id="6969c-116">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6969c-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6969c-117">Recommended action</span></span>

<span data-ttu-id="6969c-118">Este cambio importante afecta a todos los usuarios que configuren valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="6969c-118">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="6969c-119">Si usa el protocolo de concentrador de MessagePack de ASP.NET Core SignalR y modifica las opciones, actualice su uso para emplear la nueva API de opciones, como se mostró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6969c-119">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6969c-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6969c-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
