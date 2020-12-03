---
title: 'Cambio importante: El valor de FrameworkDescription es .NET en lugar de .NET Core'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET, donde RuntimeInformation.FrameworkDescription ahora devuelve ".NET" en lugar de ".NET Core".
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760203"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="38090-103">El valor de FrameworkDescription es .NET en lugar de .NET Core</span><span class="sxs-lookup"><span data-stu-id="38090-103">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="38090-104">Ahora <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" en lugar de ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="38090-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

## <a name="change-description"></a><span data-ttu-id="38090-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="38090-105">Change description</span></span>

<span data-ttu-id="38090-106">En versiones anteriores de .NET, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET Core" como parte de la cadena de descripción, por ejemplo, `.NET Core 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="38090-106">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="38090-107">A partir de .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" como parte de la cadena de descripción, por ejemplo, `.NET 5.0.0`.</span><span class="sxs-lookup"><span data-stu-id="38090-107">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="38090-108">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="38090-108">Reason for change</span></span>

<span data-ttu-id="38090-109">Con .NET 5, `netcoreapp` se reemplaza por `net` como el moniker corto del marco de destino.</span><span class="sxs-lookup"><span data-stu-id="38090-109">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="38090-110">Por coherencia, también se ha actualizado la descripción del marco.</span><span class="sxs-lookup"><span data-stu-id="38090-110">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="38090-111">El cambio es cosmético, ya que `FrameworkName` solo se codifica en la propiedad <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="38090-111">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="38090-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="38090-112">Version introduced</span></span>

<span data-ttu-id="38090-113">5.0</span><span class="sxs-lookup"><span data-stu-id="38090-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="38090-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="38090-114">Recommended action</span></span>

<span data-ttu-id="38090-115">Actualice cualquier código que busque ".NET Core" en la cadena devuelta por <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span><span class="sxs-lookup"><span data-stu-id="38090-115">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="38090-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="38090-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
