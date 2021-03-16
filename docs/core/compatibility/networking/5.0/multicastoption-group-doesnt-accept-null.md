---
title: 'Cambio importante: MulticastOption.Group no acepta un valor NULL'
description: Obtenga información sobre el cambio importante en .NET 5, donde MulticastOption.Group ya no acepta un valor NULL.
ms.date: 08/18/2020
ms.openlocfilehash: 09c6415d275361abee8285aabdda13ccd9727043
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256457"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="c3027-103">MulticastOption.Group no acepta un valor NULL</span><span class="sxs-lookup"><span data-stu-id="c3027-103">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="c3027-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> ya no acepta un valor de `null`.</span><span class="sxs-lookup"><span data-stu-id="c3027-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="c3027-105">Si establece la propiedad en `null`, se inicia <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="c3027-105">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c3027-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c3027-106">Version introduced</span></span>

<span data-ttu-id="c3027-107">5.0</span><span class="sxs-lookup"><span data-stu-id="c3027-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="c3027-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c3027-108">Change description</span></span>

<span data-ttu-id="c3027-109">En versiones anteriores de .NET, puede establecer la propiedad <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`.</span><span class="sxs-lookup"><span data-stu-id="c3027-109">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="c3027-110">Si después se pasa <xref:System.Net.Sockets.MulticastOption> a <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, el entorno de ejecución genera <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="c3027-110">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="c3027-111">En .NET 5 y versiones posteriores, se genera <xref:System.ArgumentNullException> si establece la propiedad en `null`.</span><span class="sxs-lookup"><span data-stu-id="c3027-111">In .NET 5 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c3027-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c3027-112">Reason for change</span></span>

<span data-ttu-id="c3027-113">Por coherencia con las directrices de diseño de .NET Framework, la propiedad se ha actualizado para generar <xref:System.ArgumentNullException> si el valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="c3027-113">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c3027-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c3027-114">Recommended action</span></span>

<span data-ttu-id="c3027-115">Asegúrese de que no establece <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`.</span><span class="sxs-lookup"><span data-stu-id="c3027-115">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c3027-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c3027-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
