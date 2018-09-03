---
title: int (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: 95ac267bc70d2e7873593c08e0b10cb50fefd8c8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421968"
---
# <a name="int-c-reference"></a><span data-ttu-id="5136b-102">int (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5136b-102">int (C# Reference)</span></span>

<span data-ttu-id="5136b-103">`int` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5136b-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="5136b-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="5136b-104">Type</span></span>|<span data-ttu-id="5136b-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="5136b-105">Range</span></span>|<span data-ttu-id="5136b-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="5136b-106">Size</span></span>|<span data-ttu-id="5136b-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="5136b-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`int`|<span data-ttu-id="5136b-108">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="5136b-108">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="5136b-109">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="5136b-109">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="5136b-110">Literales</span><span class="sxs-lookup"><span data-stu-id="5136b-110">Literals</span></span>  
 
<span data-ttu-id="5136b-111">Puede declarar e inicializar una variable `int` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="5136b-111">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="5136b-112">Si el literal entero está fuera del intervalo de `int` (es decir, si es inferior a <xref:System.Int32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="5136b-112">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="5136b-113">En el ejemplo siguiente, los enteros que equivalen a 90 946 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `int`.</span><span class="sxs-lookup"><span data-stu-id="5136b-113">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="5136b-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="5136b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="5136b-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="5136b-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="5136b-116">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="5136b-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="5136b-117">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="5136b-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="5136b-118">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="5136b-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="5136b-119">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="5136b-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="5136b-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5136b-120">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="5136b-121">Los literales enteros también pueden incluir un sufijo que denote el tipo, aunque no existe ningún sufijo que denote el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="5136b-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="5136b-122">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="5136b-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="5136b-123">uint</span><span class="sxs-lookup"><span data-stu-id="5136b-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="5136b-124">long</span><span class="sxs-lookup"><span data-stu-id="5136b-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="5136b-125">ulong</span><span class="sxs-lookup"><span data-stu-id="5136b-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="5136b-126">En estos ejemplos, el literal 90946 es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="5136b-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="5136b-127">Conversiones</span><span class="sxs-lookup"><span data-stu-id="5136b-127">Conversions</span></span>  
 <span data-ttu-id="5136b-128">Hay una conversión implícita predefinida de `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="5136b-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="5136b-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5136b-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="5136b-130">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="5136b-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="5136b-131">Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:</span><span class="sxs-lookup"><span data-stu-id="5136b-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5136b-132">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `int`.</span><span class="sxs-lookup"><span data-stu-id="5136b-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="5136b-133">Por ejemplo, la instrucción siguiente genera un error del compilador a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="5136b-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5136b-134">Para obtener más información sobre las expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="5136b-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5136b-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5136b-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5136b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5136b-136">See Also</span></span>

- <xref:System.Int32>  
- [<span data-ttu-id="5136b-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5136b-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5136b-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5136b-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5136b-139">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5136b-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="5136b-140">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="5136b-140">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="5136b-141">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="5136b-141">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="5136b-142">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="5136b-142">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="5136b-143">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="5136b-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
