---
title: 'Cambio importante: Socket.LocalEndPoint se actualiza después de llamar a SendToAsync'
description: Obtenga información sobre el cambio importante en .NET 5, donde ahora SendToAsync actualiza el valor de la propiedad de punto de conexión local a la dirección local del socket.
ms.date: 10/18/2020
ms.openlocfilehash: 4be62f8bf6596cc3531d59f3e65eda005bff778a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256431"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint se actualiza después de llamar a SendToAsync

Ahora <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> actualiza el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> a la dirección local del socket.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> no modifica el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> en la instancia del socket. A partir de .NET 5, cuando <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> se completa de forma correcta, el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> es la dirección local del socket enlazado de forma implícita. Este nuevo comportamiento es coherente con el de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> y <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio [corrige un error](https://github.com/dotnet/runtime/issues/915) y hace que el comportamiento sea coherente entre las variantes de `SendTo`.

## <a name="recommended-action"></a>Acción recomendada

Modifique cualquier código en el que se asuma que <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> no modificará el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
