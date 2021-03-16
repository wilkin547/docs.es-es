---
title: 'Cambio importante: StringInfo y TextElementEnumerator ahora son compatibles con UAX29'
description: Obtenga información sobre el cambio importante de globalización en .NET 5, donde StringInfo y TextElementEnumerator procesan los clústeres de grafemas según la versión más reciente del estándar Unicode.
ms.date: 04/07/2020
ms.openlocfilehash: cf770e30bfadf1973bbe018cc9d2783ed6234723
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256710"
---
# <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="748b2-103">StringInfo y TextElementEnumerator ahora son compatibles con UAX29</span><span class="sxs-lookup"><span data-stu-id="748b2-103">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="748b2-104">Antes de este cambio, <xref:System.Globalization.StringInfo?displayProperty=fullName> y <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> no trataban correctamente todos los clústeres de grafemas.</span><span class="sxs-lookup"><span data-stu-id="748b2-104">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="748b2-105">Algunos grafemas se dividieron en sus componentes constituyentes en lugar de mantenerse juntos.</span><span class="sxs-lookup"><span data-stu-id="748b2-105">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="748b2-106">Ahora, <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> procesan los clústeres de grafemas de acuerdo con la versión más reciente del estándar Unicode.</span><span class="sxs-lookup"><span data-stu-id="748b2-106">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="748b2-107">Además, el método <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>, que invierte los caracteres de una cadena en Visual Basic, ahora también sigue el estándar Unicode para los clústeres de grafemas.</span><span class="sxs-lookup"><span data-stu-id="748b2-107">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

## <a name="change-description"></a><span data-ttu-id="748b2-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="748b2-108">Change description</span></span>

<span data-ttu-id="748b2-109">Un [grafema](https://www.unicode.org/glossary/#grapheme) o [clúster de grafemas ampliado](https://www.unicode.org/glossary/#extended_grapheme_cluster) es un único carácter que percibe el usuario y que puede estar formado por varios puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="748b2-109">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="748b2-110">Por ejemplo, la cadena que contiene el carácter tailandés "kam" (:::no-loc text="กำ":::) consta de los dos caracteres siguientes:</span><span class="sxs-lookup"><span data-stu-id="748b2-110">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="748b2-111">:::no-loc text="ก"::: (= '\u0e01') CARÁCTER TAILANDÉS KO KAI</span><span class="sxs-lookup"><span data-stu-id="748b2-111">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="748b2-112">:::no-loc text=" ำ"::: (= '\u0e33') CARÁCTER TAILANDÉS SARA AM</span><span class="sxs-lookup"><span data-stu-id="748b2-112">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="748b2-113">Cuando se muestra al usuario, el sistema operativo combina los dos caracteres para formar el único carácter de presentación (o grafema) "kam" o :::no-loc text="กำ":::.</span><span class="sxs-lookup"><span data-stu-id="748b2-113">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="748b2-114">El emoji también puede constar de varios caracteres que se combinan para mostrarse de forma similar.</span><span class="sxs-lookup"><span data-stu-id="748b2-114">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="748b2-115">En ocasiones, la documentación de .NET usa el término "elemento de texto" al hacer referencia a un grafema.</span><span class="sxs-lookup"><span data-stu-id="748b2-115">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="748b2-116">Las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> inspeccionan las cadenas y devuelven información sobre los grafemas que contienen.</span><span class="sxs-lookup"><span data-stu-id="748b2-116">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="748b2-117">En .NET Framework (todas las versiones) y .NET Core 3.x y versiones anteriores, estas dos clases usan una lógica personalizada que controla algunas clases de combinación, pero no cumple totalmente con el [estándar Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span><span class="sxs-lookup"><span data-stu-id="748b2-117">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="748b2-118">Por ejemplo, las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> dividen incorrectamente el carácter tailandés "kam" de nuevo en sus componentes constituyentes en lugar de mantenerlos juntos.</span><span class="sxs-lookup"><span data-stu-id="748b2-118">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="748b2-119">Estas clases también dividen incorrectamente el carácter "🤷🏽 ♀️" de emoji en cuatro clústeres (persona encogiéndose de hombros, modificador del tono de piel, modificador de género y un combinador invisible) en lugar de mantenerlos juntos como un único clúster de grafemas.</span><span class="sxs-lookup"><span data-stu-id="748b2-119">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="748b2-120">A partir de .NET 5, las clases <xref:System.Globalization.StringInfo> y <xref:System.Globalization.TextElementEnumerator> implementan el estándar Unicode, tal y como se define en el [anexo del estándar Unicode \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span><span class="sxs-lookup"><span data-stu-id="748b2-120">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="748b2-121">En concreto, ahora devuelven [clústeres de grafemas ampliados](https://www.unicode.org/glossary/#extended_grapheme_cluster) para todas las clases que se combinan.</span><span class="sxs-lookup"><span data-stu-id="748b2-121">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="748b2-122">Observe el código C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="748b2-122">Consider the following C# code:</span></span>

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="748b2-123">En .NET Framework y .NET Core 3.x y versiones anteriores, los grafemas se dividen y el resultado de la consola es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="748b2-123">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="748b2-124">En .NET 5 y versiones posteriores, los grafemas se mantienen juntos y el resultado de la consola es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="748b2-124">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="748b2-125">Además, a partir de .NET 5, el método <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>, que invierte los caracteres de una cadena en Visual Basic, ahora también sigue el estándar Unicode para los clústeres de grafemas.</span><span class="sxs-lookup"><span data-stu-id="748b2-125">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="748b2-126">Estos cambios forman parte de un conjunto más amplio de mejoras de Unicode y UTF-8 en .NET, incluida una API de enumeración de clústeres extendidos de grafemas para complementar las API de enumeración de valores escalares de Unicode que se introdujeron con el tipo de <xref:System.Text.Rune?displayProperty=fullName> en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="748b2-126">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="748b2-127">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="748b2-127">Version introduced</span></span>

<span data-ttu-id="748b2-128">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="748b2-128">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="748b2-129">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="748b2-129">Recommended action</span></span>

<span data-ttu-id="748b2-130">No tiene que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="748b2-130">You don't need to take any action.</span></span> <span data-ttu-id="748b2-131">Las aplicaciones se comportarán automáticamente de forma más conforme a los estándares en diversos escenarios relacionados con la globalización.</span><span class="sxs-lookup"><span data-stu-id="748b2-131">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="748b2-132">API afectadas</span><span class="sxs-lookup"><span data-stu-id="748b2-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

### Category

Globalization

-->
