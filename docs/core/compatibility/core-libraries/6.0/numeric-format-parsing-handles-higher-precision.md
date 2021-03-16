---
title: 'Cambio importante: Precisión del análisis de formato numérico estándar'
description: Obtenga información sobre el cambio importante de .NET 6 en las bibliotecas .NET básicas, donde el análisis de formato numérico estándar ahora maneja precisiones más altas.
ms.date: 02/26/2021
ms.openlocfilehash: ad1555493bbc6198541365132cc421db7c01a5a2
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256925"
---
# <a name="standard-numeric-format-parsing-precision"></a><span data-ttu-id="0f79b-103">Precisión del análisis de formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="0f79b-103">Standard numeric format parsing precision</span></span>

<span data-ttu-id="0f79b-104">.NET ahora admite valores de precisión mayores al dar formato a los números como cadenas mediante `ToString` y `TryFormat`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-104">.NET now supports greater precision values when formatting numbers as strings using `ToString` and `TryFormat`.</span></span>

## <a name="change-description"></a><span data-ttu-id="0f79b-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="0f79b-105">Change description</span></span>

<span data-ttu-id="0f79b-106">Al dar formato a los números como cadenas, el *especificador de precisión* en la [cadena de formato](../../../../standard/base-types/standard-numeric-format-strings.md) representa el número de dígitos de la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="0f79b-106">When formatting numbers as strings, the *precision specifier* in the [format string](../../../../standard/base-types/standard-numeric-format-strings.md) represents the number of digits in the resulting string.</span></span> <span data-ttu-id="0f79b-107">Dependiendo del *especificador de formato*, que es el [carácter situado al principio de la cadena](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers), la precisión puede representar el número total de dígitos, el número de dígitos significativos o el número de dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="0f79b-107">Depending on the *format specifier*, which is the [character at the beginning of the string](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers), the precision can represent the total number of digits, the number of significant digits, or the number of decimal digits.</span></span>

<span data-ttu-id="0f79b-108">En versiones anteriores de .NET, la lógica de análisis de formato numérico estándar se limita a una precisión de 99 o menos.</span><span class="sxs-lookup"><span data-stu-id="0f79b-108">In previous .NET versions, the standard numeric format parsing logic is limited to a precision of 99 or less.</span></span> <span data-ttu-id="0f79b-109">Algunos tipos numéricos tienen más precisión, pero `ToString(string format)` no los expone correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f79b-109">Some numeric types have more precision, but `ToString(string format)` does not expose it correctly.</span></span> <span data-ttu-id="0f79b-110">Si especifica una precisión mayor que 99, por ejemplo `32.ToString("C100")`, la cadena de formato se interpreta como una [cadena de formato numérico personalizado](../../../../standard/base-types/custom-numeric-format-strings.md) en lugar de "moneda con precisión 100".</span><span class="sxs-lookup"><span data-stu-id="0f79b-110">If you specify a precision greater than 99, for example, `32.ToString("C100")`, the format string is interpreted as a [custom numeric format string](../../../../standard/base-types/custom-numeric-format-strings.md) instead of "currency with precision 100".</span></span> <span data-ttu-id="0f79b-111">En las cadenas de formato numérico personalizado, los caracteres se interpretan como [literales de carácter](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals).</span><span class="sxs-lookup"><span data-stu-id="0f79b-111">In custom numeric format strings, characters are interpreted as [character literals](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals).</span></span> <span data-ttu-id="0f79b-112">Además, una cadena de formato que contiene un especificador de formato no válido se interpreta de manera diferente en función del valor de precisión.</span><span class="sxs-lookup"><span data-stu-id="0f79b-112">In addition, a format string that contains an invalid format specifier is interpreted differently depending on the precision value.</span></span> <span data-ttu-id="0f79b-113">`H99` genera <xref:System.FormatException> para el especificador de formato no válido, mientras que `H100` se interpreta como una cadena de formato numérico personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f79b-113">`H99` throws a <xref:System.FormatException> for the invalid format specifier, while `H100` is interpreted as a custom numeric format string.</span></span>

<span data-ttu-id="0f79b-114">A partir de .NET 6, .NET admite una precisión de hasta <xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f79b-114">Starting in .NET 6, .NET supports precision up to <xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f79b-115">Una cadena de formato que consta de un especificador de formato con cualquier número de dígitos se interpreta como una cadena de formato numérico estándar con precisión.</span><span class="sxs-lookup"><span data-stu-id="0f79b-115">A format string that consists of a format specifier with any number of digits is interpreted as a standard numeric format string with precision.</span></span> <span data-ttu-id="0f79b-116">Se produce <xref:System.FormatException> para una o ambas de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f79b-116">A <xref:System.FormatException> is thrown for either or both of the following conditions:</span></span>

