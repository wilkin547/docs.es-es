---
title: int (Referencia de C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7acb8bb482ebf8f5c2b508e7cfd45b5b64aae3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="int-c-reference"></a><span data-ttu-id="475de-102">int (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="475de-102">int (C# Reference)</span></span>

<span data-ttu-id="475de-103">`int` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="475de-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="475de-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="475de-104">Type</span></span>|<span data-ttu-id="475de-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="475de-105">Range</span></span>|<span data-ttu-id="475de-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="475de-106">Size</span></span>|<span data-ttu-id="475de-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="475de-107">.NET Framework type</span></span>|<span data-ttu-id="475de-108">Default Value</span><span class="sxs-lookup"><span data-stu-id="475de-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="475de-109">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="475de-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="475de-110">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="475de-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="475de-111">0</span><span class="sxs-lookup"><span data-stu-id="475de-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="475de-112">Literales</span><span class="sxs-lookup"><span data-stu-id="475de-112">Literals</span></span>  
 
<span data-ttu-id="475de-113">Puede declarar e inicializar una variable `int` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="475de-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="475de-114">Si el literal entero está fuera del intervalo de `int` (es decir, si es inferior a <xref:System.Int32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="475de-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="475de-115">En el ejemplo siguiente, los enteros que equivalen a 90 946 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `int`.</span><span class="sxs-lookup"><span data-stu-id="475de-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="475de-116">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="475de-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="475de-117">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="475de-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="475de-118">A partir de C# 7, se han agregado un par de características mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="475de-118">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="475de-119">C# 7.0 permite el uso del carácter de subrayado, `_`, como un separador de dígito.</span><span class="sxs-lookup"><span data-stu-id="475de-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="475de-120">7.2 C# permite `_` para usarse como un separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="475de-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="475de-121">Un literal decimal no está permitido que tengan un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="475de-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="475de-122">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="475de-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="475de-123">Los literales enteros también pueden incluir un sufijo que denote el tipo, aunque no existe ningún sufijo que denote el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="475de-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="475de-124">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="475de-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="475de-125">uint</span><span class="sxs-lookup"><span data-stu-id="475de-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="475de-126">long</span><span class="sxs-lookup"><span data-stu-id="475de-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="475de-127">ulong</span><span class="sxs-lookup"><span data-stu-id="475de-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="475de-128">En estos ejemplos, el literal 90946 es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="475de-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="475de-129">Conversiones</span><span class="sxs-lookup"><span data-stu-id="475de-129">Conversions</span></span>  
 <span data-ttu-id="475de-130">Hay una conversión implícita predefinida de `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="475de-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="475de-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="475de-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="475de-132">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="475de-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="475de-133">Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:</span><span class="sxs-lookup"><span data-stu-id="475de-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="475de-134">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `int`.</span><span class="sxs-lookup"><span data-stu-id="475de-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="475de-135">Por ejemplo, la instrucción siguiente genera un error del compilador a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="475de-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="475de-136">Para obtener más información sobre las expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="475de-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="475de-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="475de-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="475de-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="475de-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="475de-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="475de-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="475de-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="475de-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="475de-141">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="475de-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="475de-142">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="475de-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="475de-143">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="475de-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="475de-144">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="475de-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="475de-145">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="475de-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
