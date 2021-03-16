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
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="a1dd0-103">Socket.LocalEndPoint se actualiza después de llamar a SendToAsync</span><span class="sxs-lookup"><span data-stu-id="a1dd0-103">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="a1dd0-104">Ahora <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> actualiza el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> a la dirección local del socket.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a1dd0-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a1dd0-105">Version introduced</span></span>

<span data-ttu-id="a1dd0-106">5.0</span><span class="sxs-lookup"><span data-stu-id="a1dd0-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="a1dd0-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a1dd0-107">Change description</span></span>

<span data-ttu-id="a1dd0-108">En versiones anteriores de .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> no modifica el valor de la propiedad <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> en la instancia del socket.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-108">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="a1dd0-109">A partir de .NET 5, cuando <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> se completa de forma correcta, el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> es la dirección local del socket enlazado de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-109">Starting in .NET 5, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="a1dd0-110">Este nuevo comportamiento es coherente con el de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> y <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-110">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a1dd0-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a1dd0-111">Reason for change</span></span>

<span data-ttu-id="a1dd0-112">Este cambio [corrige un error](https://github.com/dotnet/runtime/issues/915) y hace que el comportamiento sea coherente entre las variantes de `SendTo`.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-112">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a1dd0-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a1dd0-113">Recommended action</span></span>

<span data-ttu-id="a1dd0-114">Modifique cualquier código en el que se asuma que <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> no modificará el valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1dd0-114">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a1dd0-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a1dd0-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
