---
title: ushort (Palabra clave, Referencia de C#)
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 934e25576a8a24c176a54ec6af984459b513fe5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614468"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="c01c6-102">ushort (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c01c6-102">ushort (C# Reference)</span></span>

<span data-ttu-id="c01c6-103">La palabra clave `ushort` indica un tipo de datos entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c01c6-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="c01c6-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="c01c6-104">Type</span></span>|<span data-ttu-id="c01c6-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="c01c6-105">Range</span></span>|<span data-ttu-id="c01c6-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="c01c6-106">Size</span></span>|<span data-ttu-id="c01c6-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="c01c6-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ushort`|<span data-ttu-id="c01c6-108">De 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="c01c6-108">0 to 65,535</span></span>|<span data-ttu-id="c01c6-109">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="c01c6-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="c01c6-110">Literales</span><span class="sxs-lookup"><span data-stu-id="c01c6-110">Literals</span></span>

<span data-ttu-id="c01c6-111">Puede declarar e inicializar una variable `ushort` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="c01c6-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="c01c6-112">Si el literal entero está fuera del intervalo de `ushort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="c01c6-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="c01c6-113">En el ejemplo siguiente, los enteros que equivalen a 65 034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](int.md) a valores `ushort`.</span><span class="sxs-lookup"><span data-stu-id="c01c6-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `ushort` values.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]

> [!NOTE]
> <span data-ttu-id="c01c6-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="c01c6-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c01c6-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="c01c6-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c01c6-116">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad:</span><span class="sxs-lookup"><span data-stu-id="c01c6-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="c01c6-117">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="c01c6-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="c01c6-118">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="c01c6-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="c01c6-119">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="c01c6-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="c01c6-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c01c6-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="c01c6-121">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="c01c6-121">Compiler overload resolution</span></span>

<span data-ttu-id="c01c6-122">Debe usarse una conversión al llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="c01c6-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="c01c6-123">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ushort` e [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="c01c6-123">Consider, for example, the following overloaded methods that use `ushort` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ushort s) {}
```

<span data-ttu-id="c01c6-124">El uso de la conversión `ushort` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c01c6-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calls the method with the int parameter:
SampleMethod(5);
// Calls the method with the ushort parameter:
SampleMethod((ushort)5);
```

## <a name="conversions"></a><span data-ttu-id="c01c6-125">Conversiones</span><span class="sxs-lookup"><span data-stu-id="c01c6-125">Conversions</span></span>

<span data-ttu-id="c01c6-126">Hay una conversión implícita predefinida de `ushort` a [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="c01c6-126">There is a predefined implicit conversion from `ushort` to [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="c01c6-127">Hay una conversión implícita predefinida de [byte](byte.md) o [char](char.md) a `ushort`.</span><span class="sxs-lookup"><span data-stu-id="c01c6-127">There is a predefined implicit conversion from [byte](byte.md) or [char](char.md) to `ushort`.</span></span> <span data-ttu-id="c01c6-128">De lo contrario, se debe usar una conversión para realizar una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="c01c6-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="c01c6-129">Por ejemplo, considere las dos variables de `ushort` siguientes, `x` y `y`:</span><span class="sxs-lookup"><span data-stu-id="c01c6-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>

```csharp
ushort x = 5, y = 12;
```

<span data-ttu-id="c01c6-130">La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética de la derecha del operador de asignación da como resultado `int` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c01c6-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>

```csharp
ushort z = x + y;   // Error: conversion from int to ushort
```

<span data-ttu-id="c01c6-131">Para corregir este problema, use una conversión:</span><span class="sxs-lookup"><span data-stu-id="c01c6-131">To fix this problem, use a cast:</span></span>

```csharp
ushort z = (ushort)(x + y);   // OK: explicit conversion
```

<span data-ttu-id="c01c6-132">Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="c01c6-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="c01c6-133">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `ushort`.</span><span class="sxs-lookup"><span data-stu-id="c01c6-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="c01c6-134">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="c01c6-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ushort x = 3.0;
// OK -- explicit conversion:
ushort y = (ushort)3.0;
```

<span data-ttu-id="c01c6-135">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="c01c6-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="c01c6-136">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c01c6-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c01c6-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c01c6-137">C# language specification</span></span>

<span data-ttu-id="c01c6-138">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c01c6-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="c01c6-139">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c01c6-139">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c01c6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c01c6-140">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="c01c6-141">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c01c6-141">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c01c6-142">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c01c6-142">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c01c6-143">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="c01c6-143">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c01c6-144">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="c01c6-144">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="c01c6-145">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="c01c6-145">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="c01c6-146">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="c01c6-146">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="c01c6-147">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="c01c6-147">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
