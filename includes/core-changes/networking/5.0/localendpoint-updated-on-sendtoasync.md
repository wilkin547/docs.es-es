---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050536"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="aece2-101">Socket.LocalEndPoint se actualiza después de llamar a SendToAsync</span><span class="sxs-lookup"><span data-stu-id="aece2-101">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="aece2-102">Ahora <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> actualiza el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> a la dirección local del socket.</span><span class="sxs-lookup"><span data-stu-id="aece2-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aece2-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="aece2-103">Version introduced</span></span>

<span data-ttu-id="aece2-104">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="aece2-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="aece2-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="aece2-105">Change description</span></span>

<span data-ttu-id="aece2-106">En versiones anteriores de .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> no modifica el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> en la instancia del socket.</span><span class="sxs-lookup"><span data-stu-id="aece2-106">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="aece2-107">A partir de .NET 5.0, cuando <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> se completa de forma correcta, el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> es la dirección local del socket enlazado de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="aece2-107">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="aece2-108">Este nuevo comportamiento es coherente con el de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> y <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span><span class="sxs-lookup"><span data-stu-id="aece2-108">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aece2-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="aece2-109">Reason for change</span></span>

<span data-ttu-id="aece2-110">Este cambio [corrige un error](https://github.com/dotnet/runtime/issues/915) y hace que el comportamiento sea coherente entre las variantes de `SendTo`.</span><span class="sxs-lookup"><span data-stu-id="aece2-110">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aece2-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="aece2-111">Recommended action</span></span>

<span data-ttu-id="aece2-112">Modifique cualquier código en el que se asuma que <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> no modificará el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aece2-112">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="aece2-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="aece2-113">Category</span></span>

<span data-ttu-id="aece2-114">Redes</span><span class="sxs-lookup"><span data-stu-id="aece2-114">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aece2-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="aece2-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
