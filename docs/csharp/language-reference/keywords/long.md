---
title: 'long: Referencia de C#'
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: 3085fd9c5f0c379d4a2ef22f4adb0ec157f0b785
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585515"
---
# <a name="long-c-reference"></a><span data-ttu-id="2e861-102">long (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2e861-102">long (C# Reference)</span></span>

<span data-ttu-id="2e861-103">`long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e861-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="2e861-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="2e861-104">Type</span></span>|<span data-ttu-id="2e861-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="2e861-105">Range</span></span>|<span data-ttu-id="2e861-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="2e861-106">Size</span></span>|<span data-ttu-id="2e861-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="2e861-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="2e861-108">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="2e861-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="2e861-109">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="2e861-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="2e861-110">Literales</span><span class="sxs-lookup"><span data-stu-id="2e861-110">Literals</span></span> 

<span data-ttu-id="2e861-111">Puede declarar e inicializar una variable `long` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="2e861-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="2e861-112">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `long`.</span><span class="sxs-lookup"><span data-stu-id="2e861-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> <span data-ttu-id="2e861-113">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="2e861-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="2e861-114">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="2e861-114">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="2e861-115">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="2e861-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="2e861-116">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="2e861-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="2e861-117">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="2e861-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="2e861-118">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="2e861-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="2e861-119">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2e861-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="2e861-120">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="2e861-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="2e861-121">El sufijo `L` denota un `long`.</span><span class="sxs-lookup"><span data-stu-id="2e861-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="2e861-122">En el ejemplo siguiente se usa el sufijo `L` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="2e861-122">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="2e861-123">También puede usar la letra minúscula "l" como sufijo,</span><span class="sxs-lookup"><span data-stu-id="2e861-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="2e861-124">aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1".</span><span class="sxs-lookup"><span data-stu-id="2e861-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="2e861-125">Use "L" para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="2e861-125">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="2e861-126">Cuando se usa el sufijo `L`, se determina que el tipo del entero literal es `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md), según su tamaño.</span><span class="sxs-lookup"><span data-stu-id="2e861-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="2e861-127">En este caso, es `long` porque es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="2e861-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="2e861-128">El sufijo se usa habitualmente para llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="2e861-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="2e861-129">Por ejemplo, los siguientes métodos sobrecargados tienen parámetros de tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="2e861-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="2e861-130">El sufijo `L` garantiza que se llame a la sobrecarga correcta:</span><span class="sxs-lookup"><span data-stu-id="2e861-130">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="2e861-131">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="2e861-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="2e861-132">int</span><span class="sxs-lookup"><span data-stu-id="2e861-132">int</span></span>](int.md)
2. [<span data-ttu-id="2e861-133">uint</span><span class="sxs-lookup"><span data-stu-id="2e861-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="2e861-134">ulong</span><span class="sxs-lookup"><span data-stu-id="2e861-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="2e861-135">El literal 4294967296 de los ejemplos anteriores es de tipo `long` porque supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="2e861-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="2e861-136">Si usa el tipo `long` con otros tipos enteros en la misma expresión, la expresión se evalúa como `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas).</span><span class="sxs-lookup"><span data-stu-id="2e861-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="2e861-137">Por ejemplo, la siguiente expresión se evalúa como `long`:</span><span class="sxs-lookup"><span data-stu-id="2e861-137">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="2e861-138">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="2e861-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="2e861-139">Conversiones</span><span class="sxs-lookup"><span data-stu-id="2e861-139">Conversions</span></span>  
 <span data-ttu-id="2e861-140">Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="2e861-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="2e861-141">De lo contrario, se debe usar una conversión.</span><span class="sxs-lookup"><span data-stu-id="2e861-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="2e861-142">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="2e861-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int y = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="2e861-143">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.</span><span class="sxs-lookup"><span data-stu-id="2e861-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="2e861-144">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `long`.</span><span class="sxs-lookup"><span data-stu-id="2e861-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="2e861-145">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="2e861-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="2e861-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2e861-146">C# Language Specification</span></span>  

<span data-ttu-id="2e861-147">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e861-147">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="2e861-148">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="2e861-148">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e861-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e861-149">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="2e861-150">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2e861-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2e861-151">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2e861-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2e861-152">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="2e861-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="2e861-153">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="2e861-153">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="2e861-154">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="2e861-154">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="2e861-155">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="2e861-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="2e861-156">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="2e861-156">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
