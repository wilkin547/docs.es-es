---
title: sbyte (Referencia de C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
dev_langs:
- CSharp
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
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
ms.openlocfilehash: 69741a5b9556c769156687584041667312550c17
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="sbyte-c-reference"></a><span data-ttu-id="74e38-102">sbyte (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="74e38-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="74e38-103">`sbyte` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="74e38-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="74e38-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="74e38-104">Type</span></span>|<span data-ttu-id="74e38-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="74e38-105">Range</span></span>|<span data-ttu-id="74e38-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="74e38-106">Size</span></span>|<span data-ttu-id="74e38-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74e38-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="74e38-108">De -128 a 127</span><span class="sxs-lookup"><span data-stu-id="74e38-108">-128 to 127</span></span>|<span data-ttu-id="74e38-109">Entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="74e38-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="74e38-110">Literales</span><span class="sxs-lookup"><span data-stu-id="74e38-110">Literals</span></span>  

<span data-ttu-id="74e38-111">Puede declarar e inicializar una variable `sbyte` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="74e38-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="74e38-112">En el ejemplo siguiente, los enteros que equivalen a -102 que se representan como literales binarios, hexadecimales y decimales se convierten de [int](../../../csharp/language-reference/keywords/int.md) a valores `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="74e38-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
<span data-ttu-id="74e38-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span><span class="sxs-lookup"><span data-stu-id="74e38-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="74e38-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="74e38-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="74e38-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="74e38-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="74e38-116">A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="74e38-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="74e38-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span><span class="sxs-lookup"><span data-stu-id="74e38-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span></span>  

<span data-ttu-id="74e38-118">Si el literal entero está fuera del intervalo de `sbyte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=fullName> o mayor que <xref:System.SByte.MaxValue?displayProperty=fullName>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="74e38-118">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=fullName> or greater than <xref:System.SByte.MaxValue?displayProperty=fullName>, a compilation error occurs.</span></span> <span data-ttu-id="74e38-119">Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span><span class="sxs-lookup"><span data-stu-id="74e38-119">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="74e38-120">Esto significa que, en este ejemplo, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros con signo de 32 bits con un valor de 156, que supera <xref:System.SByte.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="74e38-120">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="74e38-121">Por este motivo, se necesita el operador de conversión, y debe producirse la asignación en un contexto [desactivado](unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="74e38-121">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="74e38-122">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="74e38-122">Compiler overload resolution</span></span>

 <span data-ttu-id="74e38-123">Debe usarse una conversión de tipos al llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="74e38-123">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="74e38-124">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `sbyte` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="74e38-124">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="74e38-125">El uso de la conversión `sbyte` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="74e38-125">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="74e38-126">Conversiones</span><span class="sxs-lookup"><span data-stu-id="74e38-126">Conversions</span></span>  
 <span data-ttu-id="74e38-127">Existe una conversión implícita predefinida de `sbyte` a [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="74e38-127">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="74e38-128">No se pueden convertir implícitamente los tipos numéricos no literales de mayor tamaño de almacenamiento a `sbyte` (vea en la [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="74e38-128">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="74e38-129">Considere, por ejemplo, las dos siguientes variables de `sbyte` `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="74e38-129">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="74e38-130">La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética del lado derecho del operador de asignación da como resultado [int](../../../csharp/language-reference/keywords/int.md) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74e38-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="74e38-131">Para corregir este problema, convierta la expresión como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74e38-131">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="74e38-132">Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="74e38-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="74e38-133">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="74e38-133">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="74e38-134">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="74e38-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="74e38-135">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="74e38-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="74e38-136">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="74e38-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="74e38-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="74e38-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74e38-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="74e38-138">See Also</span></span>  
 <span data-ttu-id="74e38-139"><xref:System.SByte></span><span class="sxs-lookup"><span data-stu-id="74e38-139"><xref:System.SByte></span></span>   
 <span data-ttu-id="74e38-140">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="74e38-141">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="74e38-142">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="74e38-143">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-143">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="74e38-144">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-144">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="74e38-145">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="74e38-145">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="74e38-146">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="74e38-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

