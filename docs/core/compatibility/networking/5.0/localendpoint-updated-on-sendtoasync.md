---
title: 'Cambio importante: Socket.LocalEndPoint se actualiza después de llamar a SendToAsync'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde ahora SendToAsync actualiza el valor de la propiedad de punto de conexión local a la dirección local del socket.
ms.date: 10/18/2020
ms.openlocfilehash: 53d7da350eac6e65832012331044427fd90fe796
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760145"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint se actualiza después de llamar a SendToAsync

Ahora <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> actualiza el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> a la dirección local del socket.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> no modifica el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> en la instancia del socket. A partir de .NET 5.0, cuando <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> se completa de forma correcta, el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> es la dirección local del socket enlazado de forma implícita. Este nuevo comportamiento es coherente con el de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> y <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.

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