- <span data-ttu-id="0f79b-117">El carácter especificador de formato no es un [especificador de formato estándar](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers).</span><span class="sxs-lookup"><span data-stu-id="0f79b-117">The format specifier character is not a [standard format specifier](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers).</span></span>
- <span data-ttu-id="0f79b-118">La precisión es mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f79b-118">The precision is greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0f79b-119">Este cambio se implementó en la lógica de análisis que afecta a todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="0f79b-119">This change was implemented in the parsing logic that affects all numeric types.</span></span>

<span data-ttu-id="0f79b-120">En la tabla siguiente se muestran los cambios de comportamiento de varias cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="0f79b-120">The following table shows the behavior changes for various format strings.</span></span>

| <span data-ttu-id="0f79b-121">Cadena de formato</span><span class="sxs-lookup"><span data-stu-id="0f79b-121">Format string</span></span> | <span data-ttu-id="0f79b-122">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="0f79b-122">Previous behavior</span></span> | <span data-ttu-id="0f79b-123">Comportamiento a partir de .NET 6</span><span class="sxs-lookup"><span data-stu-id="0f79b-123">.NET 6+ behavior</span></span> |
| - | - | - |
| `C2` | <span data-ttu-id="0f79b-124">Denota moneda con dos dígitos decimales</span><span class="sxs-lookup"><span data-stu-id="0f79b-124">Denotes currency with two decimal digits</span></span> | <span data-ttu-id="0f79b-125">Denota moneda con dos dígitos decimales (*sin cambios*)</span><span class="sxs-lookup"><span data-stu-id="0f79b-125">Denotes currency with two decimal digits (*no change*)</span></span> |
| `C100` | <span data-ttu-id="0f79b-126">Denota una cadena de formato numérico personalizado que imprime "C100"</span><span class="sxs-lookup"><span data-stu-id="0f79b-126">Denotes custom numeric format string that prints "C100"</span></span> | <span data-ttu-id="0f79b-127">Denota moneda con 100 dígitos decimales</span><span class="sxs-lookup"><span data-stu-id="0f79b-127">Denotes currency with 100 decimal digits</span></span> |
| `H99` | <span data-ttu-id="0f79b-128">Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H"</span><span class="sxs-lookup"><span data-stu-id="0f79b-128">Throws <xref:System.FormatException> due to invalid standard format specifier "H"</span></span> | <span data-ttu-id="0f79b-129">Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H" (*sin cambios*)</span><span class="sxs-lookup"><span data-stu-id="0f79b-129">Throws <xref:System.FormatException> due to invalid standard format specifier "H" (*no change*)</span></span> |
| `H100` | <span data-ttu-id="0f79b-130">Denota una cadena de formato numérico personalizado</span><span class="sxs-lookup"><span data-stu-id="0f79b-130">Denotes custom numeric format string</span></span> | <span data-ttu-id="0f79b-131">Se produce <xref:System.FormatException> debido al especificador de formato estándar no válido "H"</span><span class="sxs-lookup"><span data-stu-id="0f79b-131">Throws <xref:System.FormatException> due to invalid standard format specifier "H"</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="0f79b-132">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0f79b-132">Version introduced</span></span>

<span data-ttu-id="0f79b-133">6.0 (versión preliminar 2)</span><span class="sxs-lookup"><span data-stu-id="0f79b-133">6.0 Preview 2</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0f79b-134">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="0f79b-134">Reason for change</span></span>

<span data-ttu-id="0f79b-135">Este cambio corrige el comportamiento inesperado al usar una precisión mayor para el análisis de formato numérico.</span><span class="sxs-lookup"><span data-stu-id="0f79b-135">This change corrects unexpected behavior when using higher precision for numeric format parsing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0f79b-136">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="0f79b-136">Recommended action</span></span>

<span data-ttu-id="0f79b-137">En la mayoría de los casos, no es necesario realizar ninguna acción y se mostrará la precisión correcta en las cadenas resultantes.</span><span class="sxs-lookup"><span data-stu-id="0f79b-137">In most cases, no action is necessary and the correct precision will be shown in the resulting strings.</span></span>

