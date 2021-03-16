---
title: 'Cambio importante: Categoría Unicode modificada para algunos caracteres del alfabeto latino 1'
description: Obtenga información sobre el cambio importante de globalización en .NET 5, donde los métodos char ahora devuelven la categoría Unicode correcta para los caracteres en el intervalo Latin-1.
ms.date: 04/07/2020
ms.openlocfilehash: 03355c488d2bdae78f989e647c9b5b7913d73649
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256678"
---
# <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="d72f7-103">Categoría Unicode modificada para algunos caracteres del alfabeto latino 1</span><span class="sxs-lookup"><span data-stu-id="d72f7-103">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="d72f7-104">Los métodos <xref:System.Char> ahora devuelven la categoría Unicode correcta para los caracteres del alfabeto latino 1.</span><span class="sxs-lookup"><span data-stu-id="d72f7-104"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="d72f7-105">La categoría coincide con la del estándar Unicode.</span><span class="sxs-lookup"><span data-stu-id="d72f7-105">The category matches that of the Unicode standard.</span></span>

## <a name="change-description"></a><span data-ttu-id="d72f7-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d72f7-106">Change description</span></span>

<span data-ttu-id="d72f7-107">En versiones anteriores de .NET, los métodos <xref:System.Char> usaban una lista fija de categorías Unicode para los caracteres del alfabeto latino 1.</span><span class="sxs-lookup"><span data-stu-id="d72f7-107">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="d72f7-108">Pero el estándar Unicode ha cambiado las categorías de algunos de estos caracteres desde que se implementaron esas API, lo que ha creado una discrepancia.</span><span class="sxs-lookup"><span data-stu-id="d72f7-108">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="d72f7-109">Además, también existía una discrepancia entre las API <xref:System.Char> y <xref:System.Globalization.CharUnicodeInfo>, que siguen el estándar Unicode.</span><span class="sxs-lookup"><span data-stu-id="d72f7-109">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="d72f7-110">En .NET 5 y versiones posteriores, los métodos <xref:System.Char> usan y devuelven la categoría Unicode que coincide con el estándar Unicode para todos los caracteres.</span><span class="sxs-lookup"><span data-stu-id="d72f7-110">In .NET 5 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="d72f7-111">En la tabla siguiente se muestran los caracteres cuyas categorías Unicode han cambiado en .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="d72f7-111">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="d72f7-112">Carácter</span><span class="sxs-lookup"><span data-stu-id="d72f7-112">Character</span></span>    | <span data-ttu-id="d72f7-113">Categoría Unicode</span><span class="sxs-lookup"><span data-stu-id="d72f7-113">Unicode category</span></span><br><span data-ttu-id="d72f7-114">en versiones anteriores de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d72f7-114">in previous .NET versions</span></span> | <span data-ttu-id="d72f7-115">Categoría Unicode</span><span class="sxs-lookup"><span data-stu-id="d72f7-115">Unicode category</span></span><br><span data-ttu-id="d72f7-116">en .NET 5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d72f7-116">in .NET 5 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="d72f7-117">§ (\u00a7)</span><span class="sxs-lookup"><span data-stu-id="d72f7-117">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="d72f7-118">ª (\u00aa)</span><span class="sxs-lookup"><span data-stu-id="d72f7-118">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="d72f7-119">SHY (\u00ad)</span><span class="sxs-lookup"><span data-stu-id="d72f7-119">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="d72f7-120">¶ (\u00b6)</span><span class="sxs-lookup"><span data-stu-id="d72f7-120">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="d72f7-121">º (\u00ba)</span><span class="sxs-lookup"><span data-stu-id="d72f7-121">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

## <a name="version-introduced"></a><span data-ttu-id="d72f7-122">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d72f7-122">Version introduced</span></span>

<span data-ttu-id="d72f7-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d72f7-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d72f7-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d72f7-124">Recommended action</span></span>

<span data-ttu-id="d72f7-125">Si tiene código que obtiene la categoría de caracteres Unicode mediante la clase <xref:System.Char> y supone que la categoría nunca cambia, puede que tenga que actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="d72f7-125">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d72f7-126">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d72f7-126">Reason for change</span></span>

<span data-ttu-id="d72f7-127">Este cambio se ha llevado a cabo para que las categorías devueltas por el tipo <xref:System.Char> sean coherentes con el estándar Unicode y el tipo <xref:System.Globalization.CharUnicodeInfo>.</span><span class="sxs-lookup"><span data-stu-id="d72f7-127">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d72f7-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d72f7-128">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="d72f7-129">Además, cualquier clase que dependa de <xref:System.Char> para obtener la categoría de caracteres Unicode, por ejemplo, <xref:System.Text.RegularExpressions.Regex>, se ve afectada por este cambio.</span><span class="sxs-lookup"><span data-stu-id="d72f7-129">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

### Category

- Core .NET libraries
- Globalization
-
-->
