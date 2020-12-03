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
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x

El [protocolo de concentrador de MessagePack](/aspnet/core/signalr/messagepackhubprotocol) de ASP.NET Core SignalR usa el paquete NuGet [MessagePack](https://www.nuget.org/packages/MessagePack) para la serialización de MessagePack. ASP.NET Core 5.0 actualiza el paquete de la versión 1.x a la más reciente de la 2.x.

Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 1)

## <a name="old-behavior"></a>Comportamiento anterior

ASP.NET Core SignalR usó el paquete MessagePack 1.x para serializar y deserializar mensajes MessagePack.

## <a name="new-behavior"></a>Comportamiento nuevo

ASP.NET Core SignalR usó el paquete MessagePack 2.x para serializar y deserializar mensajes MessagePack.

## <a name="reason-for-change"></a>Motivo del cambio

Las mejoras más recientes en el paquete MessagePack 2.x agregan funcionalidad útil.

## <a name="recommended-action"></a>Acción recomendada

Este cambio importante se aplica cuando:

* Se establecen o configuran valores en <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.
* Se usan las API de MessagePack directamente y el protocolo de concentrador de MessagePack de ASP.NET Core Signalr en el mismo proyecto. Se cargará la versión más reciente en lugar de la anterior.

Para obtener instrucciones sobre la migración de los autores de paquetes, vea el artículo de [migración desde MessagePack v1.x a MessagePack V2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md). Algunos aspectos de la serialización y deserialización de mensajes se ven afectados. En concreto, hay [cambios de comportamiento en la forma en que se serializan los valores DateTime](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
