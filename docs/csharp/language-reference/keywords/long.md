---
title: long (Referencia de C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f18bed80550b293195961fd9d42491dd571cbaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="long-c-reference"></a><span data-ttu-id="2895a-102">long (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2895a-102">long (C# Reference)</span></span>

<span data-ttu-id="2895a-103">`long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2895a-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="2895a-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="2895a-104">Type</span></span>|<span data-ttu-id="2895a-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="2895a-105">Range</span></span>|<span data-ttu-id="2895a-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="2895a-106">Size</span></span>|<span data-ttu-id="2895a-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2895a-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="2895a-108">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="2895a-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="2895a-109">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="2895a-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="2895a-110">Literales</span><span class="sxs-lookup"><span data-stu-id="2895a-110">Literals</span></span> 

<span data-ttu-id="2895a-111">Puede declarar e inicializar una variable `long` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="2895a-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="2895a-112">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `long`.</span><span class="sxs-lookup"><span data-stu-id="2895a-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> <span data-ttu-id="2895a-113">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="2895a-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="2895a-114">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="2895a-114">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="2895a-115">A partir de C# 7, se han agregado un par de características mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="2895a-115">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="2895a-116">C# 7.0 permite el uso del carácter de subrayado, `_`, como un separador de dígito.</span><span class="sxs-lookup"><span data-stu-id="2895a-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="2895a-117">7.2 C# permite `_` para usarse como un separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="2895a-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="2895a-118">Un literal decimal no está permitido que tengan un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="2895a-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="2895a-119">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2895a-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="2895a-120">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="2895a-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="2895a-121">El sufijo `L` denota un `long`.</span><span class="sxs-lookup"><span data-stu-id="2895a-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="2895a-122">En el ejemplo siguiente se usa el sufijo `L` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="2895a-122">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="2895a-123">También puede usar la letra minúscula "l" como sufijo,</span><span class="sxs-lookup"><span data-stu-id="2895a-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="2895a-124">aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1".</span><span class="sxs-lookup"><span data-stu-id="2895a-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="2895a-125">Use "L" para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="2895a-125">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="2895a-126">Cuando se usa el sufijo `L`, se determina que el tipo del entero literal es `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md), según su tamaño.</span><span class="sxs-lookup"><span data-stu-id="2895a-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="2895a-127">En este caso, es `long` porque es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="2895a-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="2895a-128">El sufijo se usa habitualmente para llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="2895a-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="2895a-129">Por ejemplo, los siguientes métodos sobrecargados tienen parámetros de tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="2895a-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="2895a-130">El sufijo `L` garantiza que se llame a la sobrecarga correcta:</span><span class="sxs-lookup"><span data-stu-id="2895a-130">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="2895a-131">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="2895a-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="2895a-132">int</span><span class="sxs-lookup"><span data-stu-id="2895a-132">int</span></span>](int.md)
2. [<span data-ttu-id="2895a-133">uint</span><span class="sxs-lookup"><span data-stu-id="2895a-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="2895a-134">ulong</span><span class="sxs-lookup"><span data-stu-id="2895a-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="2895a-135">El literal 4294967296 de los ejemplos anteriores es de tipo `long` porque supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="2895a-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="2895a-136">Si usa el tipo `long` con otros tipos enteros en la misma expresión, la expresión se evalúa como `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas).</span><span class="sxs-lookup"><span data-stu-id="2895a-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="2895a-137">Por ejemplo, la siguiente expresión se evalúa como `long`:</span><span class="sxs-lookup"><span data-stu-id="2895a-137">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="2895a-138">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="2895a-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="2895a-139">Conversiones</span><span class="sxs-lookup"><span data-stu-id="2895a-139">Conversions</span></span>  
 <span data-ttu-id="2895a-140">Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="2895a-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="2895a-141">De lo contrario, se debe usar una conversión.</span><span class="sxs-lookup"><span data-stu-id="2895a-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="2895a-142">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="2895a-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="2895a-143">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.</span><span class="sxs-lookup"><span data-stu-id="2895a-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="2895a-144">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `long`.</span><span class="sxs-lookup"><span data-stu-id="2895a-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="2895a-145">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="2895a-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="2895a-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2895a-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2895a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="2895a-147">See Also</span></span>  
 <xref:System.Int64>  
 [<span data-ttu-id="2895a-148">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2895a-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2895a-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2895a-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2895a-150">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="2895a-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2895a-151">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="2895a-151">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="2895a-152">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="2895a-152">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="2895a-153">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="2895a-153">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="2895a-154">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="2895a-154">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
