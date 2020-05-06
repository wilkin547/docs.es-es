---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507104"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="8a809-101">SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack</span><span class="sxs-lookup"><span data-stu-id="8a809-101">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="8a809-102">El tipo de opciones del protocolo de concentrador de MessagePack de ASP.NET Core SignalR ha cambiado de `IList<MessagePack.IFormatterResolver>` al tipo de `MessagePackSerializerOptions` de la biblioteca de [MessagePack](https://www.nuget.org/packages/MessagePack).</span><span class="sxs-lookup"><span data-stu-id="8a809-102">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="8a809-103">Para obtener información sobre este cambio, vea [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span><span class="sxs-lookup"><span data-stu-id="8a809-103">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a809-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8a809-104">Version introduced</span></span>

<span data-ttu-id="8a809-105">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="8a809-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8a809-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="8a809-106">Old behavior</span></span>

<span data-ttu-id="8a809-107">Puede agregar a las opciones como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a809-107">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="8a809-108">Reemplace las opciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8a809-108">And replace the options as follows:</span></span>

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

#### <a name="new-behavior"></a><span data-ttu-id="8a809-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="8a809-109">New behavior</span></span>

<span data-ttu-id="8a809-110">Puede agregar a las opciones como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a809-110">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="8a809-111">Reemplace las opciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8a809-111">And replace the options as follows:</span></span>

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

#### <a name="reason-for-change"></a><span data-ttu-id="8a809-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8a809-112">Reason for change</span></span>

<span data-ttu-id="8a809-113">Este cambio forma parte de la migración a MessagePack v2.x, que se anunció en [ASPNET/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span><span class="sxs-lookup"><span data-stu-id="8a809-113">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="8a809-114">La biblioteca v2.x ha agregado una API de opciones que es más fácil de usar y proporciona más características que la lista de `MessagePack.IFormatterResolver` que se expuso previamente.</span><span class="sxs-lookup"><span data-stu-id="8a809-114">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a809-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8a809-115">Recommended action</span></span>

<span data-ttu-id="8a809-116">Este cambio importante afecta a todos los usuarios que configuren valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span><span class="sxs-lookup"><span data-stu-id="8a809-116">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="8a809-117">Si usa el protocolo de concentrador de MessagePack de ASP.NET Core SignalR y modifica las opciones, actualice su uso para emplear la nueva API de opciones, como se mostró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8a809-117">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

#### <a name="category"></a><span data-ttu-id="8a809-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="8a809-118">Category</span></span>

<span data-ttu-id="8a809-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8a809-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a809-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8a809-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
