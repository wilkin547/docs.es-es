---
ms.openlocfilehash: 1d8bcaf68d44f27642048c1c207b52c55b604690
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901747"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="9f75a-101">SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="9f75a-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="9f75a-102">El campo [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) se ha quitado y se ha reemplazado por un método auxiliar que genera una respuesta de protocolo de enlace correcta dado un protocolo `IHubProtocol` específico.</span><span class="sxs-lookup"><span data-stu-id="9f75a-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f75a-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9f75a-103">Version introduced</span></span>

<span data-ttu-id="9f75a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="9f75a-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9f75a-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="9f75a-105">Old behavior</span></span>

<span data-ttu-id="9f75a-106">`HandshakeProtocol.SuccessHandshakeData` era un campo `public static ReadOnlyMemory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="9f75a-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9f75a-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="9f75a-107">New behavior</span></span>

<span data-ttu-id="9f75a-108">`HandshakeProtocol.SuccessHandshakeData` se ha reemplazado por un método `GetSuccessfulHandshake(IHubProtocol protocol)``static` que devuelve un objeto `ReadOnlyMemory<byte>` basado en el protocolo especificado.</span><span class="sxs-lookup"><span data-stu-id="9f75a-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9f75a-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="9f75a-109">Reason for change</span></span>

<span data-ttu-id="9f75a-110">Se han agregado campos adicionales a la _respuesta_ del protocolo de enlace que no son constantes y cambian en función del protocolo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9f75a-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f75a-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9f75a-111">Recommended action</span></span>

<span data-ttu-id="9f75a-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9f75a-112">None.</span></span> <span data-ttu-id="9f75a-113">Este tipo no está diseñado para su uso desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f75a-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="9f75a-114">Es `public`, por lo que se puede compartir entre el servidor de SignalR y el cliente.</span><span class="sxs-lookup"><span data-stu-id="9f75a-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="9f75a-115">También lo pueden usar clientes de SignalR personalizados escritos en .NET.</span><span class="sxs-lookup"><span data-stu-id="9f75a-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="9f75a-116">Los **usuarios** de SignalR no deberían verse afectados por este cambio.</span><span class="sxs-lookup"><span data-stu-id="9f75a-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="9f75a-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="9f75a-117">Category</span></span>

<span data-ttu-id="9f75a-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9f75a-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f75a-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9f75a-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
