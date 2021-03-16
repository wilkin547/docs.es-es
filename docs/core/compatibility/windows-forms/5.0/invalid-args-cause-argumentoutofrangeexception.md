---
title: 'Cambio importante: Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException'
description: Obtenga información sobre el cambio importante en .NET 5 por el que algunas propiedades de Windows Forms ahora inician una excepción ArgumentOutOfRangeException para los argumentos no válidos.
ms.date: 06/18/2020
ms.openlocfilehash: 493669af1ed5646d93e7c7d2688afd40f3fa731c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256158"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="28457-103">Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="28457-103">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="28457-104">Algunas propiedades de Windows Forms inician ahora una excepción <xref:System.ArgumentOutOfRangeException> en los argumentos no válidos, donde antes no lo hacían.</span><span class="sxs-lookup"><span data-stu-id="28457-104">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="28457-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="28457-105">Change description</span></span>

<span data-ttu-id="28457-106">Anteriormente, estas propiedades producían varias excepciones, como <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>o <xref:System.ArgumentException>, cuando se pasaban argumentos fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="28457-106">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="28457-107">A partir de .NET 5, estas propiedades producen ahora <xref:System.ArgumentOutOfRangeException> cuando se pasan argumentos que están fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="28457-107">Starting in .NET 5, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="28457-108">El inicio de una <xref:System.ArgumentOutOfRangeException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="28457-108">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="28457-109">También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.</span><span class="sxs-lookup"><span data-stu-id="28457-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="28457-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="28457-110">Version introduced</span></span>

<span data-ttu-id="28457-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="28457-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="28457-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="28457-112">Recommended action</span></span>

- <span data-ttu-id="28457-113">Actualice el código para evitar pasar argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="28457-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="28457-114">Si es necesario, administre un elemento <xref:System.ArgumentOutOfRangeException> al establecer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="28457-114">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="28457-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="28457-115">Affected APIs</span></span>

<span data-ttu-id="28457-116">En la tabla siguiente se enumeran las propiedades y los parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="28457-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="28457-117">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="28457-117">Property</span></span> | <span data-ttu-id="28457-118">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="28457-118">Parameter name</span></span> | <span data-ttu-id="28457-119">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="28457-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="28457-120">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="28457-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="28457-121">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="28457-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="28457-122">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="28457-122">5.0 Preview 6</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
