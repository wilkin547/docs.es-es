---
title: ulong (Referencia de C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords: ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2058d9f6a228b13938fe08d7e2fb11e3b9f4600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-c-reference"></a><span data-ttu-id="38a35-102">ulong (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="38a35-102">ulong (C# Reference)</span></span>

<span data-ttu-id="38a35-103">La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="38a35-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="38a35-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="38a35-104">Type</span></span>|<span data-ttu-id="38a35-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="38a35-105">Range</span></span>|<span data-ttu-id="38a35-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="38a35-106">Size</span></span>|<span data-ttu-id="38a35-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="38a35-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="38a35-108">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="38a35-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="38a35-109">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="38a35-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="38a35-110">Literales</span><span class="sxs-lookup"><span data-stu-id="38a35-110">Literals</span></span>  

<span data-ttu-id="38a35-111">Puede declarar e inicializar una variable `ulong` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="38a35-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="38a35-112">Si el literal entero está fuera del intervalo de `ulong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="38a35-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="38a35-113">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ulong`.</span><span class="sxs-lookup"><span data-stu-id="38a35-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
[!code-csharp[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> <span data-ttu-id="38a35-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="38a35-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="38a35-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="38a35-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="38a35-116">A partir de C# 7, se han agregado un par de características mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="38a35-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="38a35-117">C# 7.0 permite el uso del carácter de subrayado, `_`, como un separador de dígito.</span><span class="sxs-lookup"><span data-stu-id="38a35-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="38a35-118">7.2 C# permite `_` para usarse como un separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="38a35-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="38a35-119">Un literal decimal no está permitido que tengan un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="38a35-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="38a35-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="38a35-120">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="38a35-121">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="38a35-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="38a35-122">El sufijo `UL` o `ul` identifica de manera inequívoca un literal numérico como un valor `ulong`.</span><span class="sxs-lookup"><span data-stu-id="38a35-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="38a35-123">El sufijo `L` denota un `ulong` si el valor literal supera <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="38a35-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="38a35-124">Y el sufijo `U` o `u` denota un `ulong` si el valor literal supera <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="38a35-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="38a35-125">En el ejemplo siguiente se usa el sufijo `ul` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="38a35-125">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
[!code-csharp[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="38a35-126">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="38a35-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="38a35-127">int</span><span class="sxs-lookup"><span data-stu-id="38a35-127">int</span></span>](int.md)
2. [<span data-ttu-id="38a35-128">uint</span><span class="sxs-lookup"><span data-stu-id="38a35-128">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="38a35-129">long</span><span class="sxs-lookup"><span data-stu-id="38a35-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="38a35-130">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="38a35-130">Compiler overload resolution</span></span>
  
 <span data-ttu-id="38a35-131">El sufijo se usa habitualmente en las llamadas a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="38a35-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="38a35-132">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ulong` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="38a35-132">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="38a35-133">Si se usa un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38a35-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="38a35-134">Conversiones</span><span class="sxs-lookup"><span data-stu-id="38a35-134">Conversions</span></span>  
 <span data-ttu-id="38a35-135">Existe una conversión implícita predefinida de `ulong` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="38a35-135">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="38a35-136">No existe conversión implícita de `ulong` a cualquier tipo entero.</span><span class="sxs-lookup"><span data-stu-id="38a35-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="38a35-137">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="38a35-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="38a35-138">Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="38a35-138">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="38a35-139">Además, no hay ninguna conversión implícita de tipos de punto flotante a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="38a35-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="38a35-140">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="38a35-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="38a35-141">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="38a35-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="38a35-142">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="38a35-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="38a35-143">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="38a35-143">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38a35-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a35-144">See Also</span></span>  
 <xref:System.UInt64>  
 [<span data-ttu-id="38a35-145">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="38a35-145">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="38a35-146">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="38a35-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="38a35-147">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="38a35-147">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="38a35-148">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="38a35-148">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="38a35-149">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="38a35-149">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="38a35-150">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="38a35-150">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="38a35-151">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="38a35-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
