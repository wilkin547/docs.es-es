---
title: Interpolación de cadenas en C#
description: Obtenga información sobre cómo incluir resultados de expresión con formato en una cadena de resultado en C# con la interpolación de cadenas.
author: pkulikov
ms.technology: csharp-fundamentals
ms.date: 09/02/2019
ms.openlocfilehash: b901ae661ebd4af625d9f3c999b0eb50dda1990d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73039209"
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="53b34-103">Interpolación de cadenas en C\#</span><span class="sxs-lookup"><span data-stu-id="53b34-103">String interpolation in C\#</span></span>

<span data-ttu-id="53b34-104">En este tutorial se explica cómo usar la [interpolación de cadenas](../language-reference/tokens/interpolated.md) para dar formato a resultados de expresión e incluirlos en una cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="53b34-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="53b34-105">En los ejemplos se da por hecho que ya está familiarizado con los conceptos básicos de C# y el formato de tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="53b34-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="53b34-106">Si no conoce la interpolación de cadenas o el formato de tipos .NET, vea antes el [tutorial de interpolación de cadenas interactivo](exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="53b34-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation tutorial](exploration/interpolated-strings.yml) first.</span></span> <span data-ttu-id="53b34-107">Para más información sobre cómo aplicar formato a tipos .NET, vea el tema [Aplicar formato a tipos en .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="53b34-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="53b34-108">Introduction</span></span>

<span data-ttu-id="53b34-109">La característica de [interpolación de cadenas](../language-reference/tokens/interpolated.md) se basa en la característica de [formato compuesto](../../standard/base-types/composite-formatting.md) y proporciona una sintaxis más legible y cómoda para incluir resultados de expresiones con formato en una cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="53b34-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="53b34-110">Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="53b34-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="53b34-111">Puede insertar cualquier expresión de C# válida que devuelva un valor en una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="53b34-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="53b34-112">En el siguiente ejemplo, en cuanto la expresión se evalúa, su resultado se convierte en una cadena y se incluye en una cadena de resultado:</span><span class="sxs-lookup"><span data-stu-id="53b34-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="53b34-113">Como se ilustra en el ejemplo, para incluir una expresión en una cadena interpolada hay que meterla entre llaves:</span><span class="sxs-lookup"><span data-stu-id="53b34-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```csharp
{<interpolationExpression>}
```

<span data-ttu-id="53b34-114">Las cadenas interpoladas admiten todas las funcionalidades de la característica de [formato compuesto de cadena](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-114">Interpolated strings support all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="53b34-115">Esto las convierte en una alternativa más legible al uso del método <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53b34-115">That makes them a more readable alternative to the use of the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolation-expression"></a><span data-ttu-id="53b34-116">Cómo especificar una cadena de formato para una expresión de interpolación</span><span class="sxs-lookup"><span data-stu-id="53b34-116">How to specify a format string for an interpolation expression</span></span>

<span data-ttu-id="53b34-117">Para especificar una cadena de formato compatible con el tipo de resultado de expresión, coloque después de la expresión de interpolación dos puntos (":") y la cadena de formato:</span><span class="sxs-lookup"><span data-stu-id="53b34-117">You specify a format string that is supported by the type of the expression result by following the interpolation expression with a colon (":") and the format string:</span></span>

```csharp
{<interpolationExpression>:<formatString>}
```

<span data-ttu-id="53b34-118">En el siguiente ejemplo se muestra cómo especificar cadenas de formato estándar y personalizadas para expresiones que generan resultados numéricos o de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="53b34-118">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="53b34-119">Para más información, vea la sección [Format String (Componente)](../../standard/base-types/composite-formatting.md#format-string-component) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-119">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="53b34-120">En esa sección encontrará vínculos a temas en los que se describen las cadenas de formato estándar y personalizadas compatibles con los tipos base .NET.</span><span class="sxs-lookup"><span data-stu-id="53b34-120">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolation-expression"></a><span data-ttu-id="53b34-121">Cómo controlar el ancho de campo y la alineación de las expresiones de interpolación con formato</span><span class="sxs-lookup"><span data-stu-id="53b34-121">How to control the field width and alignment of the formatted interpolation expression</span></span>

<span data-ttu-id="53b34-122">Para especificar el ancho de campo mínimo y la alineación del resultado de expresión con formato, coloque después de la expresión de interpolación una coma (",") y la expresión constante:</span><span class="sxs-lookup"><span data-stu-id="53b34-122">You specify the minimum field width and the alignment of the formatted expression result by following the interpolation expression with a comma (",") and the constant expression:</span></span>

```csharp
{<interpolationExpression>,<alignment>}
```

<span data-ttu-id="53b34-123">Si el valor de *alignment* es positivo, el resultado de la expresión con formato se alineará a la derecha y, si es negativo, lo hará a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="53b34-123">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="53b34-124">En caso de que haya que especificar una alineación y una cadena de formato, comience por el componente de alineación:</span><span class="sxs-lookup"><span data-stu-id="53b34-124">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```csharp
{<interpolationExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="53b34-125">En el siguiente ejemplo se muestra cómo especificar la alineación y se emplean caracteres de barra vertical ("|") para delimitar los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="53b34-125">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="53b34-126">Tal y como refleja la salida del ejemplo, si la longitud del resultado de expresión con formato supera el ancho de campo especificado, se omitirá el valor de *alignment*.</span><span class="sxs-lookup"><span data-stu-id="53b34-126">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="53b34-127">Para más información, vea la sección [Alignment (Componente)](../../standard/base-types/composite-formatting.md#alignment-component) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-127">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="53b34-128">Cómo usar secuencias de escape en una cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="53b34-128">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="53b34-129">Las cadenas interpoladas admiten todas las secuencias de escape que se usan en los literales de cadena ordinarios.</span><span class="sxs-lookup"><span data-stu-id="53b34-129">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="53b34-130">Para más información, vea [Secuencias de escape de cadena](../programming-guide/strings/index.md#string-escape-sequences).</span><span class="sxs-lookup"><span data-stu-id="53b34-130">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="53b34-131">Para interpretar las secuencias de escape literalmente, use un literal de cadena [textual](../language-reference/tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-131">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="53b34-132">Las cadenas textuales interpoladas comienzan por el carácter `$`, seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="53b34-132">An interpolated verbatim string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="53b34-133">A partir C# 8.0, puede usar los tokens `$` y `@` en cualquier orden; tanto `$@"..."` como `@$"..."` son cadenas textuales interpoladas válidas.</span><span class="sxs-lookup"><span data-stu-id="53b34-133">Starting with C# 8.0, you can use the `$` and `@` tokens in any order: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span>

<span data-ttu-id="53b34-134">Para incluir una llave ("{" o "}") en una cadena de resultado, use dos llaves ("{{" o "}}").</span><span class="sxs-lookup"><span data-stu-id="53b34-134">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="53b34-135">Para más información, vea la sección [Llaves de escape](../../standard/base-types/composite-formatting.md#escaping-braces) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-135">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="53b34-136">En el siguiente ejemplo se muestra cómo incluir llaves en una cadena de resultado y cómo construir una cadena interpolada textual:</span><span class="sxs-lookup"><span data-stu-id="53b34-136">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolation-expression"></a><span data-ttu-id="53b34-137">Cómo usar un operador condicional ternario `?:` en una expresión de interpolación</span><span class="sxs-lookup"><span data-stu-id="53b34-137">How to use a ternary conditional operator `?:` in an interpolation expression</span></span>

<span data-ttu-id="53b34-138">Dado que los dos puntos (:) tienen un significado especial en un elemento con una expresión de interpolación, para poder usar un [operador condicional](../language-reference/operators/conditional-operator.md) en una expresión de este tipo habrá que ponerlo entre paréntesis, como vemos en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="53b34-138">As the colon (":") has special meaning in an item with an interpolation expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="53b34-139">Cómo crear una cadena de resultado específica de la referencia cultural con interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="53b34-139">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="53b34-140">Las cadenas interpoladas usan de forma predeterminada la referencia cultural definida actualmente por la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> en todas las operaciones de formato.</span><span class="sxs-lookup"><span data-stu-id="53b34-140">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="53b34-141">Use la conversión implícita de una cadena interpolada en una instancia de <xref:System.FormattableString?displayProperty=nameWithType> y llame al método <xref:System.FormattableString.ToString(System.IFormatProvider)> correspondiente para crear una cadena de resultado específica de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="53b34-141">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="53b34-142">En el siguiente ejemplo se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="53b34-142">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="53b34-143">Tal y como se muestra en el ejemplo, se puede usar una instancia de <xref:System.FormattableString> para generar varias cadenas de resultado para varias referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="53b34-143">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="53b34-144">Cómo crear una cadena de resultado usando la referencia de cultura invariable</span><span class="sxs-lookup"><span data-stu-id="53b34-144">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="53b34-145">Puede usar el método estático <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> junto con el método <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> para resolver una cadena interpolada en una cadena de resultado de <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="53b34-145">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="53b34-146">En el siguiente ejemplo se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="53b34-146">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="53b34-147">Conclusión</span><span class="sxs-lookup"><span data-stu-id="53b34-147">Conclusion</span></span>

<span data-ttu-id="53b34-148">En este tutorial se han descrito escenarios habituales en los que se usa la interpolación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="53b34-148">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="53b34-149">Para más información sobre la interpolación de cadenas, vea el tema [Interpolación de cadenas](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-149">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="53b34-150">Para más información sobre cómo aplicar formato a tipos .NET, vea los temas [Aplicar formato a tipos en .NET](../../standard/base-types/formatting-types.md) y [Formatos compuestos](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="53b34-150">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="53b34-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b34-151">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="53b34-152">Cadenas</span><span class="sxs-lookup"><span data-stu-id="53b34-152">Strings</span></span>](../programming-guide/strings/index.md)
