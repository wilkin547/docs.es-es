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
ms.openlocfilehash: cabb40c9c449780c8c2a504aad3e53938e2ed957
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="2ed6d-103">$ - Interpolación de cadenas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2ed6d-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="2ed6d-104">El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="2ed6d-105">Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="2ed6d-106">Cuando se resuelve la cadena interpolada a la cadena de resultado, los elementos con expresiones interpoladas se reemplazan por las representaciones de cadena de los resultados de la expresión.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-106">When the interpolated string is resolved to the result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="2ed6d-107">Esta característica está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="2ed6d-108">La interpolación de cadenas proporciona una sintaxis más legible y cómoda de crear cadenas con formato que si se usa la característica de [formato compuesto de cadena](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="2ed6d-109">En este ejemplo se usan ambas características para producir el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="2ed6d-110">No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia la cadena.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="2ed6d-111">Si hay alguno, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="2ed6d-112">La estructura de un elemento con una expresión interpolada es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="2ed6d-113">Los elementos entre corchetes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="2ed6d-114">En esta tabla se describe cada elemento.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-114">The following table describes each element.</span></span>

|<span data-ttu-id="2ed6d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ed6d-115">Element</span></span>|<span data-ttu-id="2ed6d-116">Description</span><span class="sxs-lookup"><span data-stu-id="2ed6d-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="2ed6d-117">La expresión que se va a evaluar para obtener un resultado al que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="2ed6d-118">La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="2ed6d-119">La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="2ed6d-120">Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="2ed6d-121">Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="2ed6d-122">Una cadena de formato estándar o personalizado que sea compatible con el tipo de resultado de la expresión.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="2ed6d-123">Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="2ed6d-124">En el ejemplo siguiente, se usan componentes opcionales de formato que se han descrito anteriormente:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-124">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="2ed6d-125">Para incluir una llave ("{" o "}") en el texto producido por una cadena interpolada, use dos llaves, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="2ed6d-125">To include a brace ("{" or "}") in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="2ed6d-126">Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="2ed6d-127">Como los dos puntos (:) tienen un significado especial en un elemento de expresión interpolada, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión interpolada, incluya esa expresión entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="2ed6d-128">En este ejemplo, se muestra cómo incluir una llave en la cadena de resultado y cómo usar un operador condicional en una expresión interpolada:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-128">The following example shows how to include a brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="2ed6d-129">Las cadenas interpoladas textuales usan el carácter `$` seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="2ed6d-130">Para más información sobre las cadenas textuales, vea el tema [string](../keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="2ed6d-131">El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

<span data-ttu-id="2ed6d-132">Hay tres conversiones implícitas de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-132">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="2ed6d-133">Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión interpolada que se reemplazan con las representaciones de cadena con formato correcto de sus resultados.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-133">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="2ed6d-134">Esta conversión usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-134">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="2ed6d-135">Conversión de una cadena interpolada a una instancia <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-135">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="2ed6d-136">Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-136">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="2ed6d-137">Para ello, llame a uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-137">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="2ed6d-138">Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-138">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="2ed6d-139">Un método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-139">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="2ed6d-140">Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-140">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="2ed6d-141">Conversión de una cadena interpolada a una instancia <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="2ed6d-141">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="2ed6d-142">En el ejemplo siguiente, se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:</span><span class="sxs-lookup"><span data-stu-id="2ed6d-142">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

<span data-ttu-id="2ed6d-143">Si no está familiarizado con la interpolación de cadenas, consulte la guía de inicio rápido [Interpolación de cadenas en C#](../../quick-starts/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-143">If you are new to the string interpolation, check the [String interpolation in C#](../../quick-starts/interpolated-strings.yml) quickstart.</span></span> <span data-ttu-id="2ed6d-144">Para ver más ejemplos, eche un vistazo al tutorial 
[Interpolación de cadenas en C#](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="2ed6d-144">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ed6d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ed6d-145">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="2ed6d-146">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="2ed6d-146">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="2ed6d-147">Cadenas</span><span class="sxs-lookup"><span data-stu-id="2ed6d-147">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="2ed6d-148">Caracteres especiales de C#</span><span class="sxs-lookup"><span data-stu-id="2ed6d-148">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="2ed6d-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2ed6d-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2ed6d-150">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2ed6d-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  