<span data-ttu-id="0f79b-138">Sin embargo, si desea revertir al comportamiento anterior en el que el especificador de formato se interpreta como un carácter literal cuando la precisión es mayor que 99, puede especificar ese carácter entre comillas simples o escaparlo con una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="0f79b-138">However, if you want to revert to the previous behavior where the format specifier is interpreted as a literal character when the precision is greater than 99, you can wrap that character in single quotes or escape it with a backslash.</span></span> <span data-ttu-id="0f79b-139">Por ejemplo, en versiones anteriores de .NET, `42.ToString("G999")` devuelve `G999`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-139">For example, in previous .NET versions, `42.ToString("G999")` returns `G999`.</span></span> <span data-ttu-id="0f79b-140">Para mantener ese comportamiento, cambie la cadena de formato a `"'G'999"` o `"\\G999"`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-140">To maintain that behavior, change the format string to `"'G'999"` or `"\\G999"`.</span></span> <span data-ttu-id="0f79b-141">Esto funcionará en .NET Framework, .NET Core y .NET 5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0f79b-141">This will work on .NET Framework, .NET Core, and .NET 5+.</span></span>

<span data-ttu-id="0f79b-142">Las cadenas de formato siguientes se seguirán interpretando como cadenas de formato numérico personalizado:</span><span class="sxs-lookup"><span data-stu-id="0f79b-142">The following format strings will continue to be interpreted as custom numeric format strings:</span></span>

- <span data-ttu-id="0f79b-143">Comienzan con cualquier carácter que no sea un carácter alfabético ASCII, por ejemplo `$` o `è`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-143">Start with any character that is not an ASCII alphabetical character, for example, `$` or `è`.</span></span>
- <span data-ttu-id="0f79b-144">Comienzan con un carácter alfabético ASCII no seguido de un dígito ASCII, por ejemplo `A$`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-144">Start with an ASCII alphabetical character that's not followed by an ASCII digit, for example, `A$`.</span></span>
- <span data-ttu-id="0f79b-145">Comienzan con un carácter alfabético ASCII, seguido de una secuencia de dígitos ASCII y, a continuación, cualquier carácter que no sea un carácter de dígito ASCII, por ejemplo `A12A`.</span><span class="sxs-lookup"><span data-stu-id="0f79b-145">Start with an ASCII alphabetical character, followed by an ASCII digit sequence, and then any character that is not an ASCII digit character, for example, `A12A`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0f79b-146">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0f79b-146">Affected APIs</span></span>

<span data-ttu-id="0f79b-147">Este cambio se implementó en la lógica de análisis que afecta a todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="0f79b-147">This change was implemented in the parsing logic that affects all numeric types.</span></span>

- <xref:System.Numerics.BigInteger.ToString(System.String)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="0f79b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f79b-148">See also</span></span>

- [<span data-ttu-id="0f79b-149">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="0f79b-149">Standard numeric format strings</span></span>](../../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="0f79b-150">Literales de carácter en cadenas de formato personalizado</span><span class="sxs-lookup"><span data-stu-id="0f79b-150">Character literals in custom format strings</span></span>](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals)

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.BigInteger.ToString(System.String)`
- `M:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)`
- `M:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int32.ToString(System.String)`
- `M:System.Int32.ToString(System.String,System.IFormatProvider)`
- `M:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt32.ToString(System.String)`
- `M:System.UInt32.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Byte.ToString(System.String)`
- `M:System.Byte.ToString(System.String,System.IFormatProvider)`
- `M:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.SByte.ToString(System.String)`
- `M:System.SByte.ToString(System.String,System.IFormatProvider)`
- `M:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int16.ToString(System.String)`
- `M:System.Int16.ToString(System.String,System.IFormatProvider)`
- `M:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt16.ToString(System.String)`
- `M:System.UInt16.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int64.ToString(System.String)`
- `M:System.Int64.ToString(System.String,System.IFormatProvider)`
- `M:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt64.ToString(System.String)`
- `M:System.UInt64.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Half.ToString(System.String)`
- `M:System.Half.ToString(System.String,System.IFormatProvider)`
- `M:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Single.ToString(System.String)`
- `M:System.Single.ToString(System.String,System.IFormatProvider)`
- `M:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Double.ToString(System.String)`
- `M:System.Double.ToString(System.String,System.IFormatProvider)`
- `M:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Decimal.ToString(System.String)`
- `M:System.Decimal.ToString(System.String,System.IFormatProvider)`
- `M:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`

-->
