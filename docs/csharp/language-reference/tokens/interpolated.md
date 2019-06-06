---
title: '$ - Interpolación de cadenas: Referencia de C#'
ms.custom: seodec18
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 04/29/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: bc27eedcf1957a109a9bcb80cf9a49e9606921fd
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250997"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="09aef-103">$ - Interpolación de cadenas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="09aef-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="09aef-104">El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="09aef-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="09aef-105">Una cadena interpolada es un literal de cadena que puede contener *expresiones de interpolación*.</span><span class="sxs-lookup"><span data-stu-id="09aef-105">An interpolated string is a string literal that might contain *interpolation expressions*.</span></span> <span data-ttu-id="09aef-106">Cuando una cadena interpolada se resuelve en una cadena de resultado, los elementos con expresiones de interpolación se reemplazan por las representaciones de cadena de los resultados de la expresión.</span><span class="sxs-lookup"><span data-stu-id="09aef-106">When an interpolated string is resolved to a result string, items with interpolation expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="09aef-107">Esta característica está disponible en C# 6 y versiones posteriores del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="09aef-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="09aef-108">La interpolación de cadenas proporciona una sintaxis más legible y cómoda de crear cadenas con formato que si se usa la característica de [formato compuesto de cadena](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="09aef-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="09aef-109">En este ejemplo se usan ambas características para producir el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="09aef-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="09aef-110">Estructura de una cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="09aef-110">Structure of an interpolated string</span></span>

<span data-ttu-id="09aef-111">Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="09aef-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="09aef-112">No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="09aef-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="09aef-113">Si hay alguno, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="09aef-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="09aef-114">La estructura de un elemento con una expresión de interpolación es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="09aef-114">The structure of an item with an interpolation expression is as follows:</span></span>

```
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="09aef-115">Los elementos entre corchetes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="09aef-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="09aef-116">En esta tabla se describe cada elemento:</span><span class="sxs-lookup"><span data-stu-id="09aef-116">The following table describes each element:</span></span>

|<span data-ttu-id="09aef-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="09aef-117">Element</span></span>|<span data-ttu-id="09aef-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="09aef-118">Description</span></span>|
|-------------|-----------------|
|`interpolationExpression`|<span data-ttu-id="09aef-119">Expresión que genera un resultado al que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="09aef-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="09aef-120">La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09aef-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="09aef-121">La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión de interpolación.</span><span class="sxs-lookup"><span data-stu-id="09aef-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolation expression.</span></span> <span data-ttu-id="09aef-122">Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="09aef-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="09aef-123">Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="09aef-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="09aef-124">Cadena de formato compatible con el tipo de resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="09aef-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="09aef-125">Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="09aef-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="09aef-126">En el ejemplo siguiente, se usan componentes opcionales de formato que se han descrito anteriormente:</span><span class="sxs-lookup"><span data-stu-id="09aef-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="09aef-127">Caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="09aef-127">Special characters</span></span>

<span data-ttu-id="09aef-128">Para incluir una llave ("{" o "}") en el texto generado por una cadena interpolada, use dos llaves ("{{" o "}}").</span><span class="sxs-lookup"><span data-stu-id="09aef-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="09aef-129">Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="09aef-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="09aef-130">Como los dos puntos (":") tienen un significado especial en un elemento de expresión de interpolación, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión de interpolación, incluya esa expresión entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="09aef-130">As the colon (":") has special meaning in an interpolation expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolation expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="09aef-131">En este ejemplo, se muestra cómo incluir una llave en una cadena de resultado y cómo usar un operador condicional en una expresión de interpolación:</span><span class="sxs-lookup"><span data-stu-id="09aef-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolation expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="09aef-132">Las cadenas interpoladas textuales comienzan por el carácter `$`, seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="09aef-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="09aef-133">Para más información sobre las cadenas textuales, vea los temas [string](../keywords/string.md) e [Identificador textual](verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="09aef-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="09aef-134">El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.</span><span class="sxs-lookup"><span data-stu-id="09aef-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="09aef-135">Conversiones implícitas y especificar una implementación de `IFormatProvider`</span><span class="sxs-lookup"><span data-stu-id="09aef-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="09aef-136">Hay tres conversiones implícitas de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="09aef-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="09aef-137">Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión de interpolación que se reemplazan con las representaciones de cadena con formato correcto de sus resultados.</span><span class="sxs-lookup"><span data-stu-id="09aef-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolation expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="09aef-138">Esta conversión usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="09aef-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="09aef-139">Conversión de una cadena interpolada a una instancia <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="09aef-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="09aef-140">Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="09aef-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="09aef-141">Para ello, llame a uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="09aef-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="09aef-142">Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="09aef-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="09aef-143">Método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="09aef-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="09aef-144">Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="09aef-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="09aef-145">También puede usar el método <xref:System.FormattableString.ToString(System.IFormatProvider)> para proporcionar una implementación definido por el usuario de la interfaz <xref:System.IFormatProvider> que admite formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="09aef-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="09aef-146">Para más información, vea [Formato personalizado con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="09aef-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="09aef-147">Conversión de una cadena interpolada a una instancia <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="09aef-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="09aef-148">En el ejemplo siguiente, se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:</span><span class="sxs-lookup"><span data-stu-id="09aef-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="09aef-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="09aef-149">Additional resources</span></span>

<span data-ttu-id="09aef-150">Si no está familiarizado con la interpolación de cadenas, vea el tutorial interactivo [Interpolación de cadenas en C#](../../tutorials/exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="09aef-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="09aef-151">También puede consultar otro tutorial de [interpolación de cadenas en C#](../../tutorials/string-interpolation.md) que muestra cómo usar cadenas interpoladas para generar cadenas con formato.</span><span class="sxs-lookup"><span data-stu-id="09aef-151">You also can check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="09aef-152">Compilación de cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="09aef-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="09aef-153">Si una cadena interpolada tiene el tipo `string`, normalmente se transforma en una llamada de método <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09aef-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="09aef-154">El compilador puede reemplazar <xref:System.String.Format%2A?displayProperty=nameWithType> por <xref:System.String.Concat%2A?displayProperty=nameWithType> si el comportamiento analizado es equivalente a una concatenación.</span><span class="sxs-lookup"><span data-stu-id="09aef-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="09aef-155">Si una cadena interpolada tiene el tipo <xref:System.IFormattable> o <xref:System.FormattableString>, el compilador genera una llamada al método <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09aef-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09aef-156">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="09aef-156">C# language specification</span></span>

<span data-ttu-id="09aef-157">Para obtener más información, vea la sección [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) (Cadenas interpoladas) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="09aef-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09aef-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="09aef-158">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="09aef-159">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="09aef-159">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="09aef-160">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="09aef-160">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="09aef-161">Cadenas</span><span class="sxs-lookup"><span data-stu-id="09aef-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="09aef-162">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="09aef-162">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="09aef-163">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="09aef-163">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="09aef-164">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="09aef-164">C# Reference</span></span>](../index.md)
