---
title: Cadenas interpoladas (C#)
ms.date: 10/18/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0569636bde875d2d0d8921a544273f3214d05188
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2018
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="9454e-102">Cadenas interpoladas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9454e-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="9454e-103">Se utiliza para construir cadenas.</span><span class="sxs-lookup"><span data-stu-id="9454e-103">Used to construct strings.</span></span>  <span data-ttu-id="9454e-104">Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="9454e-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="9454e-105">Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="9454e-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="9454e-106">Esta característica está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9454e-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="9454e-107">Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="9454e-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="9454e-108">Por ejemplo, la cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="9454e-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="9454e-109">contiene dos expresiones interpoladas, "{name}" y "{hours:hh}".</span><span class="sxs-lookup"><span data-stu-id="9454e-109">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="9454e-110">La cadena de formato compuesto equivalente es esta:</span><span class="sxs-lookup"><span data-stu-id="9454e-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="9454e-111">La estructura de una cadena interpolada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9454e-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="9454e-112">donde:</span><span class="sxs-lookup"><span data-stu-id="9454e-112">where:</span></span> 

- <span data-ttu-id="9454e-113">*field-width* es un entero con signo que indica el número de caracteres del campo.</span><span class="sxs-lookup"><span data-stu-id="9454e-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="9454e-114">Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="9454e-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="9454e-115">*format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato.</span><span class="sxs-lookup"><span data-stu-id="9454e-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="9454e-116">Por ejemplo, para un valor <xref:System.DateTime>, podría ser una cadena de formato estándar de fecha y hora, como "D" o "d".</span><span class="sxs-lookup"><span data-stu-id="9454e-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9454e-117">No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia la cadena.</span><span class="sxs-lookup"><span data-stu-id="9454e-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="9454e-118">Si hay alguno, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9454e-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="9454e-119">Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="9454e-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="9454e-120">La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="9454e-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="9454e-121">Esto le permite separar la definición y la evaluación de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="9454e-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="9454e-122">Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="9454e-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="9454e-123">Consulte la sección Conversiones implícitas para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="9454e-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="9454e-124">Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="9454e-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="9454e-125">En el ejemplo siguiente las comillas se escriben entre caracteres de escape para incluirlas en la cadena de resultado y se usan paréntesis para delimitar la expresión `(age == 1 ? "" : "s")` de modo que el carácter de dos puntos no se interprete como el principio de una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="9454e-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="9454e-126">Las cadenas interpoladas textuales usan el carácter `$` seguido del carácter `@`.</span><span class="sxs-lookup"><span data-stu-id="9454e-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="9454e-127">Para más información sobre las cadenas textuales, vea el tema [string](string.md).</span><span class="sxs-lookup"><span data-stu-id="9454e-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="9454e-128">El código siguiente es una versión modificada del fragmento de código anterior en el que se usa una cadena interpolada textual:</span><span class="sxs-lookup"><span data-stu-id="9454e-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="9454e-129">Los cambios de formato son necesarios porque las cadenas textuales no obedecen las secuencias de escape `\`.</span><span class="sxs-lookup"><span data-stu-id="9454e-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9454e-130">El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.</span><span class="sxs-lookup"><span data-stu-id="9454e-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="9454e-131">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="9454e-131">Implicit Conversions</span></span>  

<span data-ttu-id="9454e-132">Hay tres conversiones de tipo implícito de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="9454e-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="9454e-133">Conversión de una cadena interpolada a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9454e-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="9454e-134">En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="9454e-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="9454e-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9454e-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="9454e-136">Este es el resultado final de una interpretación de cadena.</span><span class="sxs-lookup"><span data-stu-id="9454e-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="9454e-137">Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave.</span><span class="sxs-lookup"><span data-stu-id="9454e-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="9454e-138">Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="9454e-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="9454e-139">Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="9454e-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="9454e-140">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método <xref:System.Object.ToString>.</span><span class="sxs-lookup"><span data-stu-id="9454e-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="9454e-141">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9454e-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="9454e-142">En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="9454e-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="9454e-143">También pasa la variable <xref:System.IFormattable> al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9454e-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="9454e-144">Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="9454e-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="9454e-145">Si se pasa a un método de formato de cadena, como <xref:System.Console.WriteLine(System.String)>, sus elementos de formato se resuelven y se devuelve la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="9454e-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="9454e-146">Conversión de una cadena interpolada a una variable <xref:System.FormattableString> que representa una cadena de formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="9454e-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="9454e-147">El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta.</span><span class="sxs-lookup"><span data-stu-id="9454e-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="9454e-148"><xref:System.FormattableString> también incluye sobrecargas <xref:System.FormattableString.ToString> que le permiten generar cadenas de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture> y <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="9454e-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="9454e-149">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.</span><span class="sxs-lookup"><span data-stu-id="9454e-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="9454e-150">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9454e-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="9454e-151">Especificación del lenguaje</span><span class="sxs-lookup"><span data-stu-id="9454e-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9454e-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="9454e-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="9454e-153">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9454e-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9454e-154">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9454e-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
