---
title: ulong (palabra clave) (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: d0c7df4ebda13a59e51e9599699f6abf4bbf1d71
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143433"
---
# <a name="ulong-c-reference"></a><span data-ttu-id="26f6b-102">ulong (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="26f6b-102">ulong (C# Reference)</span></span>

<span data-ttu-id="26f6b-103">La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="26f6b-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="26f6b-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="26f6b-104">Type</span></span>|<span data-ttu-id="26f6b-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="26f6b-105">Range</span></span>|<span data-ttu-id="26f6b-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="26f6b-106">Size</span></span>|<span data-ttu-id="26f6b-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="26f6b-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ulong`|<span data-ttu-id="26f6b-108">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="26f6b-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="26f6b-109">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="26f6b-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="26f6b-110">Literales</span><span class="sxs-lookup"><span data-stu-id="26f6b-110">Literals</span></span>

<span data-ttu-id="26f6b-111">Puede declarar e inicializar una variable `ulong` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="26f6b-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="26f6b-112">Si el literal entero está fuera del intervalo de `ulong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="26f6b-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="26f6b-113">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ulong`.</span><span class="sxs-lookup"><span data-stu-id="26f6b-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> <span data-ttu-id="26f6b-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="26f6b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="26f6b-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="26f6b-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="26f6b-116">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad:</span><span class="sxs-lookup"><span data-stu-id="26f6b-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="26f6b-117">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="26f6b-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="26f6b-118">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="26f6b-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="26f6b-119">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="26f6b-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="26f6b-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="26f6b-120">Some examples are shown below.</span></span>

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

<span data-ttu-id="26f6b-121">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="26f6b-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="26f6b-122">El sufijo `UL` o `ul` identifica de manera inequívoca un literal numérico como un valor `ulong`.</span><span class="sxs-lookup"><span data-stu-id="26f6b-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="26f6b-123">El sufijo `L` denota un `ulong` si el valor literal supera <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="26f6b-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="26f6b-124">Y el sufijo `U` o `u` denota un `ulong` si el valor literal supera <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="26f6b-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="26f6b-125">En el ejemplo siguiente se usa el sufijo `ul` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="26f6b-125">The following example uses the `ul` suffix to denote a long integer:</span></span>

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="26f6b-126">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="26f6b-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="26f6b-127">int</span><span class="sxs-lookup"><span data-stu-id="26f6b-127">int</span></span>](int.md)
2. [<span data-ttu-id="26f6b-128">uint</span><span class="sxs-lookup"><span data-stu-id="26f6b-128">uint</span></span>](uint.md)
3. [<span data-ttu-id="26f6b-129">long</span><span class="sxs-lookup"><span data-stu-id="26f6b-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="26f6b-130">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="26f6b-130">Compiler overload resolution</span></span>

<span data-ttu-id="26f6b-131">El sufijo se usa habitualmente en las llamadas a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="26f6b-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="26f6b-132">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ulong` e [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="26f6b-132">Consider, for example, the following overloaded methods that use `ulong` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

<span data-ttu-id="26f6b-133">Si se usa un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26f6b-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a><span data-ttu-id="26f6b-134">Conversiones</span><span class="sxs-lookup"><span data-stu-id="26f6b-134">Conversions</span></span>

<span data-ttu-id="26f6b-135">Existe una conversión implícita predefinida de `ulong` a [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="26f6b-135">There is a predefined implicit conversion from `ulong` to [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="26f6b-136">No existe conversión implícita de `ulong` a cualquier tipo entero.</span><span class="sxs-lookup"><span data-stu-id="26f6b-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="26f6b-137">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="26f6b-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

<span data-ttu-id="26f6b-138">Existe una conversión implícita predefinida de [byte](byte.md), [ushort](ushort.md), [uint](uint.md) o [char](char.md) a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="26f6b-138">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), [uint](uint.md), or [char](char.md) to `ulong`.</span></span>

<span data-ttu-id="26f6b-139">Además, no hay ninguna conversión implícita de tipos de punto flotante a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="26f6b-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="26f6b-140">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="26f6b-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

<span data-ttu-id="26f6b-141">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="26f6b-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="26f6b-142">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="26f6b-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="26f6b-143">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="26f6b-143">C# language specification</span></span>

<span data-ttu-id="26f6b-144">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="26f6b-144">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="26f6b-145">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="26f6b-145">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="26f6b-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="26f6b-146">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="26f6b-147">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="26f6b-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="26f6b-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="26f6b-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="26f6b-149">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="26f6b-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="26f6b-150">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="26f6b-150">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="26f6b-151">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="26f6b-151">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="26f6b-152">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="26f6b-152">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="26f6b-153">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="26f6b-153">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
