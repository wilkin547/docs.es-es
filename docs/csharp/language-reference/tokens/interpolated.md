---
title: $ - Interpolación de cadenas (Referencia de C#)
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="5d3b2-103">$ - Interpolación de cadenas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5d3b2-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="5d3b2-104">El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="5d3b2-105">Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="5d3b2-106">Cuando se resuelve la cadena interpolada, como por ejemplo en una instrucción de asignación o una llamada de método, las expresiones interpoladas se reemplazan por las representaciones de cadena de sus resultados para generar la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-106">When the interpolated string is resolved, for example in an assignment statement or a method call, interpolated expressions are replaced by the string representations of their results to produce the result string.</span></span> <span data-ttu-id="5d3b2-107">Esta característica está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="5d3b2-108">La interpolación de cadenas es una manera más legible y cómoda de crear cadenas con formato que si se usa la característica [formato de compuesto de cadena](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-108">String interpolation is a more readable and convenient way to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="5d3b2-109">En este ejemplo se usan ambas características para producir el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="5d3b2-110">No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia la cadena.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="5d3b2-111">Si hay alguno, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="5d3b2-112">La estructura de un elemento con una expresión interpolada es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="5d3b2-113">Los elementos entre corchetes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="5d3b2-114">En esta tabla se describe cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-114">The following table describes each element.</span></span>

|<span data-ttu-id="5d3b2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d3b2-115">Element</span></span>|<span data-ttu-id="5d3b2-116">Description</span><span class="sxs-lookup"><span data-stu-id="5d3b2-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="5d3b2-117">La expresión que se va a evaluar para obtener un resultado al que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="5d3b2-118">La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="5d3b2-119">La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="5d3b2-120">Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="5d3b2-121">Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="5d3b2-122">Una cadena de formato estándar o personalizado que sea compatible con el tipo de resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="5d3b2-123">Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="5d3b2-124">En este ejemplo se usan componentes opcionales de formato que se describen en la tabla anterior:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-124">The following example uses optional formatting components described in the table above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="5d3b2-125">Para incluir una llave ("{" o "}") en el texto producido por una cadena interpolada, use dos llaves, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="5d3b2-125">To include a curly brace ("{" or "}") in the text produced by an interpolated string, use two curly braces, "{{" or "}}".</span></span> <span data-ttu-id="5d3b2-126">Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="5d3b2-127">Como los dos puntos (:) tienen un significado especial en un elemento de expresión interpolada, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión interpolada, incluya esa expresión entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="5d3b2-128">En este ejemplo se muestra cómo incluir una llave en la cadena de resultado y cómo usar un operador condicional en una expresión interpolada:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-128">The following example shows how to include a curly brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="5d3b2-129">Las cadenas interpoladas textuales usan el carácter `$` seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="5d3b2-130">Para más información sobre las cadenas textuales, vea el tema [string](../keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="5d3b2-131">El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions"></a><span data-ttu-id="5d3b2-132">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="5d3b2-132">Implicit conversions</span></span>

<span data-ttu-id="5d3b2-133">Hay tres conversiones de tipo implícito de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-133">There are three implicit type conversions from an interpolated string:</span></span>

1. <span data-ttu-id="5d3b2-134">Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión interpolada que se reemplazan con las representaciones de cadena con formato correcto de sus resultados.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-134">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="5d3b2-135">Esta conversión usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-135">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="5d3b2-136">La conversión de una cadena interpolada a una variable <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-136">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="5d3b2-137">Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-137">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="5d3b2-138">Para ello, llame a uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-138">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="5d3b2-139">Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-139">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="5d3b2-140">Un método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-140">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="5d3b2-141">Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-141">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="5d3b2-142">Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="5d3b2-142">Conversion of an interpolated string to an <xref:System.IFormattable> variable that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="5d3b2-143">En este ejemplo se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:</span><span class="sxs-lookup"><span data-stu-id="5d3b2-143">The following example uses implicit conversion to <xref:System.FormattableString> for creating culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a><span data-ttu-id="5d3b2-144">Lecturas adicionales</span><span class="sxs-lookup"><span data-stu-id="5d3b2-144">Additional reading</span></span>

<span data-ttu-id="5d3b2-145">Si no está familiarizado con la interpolación de cadenas, eche un vistazo al inicio rápido [Cadenas interpoladas en C#](../../quick-starts//interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-145">If you are new to the string interpolation, check the [interpolated strings quickstart](../../quick-starts//interpolated-strings.yml).</span></span> <span data-ttu-id="5d3b2-146">Para ver más ejemplos, eche un vistazo al tutorial 
[Interpolación de cadenas en C#](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="5d3b2-146">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d3b2-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d3b2-147">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="5d3b2-148">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="5d3b2-148">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="5d3b2-149">Cadenas</span><span class="sxs-lookup"><span data-stu-id="5d3b2-149">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="5d3b2-150">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="5d3b2-150">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="5d3b2-151">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5d3b2-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5d3b2-152">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5d3b2-152">C# Reference</span></span>](../../../csharp/language-reference/index.md)  