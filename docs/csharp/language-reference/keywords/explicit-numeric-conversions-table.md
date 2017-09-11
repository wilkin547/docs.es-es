---
title: "Tabla de conversiones numéricas explícitas (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0315810522be319a6bb565c99e1c8f7d1ba4701b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="723cb-102">Tabla de conversiones numéricas explícitas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="723cb-102">Explicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="723cb-103">La conversión numérica explícita se usa para convertir cualquier tipo numérico en cualquier otro tipo numérico, para el que no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="723cb-103">Explicit numeric conversion is used to convert any numeric type to any other numeric type, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="723cb-104">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="723cb-104">The following table shows these conversions.</span></span>  
  
 <span data-ttu-id="723cb-105">Para obtener más información sobre las conversiones, vea [Conversiones de tipos (Guía de programación de C#)](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="723cb-105">For more information about conversions, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
|<span data-ttu-id="723cb-106">De</span><span class="sxs-lookup"><span data-stu-id="723cb-106">From</span></span>|<span data-ttu-id="723cb-107">En</span><span class="sxs-lookup"><span data-stu-id="723cb-107">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="723cb-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="723cb-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="723cb-109">`byte`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-109">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-110">byte</span><span class="sxs-lookup"><span data-stu-id="723cb-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="723cb-111">`Sbyte` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-111">`Sbyte` or `char`</span></span>|  
|[<span data-ttu-id="723cb-112">short</span><span class="sxs-lookup"><span data-stu-id="723cb-112">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="723cb-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-114">ushort</span><span class="sxs-lookup"><span data-stu-id="723cb-114">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="723cb-115">`sbyte`, `byte`, `short` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-115">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-116">int</span><span class="sxs-lookup"><span data-stu-id="723cb-116">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="723cb-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="723cb-118">uint</span><span class="sxs-lookup"><span data-stu-id="723cb-118">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="723cb-119">`sbyte`, `byte`, `short`, `ushort`, `int` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-119">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-120">long</span><span class="sxs-lookup"><span data-stu-id="723cb-120">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="723cb-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-122">ulong</span><span class="sxs-lookup"><span data-stu-id="723cb-122">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="723cb-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`</span><span class="sxs-lookup"><span data-stu-id="723cb-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="723cb-124">char</span><span class="sxs-lookup"><span data-stu-id="723cb-124">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="723cb-125">`sbyte`, `byte`o `short`</span><span class="sxs-lookup"><span data-stu-id="723cb-125">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="723cb-126">float</span><span class="sxs-lookup"><span data-stu-id="723cb-126">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="723cb-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="723cb-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="723cb-128">double</span><span class="sxs-lookup"><span data-stu-id="723cb-128">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="723cb-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="723cb-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="723cb-130">decimal</span><span class="sxs-lookup"><span data-stu-id="723cb-130">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="723cb-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`</span><span class="sxs-lookup"><span data-stu-id="723cb-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="723cb-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="723cb-132">Remarks</span></span>  
  
-   <span data-ttu-id="723cb-133">La conversión numérica explícita puede provocar la pérdida de precisión o que se generen excepciones.</span><span class="sxs-lookup"><span data-stu-id="723cb-133">The explicit numeric conversion may cause loss of precision or result in throwing exceptions.</span></span>  
  
-   <span data-ttu-id="723cb-134">Cuando convierte un valor `decimal` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="723cb-134">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="723cb-135">Si el valor entero resultante está fuera del rango del tipo de destino, se genera una excepción <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="723cb-135">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
-   <span data-ttu-id="723cb-136">Cuando convierte de un valor `double` o `float` a un tipo entero, el valor se trunca.</span><span class="sxs-lookup"><span data-stu-id="723cb-136">When you convert from a `double` or `float` value to an integral type, the value is truncated.</span></span> <span data-ttu-id="723cb-137">Si el valor entero resultante está fuera del rango del valor de destino, el resultado depende del contexto de comprobación de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="723cb-137">If the resulting integral value is outside the range of the destination value, the result depends on the overflow checking context.</span></span> <span data-ttu-id="723cb-138">En un contexto comprobado, se genera una excepción `OverflowException`, mientras que en un contexto no comprobado, el resultado es un valor no especificado del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="723cb-138">In a checked context, an `OverflowException` is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
-   <span data-ttu-id="723cb-139">Cuando convierte `double` en `float`, el valor `double` se redondea al valor `float` más cercano.</span><span class="sxs-lookup"><span data-stu-id="723cb-139">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="723cb-140">Si el valor `double` es demasiado pequeño o demasiado grande para adaptarse al tipo de destino, el resultado será cero o infinito.</span><span class="sxs-lookup"><span data-stu-id="723cb-140">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
-   <span data-ttu-id="723cb-141">Cuando convierte `float` o `double` en `decimal`, el valor de origen se convierte en la representación `decimal` y se redondea al número más cercano después de la posición decimal 28 si es necesario.</span><span class="sxs-lookup"><span data-stu-id="723cb-141">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="723cb-142">Dependiendo del valor que tenga el valor de origen, puede producirse uno de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="723cb-142">Depending on the value of the source value, one of the following results may occur:</span></span>  
  
    -   <span data-ttu-id="723cb-143">Si el valor de origen es demasiado pequeño para representarse como `decimal`, el resultado se convierte en cero.</span><span class="sxs-lookup"><span data-stu-id="723cb-143">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  
  
    -   <span data-ttu-id="723cb-144">Si el valor de origen es NaN (no es un número), infinito o demasiado grande para representarse como un `decimal`, se genera `OverflowException`.</span><span class="sxs-lookup"><span data-stu-id="723cb-144">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an `OverflowException` is thrown.</span></span>  
  
-   <span data-ttu-id="723cb-145">Cuando convierte `decimal` en `float` o `double`, el valor `decimal` se redondea al valor `double` o `float` más cercano.</span><span class="sxs-lookup"><span data-stu-id="723cb-145">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="723cb-146">Para obtener más información sobre la conversión explícita, vea Explícita en la especificación del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="723cb-146">For more information on explicit conversion, see Explicit in the C# Language Specification.</span></span> <span data-ttu-id="723cb-147">Para obtener más información sobre cómo tener acceso a la especificación, vea [Especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="723cb-147">For more information on how to access the spec, see [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723cb-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="723cb-148">See Also</span></span>  
 <span data-ttu-id="723cb-149">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="723cb-149">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="723cb-150">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="723cb-150">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="723cb-151">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="723cb-151">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="723cb-152">[() (operador)](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="723cb-152">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="723cb-153">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="723cb-153">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="723cb-154">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="723cb-154">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="723cb-155">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="723cb-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)

