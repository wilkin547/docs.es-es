---
title: uint (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: e22468eea63ce082f2e9842e6ec307aba1888964
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241605"
---
# <a name="uint-c-reference"></a><span data-ttu-id="83336-102">uint (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="83336-102">uint (C# Reference)</span></span>

<span data-ttu-id="83336-103">La palabra clave `uint` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="83336-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="83336-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="83336-104">Type</span></span>|<span data-ttu-id="83336-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="83336-105">Range</span></span>|<span data-ttu-id="83336-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="83336-106">Size</span></span>|<span data-ttu-id="83336-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="83336-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="83336-108">De 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="83336-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="83336-109">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="83336-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="83336-110">**Nota**: El tipo `uint` no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="83336-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="83336-111">Use `int` siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="83336-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="83336-112">Literales</span><span class="sxs-lookup"><span data-stu-id="83336-112">Literals</span></span>

<span data-ttu-id="83336-113">Puede declarar e inicializar una variable `uint` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="83336-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="83336-114">Si el literal entero está fuera del intervalo de `uint` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="83336-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="83336-115">En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `uint`.</span><span class="sxs-lookup"><span data-stu-id="83336-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="83336-116">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="83336-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="83336-117">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="83336-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="83336-118">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad:</span><span class="sxs-lookup"><span data-stu-id="83336-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="83336-119">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="83336-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="83336-120">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="83336-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="83336-121">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="83336-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="83336-122">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="83336-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="83336-123">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="83336-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="83336-124">El sufijo `U` o "u" denota `uint` o `ulong`, dependiendo del valor numérico del literal.</span><span class="sxs-lookup"><span data-stu-id="83336-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="83336-125">En el ejemplo siguiente se usa el sufijo `u` para denotar un entero sin signo de ambos tipos.</span><span class="sxs-lookup"><span data-stu-id="83336-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="83336-126">Tenga en cuenta que el primer literal es `uint` porque su valor es inferior a <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, mientras que el segundo es `ulong` porque su valor es superior a <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83336-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="83336-127">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="83336-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="83336-128">int</span><span class="sxs-lookup"><span data-stu-id="83336-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="83336-129">long</span><span class="sxs-lookup"><span data-stu-id="83336-129">long</span></span>](long.md)
4. [<span data-ttu-id="83336-130">ulong</span><span class="sxs-lookup"><span data-stu-id="83336-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="83336-131">Conversiones</span><span class="sxs-lookup"><span data-stu-id="83336-131">Conversions</span></span>

<span data-ttu-id="83336-132">Existe una conversión implícita predefinida de `uint` a [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="83336-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="83336-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="83336-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="83336-134">Existe una conversión implícita predefinida de [byte](byte.md), [ushort](ushort.md) o [char](char.md) a `uint`.</span><span class="sxs-lookup"><span data-stu-id="83336-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="83336-135">De lo contrario, debe usar una conversión.</span><span class="sxs-lookup"><span data-stu-id="83336-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="83336-136">Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:</span><span class="sxs-lookup"><span data-stu-id="83336-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="83336-137">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `uint`.</span><span class="sxs-lookup"><span data-stu-id="83336-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="83336-138">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="83336-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="83336-139">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="83336-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="83336-140">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="83336-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="83336-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="83336-141">C# language specification</span></span>

<span data-ttu-id="83336-142">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="83336-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="83336-143">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="83336-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="83336-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="83336-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="83336-145">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="83336-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83336-146">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="83336-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83336-147">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="83336-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="83336-148">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="83336-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="83336-149">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="83336-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="83336-150">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="83336-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="83336-151">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="83336-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)