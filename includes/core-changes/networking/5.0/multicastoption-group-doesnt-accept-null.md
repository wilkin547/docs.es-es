---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557975"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="637d5-101">MulticastOption.Group no acepta un valor NULL</span><span class="sxs-lookup"><span data-stu-id="637d5-101">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="637d5-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> ya no acepta un valor de `null`.</span><span class="sxs-lookup"><span data-stu-id="637d5-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="637d5-103">Si establece la propiedad en `null`, se inicia <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="637d5-103">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="637d5-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="637d5-104">Version introduced</span></span>

<span data-ttu-id="637d5-105">5.0</span><span class="sxs-lookup"><span data-stu-id="637d5-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="637d5-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="637d5-106">Change description</span></span>

<span data-ttu-id="637d5-107">En versiones anteriores de .NET, puede establecer la propiedad <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`.</span><span class="sxs-lookup"><span data-stu-id="637d5-107">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="637d5-108">Si después se pasa <xref:System.Net.Sockets.MulticastOption> a <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, el entorno de ejecución genera <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="637d5-108">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="637d5-109">En .NET 5.0 y versiones posteriores, se genera <xref:System.ArgumentNullException> si establece la propiedad en `null`.</span><span class="sxs-lookup"><span data-stu-id="637d5-109">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="637d5-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="637d5-110">Reason for change</span></span>

<span data-ttu-id="637d5-111">Por coherencia con las directrices de diseño de .NET Framework, la propiedad se ha actualizado para generar <xref:System.ArgumentNullException> si el valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="637d5-111">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="637d5-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="637d5-112">Recommended action</span></span>

<span data-ttu-id="637d5-113">Asegúrese de que no establece <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`.</span><span class="sxs-lookup"><span data-stu-id="637d5-113">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="637d5-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="637d5-114">Category</span></span>

<span data-ttu-id="637d5-115">Redes</span><span class="sxs-lookup"><span data-stu-id="637d5-115">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="637d5-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="637d5-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
