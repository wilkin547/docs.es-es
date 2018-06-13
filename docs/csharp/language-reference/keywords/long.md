---
title: long (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: f2bdc34400215ad24d5dcec2e1e9f314a01430d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288459"
---
# <a name="long-c-reference"></a><span data-ttu-id="ab2cd-102">long (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ab2cd-102">long (C# Reference)</span></span>

<span data-ttu-id="ab2cd-103">`long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="ab2cd-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab2cd-104">Type</span></span>|<span data-ttu-id="ab2cd-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="ab2cd-105">Range</span></span>|<span data-ttu-id="ab2cd-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="ab2cd-106">Size</span></span>|<span data-ttu-id="ab2cd-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab2cd-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="ab2cd-108">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="ab2cd-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="ab2cd-109">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="ab2cd-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="ab2cd-110">Literales</span><span class="sxs-lookup"><span data-stu-id="ab2cd-110">Literals</span></span> 

<span data-ttu-id="ab2cd-111">Puede declarar e inicializar una variable `long` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="ab2cd-112">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `long`.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> <span data-ttu-id="ab2cd-113">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="ab2cd-114">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-114">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="ab2cd-115">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="ab2cd-116">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="ab2cd-117">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="ab2cd-118">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="ab2cd-119">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="ab2cd-120">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="ab2cd-121">El sufijo `L` denota un `long`.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="ab2cd-122">En el ejemplo siguiente se usa el sufijo `L` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-122">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="ab2cd-123">También puede usar la letra minúscula "l" como sufijo,</span><span class="sxs-lookup"><span data-stu-id="ab2cd-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="ab2cd-124">aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1".</span><span class="sxs-lookup"><span data-stu-id="ab2cd-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="ab2cd-125">Use "L" para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-125">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="ab2cd-126">Cuando se usa el sufijo `L`, se determina que el tipo del entero literal es `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md), según su tamaño.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="ab2cd-127">En este caso, es `long` porque es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="ab2cd-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="ab2cd-128">El sufijo se usa habitualmente para llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="ab2cd-129">Por ejemplo, los siguientes métodos sobrecargados tienen parámetros de tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="ab2cd-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="ab2cd-130">El sufijo `L` garantiza que se llame a la sobrecarga correcta:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-130">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="ab2cd-131">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="ab2cd-132">int</span><span class="sxs-lookup"><span data-stu-id="ab2cd-132">int</span></span>](int.md)
2. [<span data-ttu-id="ab2cd-133">uint</span><span class="sxs-lookup"><span data-stu-id="ab2cd-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="ab2cd-134">ulong</span><span class="sxs-lookup"><span data-stu-id="ab2cd-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="ab2cd-135">El literal 4294967296 de los ejemplos anteriores es de tipo `long` porque supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="ab2cd-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="ab2cd-136">Si usa el tipo `long` con otros tipos enteros en la misma expresión, la expresión se evalúa como `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas).</span><span class="sxs-lookup"><span data-stu-id="ab2cd-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="ab2cd-137">Por ejemplo, la siguiente expresión se evalúa como `long`:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-137">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="ab2cd-138">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="ab2cd-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="ab2cd-139">Conversiones</span><span class="sxs-lookup"><span data-stu-id="ab2cd-139">Conversions</span></span>  
 <span data-ttu-id="ab2cd-140">Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="ab2cd-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="ab2cd-141">De lo contrario, se debe usar una conversión.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="ab2cd-142">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="ab2cd-143">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="ab2cd-144">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `long`.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="ab2cd-145">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="ab2cd-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="ab2cd-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ab2cd-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab2cd-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab2cd-147">See Also</span></span>  
 <xref:System.Int64>  
 [<span data-ttu-id="ab2cd-148">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ab2cd-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ab2cd-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ab2cd-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ab2cd-150">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ab2cd-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ab2cd-151">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="ab2cd-151">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="ab2cd-152">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="ab2cd-152">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="ab2cd-153">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="ab2cd-153">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="ab2cd-154">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="ab2cd-154">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
