---
title: Cadenas interpoladas (C#)
ms.date: 2017-02-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 03d1e3f0897713e25be7d7f893861a3eb4dac211
ms.openlocfilehash: ee35da0a008a19ad643fffff64d74485237d716f
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2017

---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="6c89d-102">Cadenas interpoladas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6c89d-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="6c89d-103">Se utiliza para construir cadenas.</span><span class="sxs-lookup"><span data-stu-id="6c89d-103">Used to construct strings.</span></span>  <span data-ttu-id="6c89d-104">Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="6c89d-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="6c89d-105">Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="6c89d-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span>  

<span data-ttu-id="6c89d-106">Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="6c89d-106">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="6c89d-107">Por ejemplo, la cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="6c89d-107">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}"); 
```  
<span data-ttu-id="6c89d-108">contiene dos expresiones interpoladas, "{name}" y "{hours:hh}".</span><span class="sxs-lookup"><span data-stu-id="6c89d-108">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="6c89d-109">La cadena de formato compuesto equivalente es esta:</span><span class="sxs-lookup"><span data-stu-id="6c89d-109">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);  
```  

<span data-ttu-id="6c89d-110">La estructura de una cadena interpolada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c89d-110">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="6c89d-111">donde:</span><span class="sxs-lookup"><span data-stu-id="6c89d-111">where:</span></span> 

- <span data-ttu-id="6c89d-112">*field-width* es un entero con signo que indica el número de caracteres del campo.</span><span class="sxs-lookup"><span data-stu-id="6c89d-112">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="6c89d-113">Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="6c89d-113">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="6c89d-114">*format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato.</span><span class="sxs-lookup"><span data-stu-id="6c89d-114">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="6c89d-115">Por ejemplo, para un valor @System.DateTime, podría ser una cadena de formato estándar de fecha y hora, como "D" o "d".</span><span class="sxs-lookup"><span data-stu-id="6c89d-115">For example, for a @System.DateTime value, it could be a standard date and time format string such as "D" or "d".</span></span>

 <span data-ttu-id="6c89d-116">Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="6c89d-116">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="6c89d-117">La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="6c89d-117">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="6c89d-118">Esto le permite separar la definición y la evaluación de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="6c89d-118">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="6c89d-119">Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="6c89d-119">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="6c89d-120">Consulte la sección Conversiones implícitas para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="6c89d-120">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="6c89d-121">Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="6c89d-121">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="6c89d-122">En el ejemplo siguiente las comillas se escriben entre caracteres de escape para incluirlas en la cadena de resultado y se usan paréntesis para delimitar la expresión `(age == 1 ? "" : "s")` de modo que el carácter de dos puntos no se interprete como el principio de una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="6c89d-122">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

<span data-ttu-id="6c89d-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="6c89d-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span></span>  

## <a name="implicit-conversions"></a><span data-ttu-id="6c89d-124">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="6c89d-124">Implicit Conversions</span></span>  

<span data-ttu-id="6c89d-125">Hay tres conversiones de tipo implícito de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="6c89d-125">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="6c89d-126">Conversión de una cadena interpolada a @System.String.</span><span class="sxs-lookup"><span data-stu-id="6c89d-126">Conversion of an interpolated string to a @System.String.</span></span> <span data-ttu-id="6c89d-127">En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="6c89d-127">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="6c89d-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c89d-128">For example:</span></span>

   <span data-ttu-id="6c89d-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="6c89d-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span></span>  

   <span data-ttu-id="6c89d-130">Este es el resultado final de una interpretación de cadena.</span><span class="sxs-lookup"><span data-stu-id="6c89d-130">This is the final result of a string interpretation.</span></span> <span data-ttu-id="6c89d-131">Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave.</span><span class="sxs-lookup"><span data-stu-id="6c89d-131">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="6c89d-132">Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="6c89d-132">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="6c89d-133">Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="6c89d-133">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="6c89d-134">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método @System.Object.ToString.</span><span class="sxs-lookup"><span data-stu-id="6c89d-134">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the @System.Object.ToString method.</span></span>  <span data-ttu-id="6c89d-135">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6c89d-135">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="6c89d-136">En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="6c89d-136">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="6c89d-137">También se pasa la variable <xref:System.IFormattable> al método @System.Console(System.String).</span><span class="sxs-lookup"><span data-stu-id="6c89d-137">It also passes the <xref:System.IFormattable> variable to the @System.Console(System.String) method.</span></span>

   <span data-ttu-id="6c89d-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="6c89d-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span></span>  

   <span data-ttu-id="6c89d-139">Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="6c89d-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="6c89d-140">Si se pasa a un método de formato de cadena, como @System.Console.WriteLine(System.String), sus elementos de formato se resuelven y se devuelve la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="6c89d-140">If it is passed to a string formatting method, such as @System.Console.WriteLine(System.String), its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="6c89d-141">Conversión de una cadena interpolada a una variable <xref:System.FormattableString> que representa una cadena de formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="6c89d-141">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="6c89d-142">El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta.</span><span class="sxs-lookup"><span data-stu-id="6c89d-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span>  <span data-ttu-id="6c89d-143"><xref:System.FormattableString> también incluye sobrecargas <xref:System.FormattableString.ToString> que le permiten generar cadenas de resultado para @System.Globalization.InvariantCulture y @System.Globalization.CurrentCulture.</span><span class="sxs-lookup"><span data-stu-id="6c89d-143"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the @System.Globalization.InvariantCulture and @System.Globalization.CurrentCulture.</span></span>  <span data-ttu-id="6c89d-144">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.</span><span class="sxs-lookup"><span data-stu-id="6c89d-144">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="6c89d-145">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6c89d-145">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="6c89d-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="6c89d-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span></span>  

## <a name="language-specification"></a><span data-ttu-id="6c89d-147">Especificación del lenguaje</span><span class="sxs-lookup"><span data-stu-id="6c89d-147">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c89d-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c89d-148">See Also</span></span>  
 <span data-ttu-id="6c89d-149"><xref:System.IFormattable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6c89d-149"><xref:System.IFormattable?displayProperty=fullName></span></span>   
 <span data-ttu-id="6c89d-150"><xref:System.FormattableString?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6c89d-150"><xref:System.FormattableString?displayProperty=fullName></span></span>   
 <span data-ttu-id="6c89d-151">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c89d-151">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="6c89d-152">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6c89d-152">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

