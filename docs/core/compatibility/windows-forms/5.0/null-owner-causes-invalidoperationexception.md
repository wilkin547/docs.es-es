---
title: 'Cambio importante: Las API relacionadas con DataGridView inician una excepción InvalidOperationException'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde algunas API relacionadas con DataGridView inician una excepción si el valor de DataGridViewCellAccessibleObject.Owner del objeto es NULL.
ms.date: 09/18/2020
ms.openlocfilehash: 927b1c9160700159a45aa1472b8d96f1a9ecfe25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760229"
---
# <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="2eb1b-103">Excepción InvalidOperationException por parte de las API relacionadas con DataGridView</span><span class="sxs-lookup"><span data-stu-id="2eb1b-103">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="2eb1b-104">Algunas API relacionadas con <xref:System.Windows.Forms.DataGridView> ahora producen una excepción <xref:System.InvalidOperationException> si el valor <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> del objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-104">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

## <a name="change-description"></a><span data-ttu-id="2eb1b-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="2eb1b-105">Change description</span></span>

<span data-ttu-id="2eb1b-106">En las versiones anteriores de .NET, las API afectadas inician una excepción <xref:System.NullReferenceException> cuando se invocan y el valor de <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> es `null`.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="2eb1b-107">A partir de .NET 5.0, estas API inician una excepción <xref:System.InvalidOperationException> en lugar de una excepción <xref:System.NullReferenceException> si el valor de <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> es `null` cuando se invocan.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-107">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="2eb1b-108">El inicio de una <xref:System.InvalidOperationException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-108">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="2eb1b-109">También mejora la experiencia de depuración al comunicar claramente qué propiedad no es válida.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-109">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2eb1b-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2eb1b-110">Version introduced</span></span>

<span data-ttu-id="2eb1b-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2eb1b-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2eb1b-112">Recommended action</span></span>

<span data-ttu-id="2eb1b-113">Revise el código y, si es necesario, actualícelo para evitar la construcción de los tipos afectados con la propiedad <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> como `null`.</span><span class="sxs-lookup"><span data-stu-id="2eb1b-113">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2eb1b-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2eb1b-114">Affected APIs</span></span>

<span data-ttu-id="2eb1b-115">En la tabla siguiente se enumeran las propiedades y los parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="2eb1b-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="2eb1b-116">Propiedad o método afectado</span><span class="sxs-lookup"><span data-stu-id="2eb1b-116">Affected method or property</span></span> | <span data-ttu-id="2eb1b-117">Propiedad validada</span><span class="sxs-lookup"><span data-stu-id="2eb1b-117">Validated property</span></span> | <span data-ttu-id="2eb1b-118">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="2eb1b-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-119">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-120">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-121">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-122">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-123">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-124">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-125">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-126">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-127">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-128">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-129">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="2eb1b-130">5.0</span><span class="sxs-lookup"><span data-stu-id="2eb1b-130">5.0</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

### Category

Windows Forms

-->
