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
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack

El tipo de opciones del protocolo de concentrador de MessagePack de ASP.NET Core SignalR ha cambiado de `IList<MessagePack.IFormatterResolver>` al tipo de `MessagePackSerializerOptions` de la biblioteca de [MessagePack](https://www.nuget.org/packages/MessagePack).

Para obtener información sobre este cambio, vea [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 4)

## <a name="old-behavior"></a>Comportamiento anterior

Puede agregar a las opciones como se muestra en el siguiente ejemplo:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

Reemplace las opciones de la siguiente manera:

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

## <a name="new-behavior"></a>Comportamiento nuevo

Puede agregar a las opciones como se muestra en el siguiente ejemplo:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

Reemplace las opciones de la siguiente manera:

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

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio forma parte de la migración a MessagePack v2.x, que se anunció en [ASPNET/Announcements#404](https://github.com/aspnet/Announcements/issues/404). La biblioteca v2.x ha agregado una API de opciones que es más fácil de usar y proporciona más características que la lista de `MessagePack.IFormatterResolver` que se expuso previamente.

## <a name="recommended-action"></a>Acción recomendada

Este cambio importante afecta a todos los usuarios que configuren valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>. Si usa el protocolo de concentrador de MessagePack de ASP.NET Core SignalR y modifica las opciones, actualice su uso para emplear la nueva API de opciones, como se mostró anteriormente.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
