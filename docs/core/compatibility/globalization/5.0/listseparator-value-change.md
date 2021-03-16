---
title: 'Cambio importante: Cambio de valor de TextInfo.ListSeparator'
description: Obtenga información sobre el cambio importante de .NET 5 en el que el valor predeterminado de TextInfo.ListSeparator se ha cambiado entre las versiones 5.0 y 5.0.1.
ms.date: 12/10/2020
ms.openlocfilehash: 9a319da8ea8e3cbf62cbf4730e553b03f5bfdc89
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256730"
---
# <a name="textinfolistseparator-values-changed"></a><span data-ttu-id="bfea2-103">Cambio de los valores de TextInfo.ListSeparator</span><span class="sxs-lookup"><span data-stu-id="bfea2-103">TextInfo.ListSeparator values changed</span></span>

<span data-ttu-id="bfea2-104">Los valores predeterminados de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para las distintas referencias culturales han cambiado en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="bfea2-104">The default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures have changed on all operating systems.</span></span>

## <a name="change-description"></a><span data-ttu-id="bfea2-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="bfea2-105">Change description</span></span>

<span data-ttu-id="bfea2-106">En .NET 5.0.0, como parte del [cambio de NLS a bibliotecas de ICU](icu-globalization-api.md), se cambiaron los valores predeterminados de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para las distintas referencias culturales en Windows.</span><span class="sxs-lookup"><span data-stu-id="bfea2-106">In .NET 5.0.0, as part of the [switch from NLS to ICU libraries](icu-globalization-api.md), the default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures changed on Windows.</span></span> <span data-ttu-id="bfea2-107">Los valores de separador decimal, obtenidos de los componentes internacionales para Unicode (ICU), se usaban como valores de <xref:System.Globalization.TextInfo.ListSeparator>.</span><span class="sxs-lookup"><span data-stu-id="bfea2-107">Decimal separator values, obtained from International Components for Unicode (ICU), were used as the <xref:System.Globalization.TextInfo.ListSeparator> values.</span></span> <span data-ttu-id="bfea2-108">En Linux y macOS, no se produjo ningún cambio en los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>, es decir, se siguieron usando valores de separador decimal.</span><span class="sxs-lookup"><span data-stu-id="bfea2-108">On Linux and macOS, there was no change in <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values; that is, they continued to use decimal separator values.</span></span>

<span data-ttu-id="bfea2-109">Para todos los sistemas operativos en .NET 5.0.1 y versiones posteriores, los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> son equivalentes a los valores que se obtendrían de NLS.</span><span class="sxs-lookup"><span data-stu-id="bfea2-109">For all operating systems in .NET 5.0.1 and later versions, the values for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> are equivalent to the values that would be obtained from NLS.</span></span> <span data-ttu-id="bfea2-110">En Windows, esto significa que los valores son equivalentes a los de .NET Framework y .NET Core 1.0 a 3.1.</span><span class="sxs-lookup"><span data-stu-id="bfea2-110">For Windows, this means the values are equivalent to what they were in .NET Framework and .NET Core 1.0 - 3.1.</span></span> <span data-ttu-id="bfea2-111">Para Linux y macOS, los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> coinciden ahora coinciden con los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para Windows.</span><span class="sxs-lookup"><span data-stu-id="bfea2-111">For Linux and macOS, the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values now match the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for Windows.</span></span>

<span data-ttu-id="bfea2-112">En la tabla siguiente se resumen los cambios en los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bfea2-112">The following table summarizes the changes for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

| | <span data-ttu-id="bfea2-113">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="bfea2-113">.NET Framework</span></span><br/><span data-ttu-id="bfea2-114">.NET Core 1.0 a 3.1</span><span class="sxs-lookup"><span data-stu-id="bfea2-114">.NET Core 1.0 - 3.1</span></span> | <span data-ttu-id="bfea2-115">.NET 5</span><span class="sxs-lookup"><span data-stu-id="bfea2-115">.NET 5</span></span> | <span data-ttu-id="bfea2-116">.NET 5.0.1</span><span class="sxs-lookup"><span data-stu-id="bfea2-116">.NET 5.0.1</span></span> |
-|-|-|-
| <span data-ttu-id="bfea2-117">**Windows**</span><span class="sxs-lookup"><span data-stu-id="bfea2-117">**Windows**</span></span> | <span data-ttu-id="bfea2-118">Obtenidos de NLS</span><span class="sxs-lookup"><span data-stu-id="bfea2-118">Obtain from NLS</span></span> | <span data-ttu-id="bfea2-119">Separador decimal de ICU</span><span class="sxs-lookup"><span data-stu-id="bfea2-119">Decimal separator from ICU.</span></span><br/><span data-ttu-id="bfea2-120">(Se puede volver a NLS)</span><span class="sxs-lookup"><span data-stu-id="bfea2-120">Can switch back to NLS.</span></span> | <span data-ttu-id="bfea2-121">Equivalentes a NLS</span><span class="sxs-lookup"><span data-stu-id="bfea2-121">Equivalent to NLS</span></span> |
| <span data-ttu-id="bfea2-122">**Linux y macOS**</span><span class="sxs-lookup"><span data-stu-id="bfea2-122">**Linux and macOS**</span></span> | <span data-ttu-id="bfea2-123">Separador decimal de ICU</span><span class="sxs-lookup"><span data-stu-id="bfea2-123">Decimal separator from ICU</span></span> | <span data-ttu-id="bfea2-124">Separador decimal de ICU</span><span class="sxs-lookup"><span data-stu-id="bfea2-124">Decimal separator from ICU</span></span> | <span data-ttu-id="bfea2-125">Equivalentes a NLS</span><span class="sxs-lookup"><span data-stu-id="bfea2-125">Equivalent to NLS</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="bfea2-126">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bfea2-126">Version introduced</span></span>

<span data-ttu-id="bfea2-127">5.0.1</span><span class="sxs-lookup"><span data-stu-id="bfea2-127">5.0.1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="bfea2-128">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="bfea2-128">Reason for change</span></span>

<span data-ttu-id="bfea2-129">Los desarrolladores informaron de que, al usar la propiedad <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para analizar archivos de valores separados por comas (CSV), los nuevos valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> interrumpían ese análisis.</span><span class="sxs-lookup"><span data-stu-id="bfea2-129">Developers reported that they use the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> property when parsing comma-separated value (CSV) files, and the new <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values broke that parsing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bfea2-130">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="bfea2-130">Recommended action</span></span>

<span data-ttu-id="bfea2-131">Si su código se basa en los valores de separador decimal anteriores, puede codificar los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> deseados.</span><span class="sxs-lookup"><span data-stu-id="bfea2-131">If your code relies on the previous decimal separator values, you can hardcode the desired <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bfea2-132">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bfea2-132">Affected APIs</span></span>

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
