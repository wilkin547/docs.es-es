---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050536"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint se actualiza después de llamar a SendToAsync

Ahora <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> actualiza el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> a la dirección local del socket.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC1

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> no modifica el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> en la instancia del socket. A partir de .NET 5.0, cuando <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> se completa de forma correcta, el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> es la dirección local del socket enlazado de forma implícita. Este nuevo comportamiento es coherente con el de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> y <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio [corrige un error](https://github.com/dotnet/runtime/issues/915) y hace que el comportamiento sea coherente entre las variantes de `SendTo`.

#### <a name="recommended-action"></a>Acción recomendada

Modifique cualquier código en el que se asuma que <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> no modificará el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Redes

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
