---
title: '$ - Interpolación de cadenas: Referencia de C#'
ms.custom: seodec18
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 03/26/2018
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
ms.openlocfilehash: 64728182fe0b758f8da668d19761305e2001f1a5
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920901"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="8e0bf-103">$ - Interpolación de cadenas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8e0bf-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="8e0bf-104">El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="8e0bf-105">Una cadena interpolada es un literal de cadena que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-105">An interpolated string is a string literal that might contain *interpolated expressions*.</span></span> <span data-ttu-id="8e0bf-106">Cuando una cadena interpolada se resuelve en una cadena de resultado, los elementos con expresiones interpoladas se reemplazan por las representaciones de cadena de los resultados de la expresión.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-106">When an interpolated string is resolved to a result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="8e0bf-107">Esta característica está disponible en C# 6 y versiones posteriores del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="8e0bf-108">La interpolación de cadenas proporciona una sintaxis más legible y cómoda de crear cadenas con formato que si se usa la característica de [formato compuesto de cadena](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="8e0bf-109">En este ejemplo se usan ambas características para producir el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="8e0bf-110">Estructura de una cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="8e0bf-110">Structure of an interpolated string</span></span>

<span data-ttu-id="8e0bf-111">Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="8e0bf-112">No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="8e0bf-113">Si hay alguno, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="8e0bf-114">La estructura de un elemento con una expresión interpolada es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-114">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="8e0bf-115">Los elementos entre corchetes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="8e0bf-116">En esta tabla se describe cada elemento:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-116">The following table describes each element:</span></span>

|<span data-ttu-id="8e0bf-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e0bf-117">Element</span></span>|<span data-ttu-id="8e0bf-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e0bf-118">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="8e0bf-119">Expresión que genera un resultado al que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="8e0bf-120">La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="8e0bf-121">La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="8e0bf-122">Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="8e0bf-123">Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="8e0bf-124">Cadena de formato compatible con el tipo de resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="8e0bf-125">Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="8e0bf-126">En el ejemplo siguiente, se usan componentes opcionales de formato que se han descrito anteriormente:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="8e0bf-127">Caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="8e0bf-127">Special characters</span></span>

<span data-ttu-id="8e0bf-128">Para incluir una llave ("{" o "}") en el texto generado por una cadena interpolada, use dos llaves ("{{" o "}}").</span><span class="sxs-lookup"><span data-stu-id="8e0bf-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="8e0bf-129">Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="8e0bf-130">Como los dos puntos (":") tienen un significado especial en un elemento de expresión interpolada, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión interpolada, incluya esa expresión entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-130">As the colon (":") has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="8e0bf-131">En este ejemplo, se muestra cómo incluir una llave en una cadena de resultado y cómo usar un operador condicional en una expresión interpolada:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="8e0bf-132">Las cadenas interpoladas textuales comienzan por el carácter `$`, seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="8e0bf-133">Para más información sobre las cadenas textuales, vea los temas [string](../keywords/string.md) e [Identificador textual](verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="8e0bf-134">El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="8e0bf-135">Conversiones implícitas y especificar una implementación de `IFormatProvider`</span><span class="sxs-lookup"><span data-stu-id="8e0bf-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="8e0bf-136">Hay tres conversiones implícitas de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="8e0bf-137">Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión interpolada que se reemplazan con las representaciones de cadena con formato correcto de sus resultados.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="8e0bf-138">Esta conversión usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="8e0bf-139">Conversión de una cadena interpolada a una instancia <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="8e0bf-140">Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="8e0bf-141">Para ello, llame a uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="8e0bf-142">Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="8e0bf-143">Método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="8e0bf-144">Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="8e0bf-145">También puede usar el método <xref:System.FormattableString.ToString(System.IFormatProvider)> para proporcionar una implementación definido por el usuario de la interfaz <xref:System.IFormatProvider> que admite formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="8e0bf-146">Para más información, vea [Formato personalizado con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="8e0bf-147">Conversión de una cadena interpolada a una instancia <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="8e0bf-148">En el ejemplo siguiente, se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:</span><span class="sxs-lookup"><span data-stu-id="8e0bf-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="8e0bf-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8e0bf-149">Additional resources</span></span>

<span data-ttu-id="8e0bf-150">Si no está familiarizado con la interpolación de cadenas, vea el tutorial interactivo [Interpolación de cadenas en C#](../../tutorials/exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="8e0bf-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="8e0bf-151">O bien, puede probar el tutorial [Interpolación de cadenas en C# ](../../tutorials/string-interpolation.md) localmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8e0bf-151">Or you can try the  [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial locally on your machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e0bf-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e0bf-152">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="8e0bf-153">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="8e0bf-153">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="8e0bf-154">Tabla de formatos de presentación para resultados numéricos</span><span class="sxs-lookup"><span data-stu-id="8e0bf-154">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="8e0bf-155">Cadenas</span><span class="sxs-lookup"><span data-stu-id="8e0bf-155">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="8e0bf-156">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8e0bf-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8e0bf-157">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="8e0bf-157">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="8e0bf-158">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8e0bf-158">C# Reference</span></span>](../index.md)
