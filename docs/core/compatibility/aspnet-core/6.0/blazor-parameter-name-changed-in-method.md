---
title: 'Cambio importante: Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync.'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: bfaaa6bfe94c32fbc1a5b5b70db863d105d389b5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488265"
---
# <a name="blazor-parameter-name-changed-in-requestimagefileasync-method"></a><span data-ttu-id="e877d-103">Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync</span><span class="sxs-lookup"><span data-stu-id="e877d-103">Blazor: Parameter name changed in RequestImageFileAsync method</span></span>

<span data-ttu-id="e877d-104">Se ha cambiado el nombre del parámetro `maxWith` del método `RequestImageFileAsync` de `maxWith` a `maxWidth`.</span><span class="sxs-lookup"><span data-stu-id="e877d-104">The `RequestImageFileAsync` method's `maxWith` parameter was renamed from `maxWith` to `maxWidth`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e877d-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e877d-105">Version introduced</span></span>

<span data-ttu-id="e877d-106">6.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="e877d-106">6.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="e877d-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="e877d-107">Old behavior</span></span>

<span data-ttu-id="e877d-108">El nombre del parámetro se escribe `maxWith`.</span><span class="sxs-lookup"><span data-stu-id="e877d-108">The parameter name is spelled `maxWith`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="e877d-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="e877d-109">New behavior</span></span>

<span data-ttu-id="e877d-110">El nombre del parámetro se escribe `maxWidth`.</span><span class="sxs-lookup"><span data-stu-id="e877d-110">The parameter name is spelled `maxWidth`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="e877d-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e877d-111">Reason for change</span></span>

<span data-ttu-id="e877d-112">El nombre del parámetro original era un error tipográfico.</span><span class="sxs-lookup"><span data-stu-id="e877d-112">The original parameter name was a typographical error.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e877d-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e877d-113">Recommended action</span></span>

<span data-ttu-id="e877d-114">Si usa parámetros con nombre en la API `RequestImageFile`, actualice el nombre del parámetro `maxWith` a `maxWidth`.</span><span class="sxs-lookup"><span data-stu-id="e877d-114">If you're using named parameters in the `RequestImageFile` API, update the `maxWith` parameter name to `maxWidth`.</span></span> <span data-ttu-id="e877d-115">De lo contrario, no es necesario ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="e877d-115">Otherwise, no change is necessary.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e877d-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e877d-116">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync`

-->
