---
title: Tipos numéricos enteros - Referencia de C#
description: Obtenga información sobre el intervalo, el tamaño de almacenamiento y el uso de cada uno de los tipos numéricos enteros.
ms.date: 10/22/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 51ea64065ea8422e5885022105545780bc916f06
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739004"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="50b08-103">Tipos numéricos enteros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="50b08-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="50b08-104">Los *tipos numéricos integrales* representan números enteros.</span><span class="sxs-lookup"><span data-stu-id="50b08-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="50b08-105">Todos los tipos numéricos integrales son [tipos de valor](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="50b08-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="50b08-106">También son [tipos simples](value-types.md#built-in-value-types) y se pueden inicializar con [literales](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="50b08-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="50b08-107">Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="50b08-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="50b08-108">Características de los tipos enteros</span><span class="sxs-lookup"><span data-stu-id="50b08-108">Characteristics of the integral types</span></span>

<span data-ttu-id="50b08-109">C# admite los siguientes tipos enteros predefinidos:</span><span class="sxs-lookup"><span data-stu-id="50b08-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="50b08-110">Palabra clave/tipo de C#</span><span class="sxs-lookup"><span data-stu-id="50b08-110">C# type/keyword</span></span>|<span data-ttu-id="50b08-111">Intervalo</span><span class="sxs-lookup"><span data-stu-id="50b08-111">Range</span></span>|<span data-ttu-id="50b08-112">Tamaño</span><span class="sxs-lookup"><span data-stu-id="50b08-112">Size</span></span>|<span data-ttu-id="50b08-113">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="50b08-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="50b08-114">De -128 a 127</span><span class="sxs-lookup"><span data-stu-id="50b08-114">-128 to 127</span></span>|<span data-ttu-id="50b08-115">Entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="50b08-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="50b08-116">De 0 a 255</span><span class="sxs-lookup"><span data-stu-id="50b08-116">0 to 255</span></span>|<span data-ttu-id="50b08-117">Entero de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="50b08-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="50b08-118">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="50b08-118">-32,768 to 32,767</span></span>|<span data-ttu-id="50b08-119">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="50b08-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="50b08-120">De 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="50b08-120">0 to 65,535</span></span>|<span data-ttu-id="50b08-121">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="50b08-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="50b08-122">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="50b08-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="50b08-123">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="50b08-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="50b08-124">De 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="50b08-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="50b08-125">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="50b08-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="50b08-126">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="50b08-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="50b08-127">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="50b08-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="50b08-128">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="50b08-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="50b08-129">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="50b08-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="50b08-130">En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="50b08-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="50b08-131">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="50b08-131">They are interchangeable.</span></span> <span data-ttu-id="50b08-132">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="50b08-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="50b08-133">El valor predeterminado de cada tipo entero es cero, `0`.</span><span class="sxs-lookup"><span data-stu-id="50b08-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="50b08-134">Cada uno de los tipos enteros tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="50b08-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="50b08-135">Use la estructura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> para representar un entero con signo sin límite superior ni inferior.</span><span class="sxs-lookup"><span data-stu-id="50b08-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="50b08-136">Literales enteros</span><span class="sxs-lookup"><span data-stu-id="50b08-136">Integer literals</span></span>

<span data-ttu-id="50b08-137">Los literales enteros pueden ser</span><span class="sxs-lookup"><span data-stu-id="50b08-137">Integer literals can be</span></span>

- <span data-ttu-id="50b08-138">*decimales*: sin ningún prefijo</span><span class="sxs-lookup"><span data-stu-id="50b08-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="50b08-139">*hexadecimales*: con el prefijo de `0x` o `0X`</span><span class="sxs-lookup"><span data-stu-id="50b08-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="50b08-140">*binarios*: con el prefijo `0b` o `0B` (disponible en C# 7.0 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="50b08-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="50b08-141">En el código siguiente se muestra un ejemplo de cada uno de ellos:</span><span class="sxs-lookup"><span data-stu-id="50b08-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="50b08-142">En el ejemplo anterior también se muestra el uso de `_` como un *separador de dígitos*, que se admite a partir de C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="50b08-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="50b08-143">Puede usar el separador de dígitos con todos los tipos de literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="50b08-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="50b08-144">El tipo de un literal entero viene determinado por su sufijo, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="50b08-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="50b08-145">Si el literal no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `int`, `uint`, `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="50b08-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="50b08-146">Si un literal entero tiene el sufijo `U` o `u`, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="50b08-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="50b08-147">Si un literal entero tiene el sufijo `L` o `l`, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="50b08-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="50b08-148">Puede usar la letra minúscula `l` como sufijo.</span><span class="sxs-lookup"><span data-stu-id="50b08-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="50b08-149">Sin embargo, esto genera una advertencia del compilador porque la letra `l` se confunde fácilmente con el dígito `1`.</span><span class="sxs-lookup"><span data-stu-id="50b08-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="50b08-150">Use `L` para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="50b08-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="50b08-151">Si el literal tiene como sufijo `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` o `lu`, su tipo es `ulong`.</span><span class="sxs-lookup"><span data-stu-id="50b08-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="50b08-152">Si el valor que representa un literal entero supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="50b08-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="50b08-153">Si el tipo determinado de un literal entero es `int` y el valor que representa el literal está dentro del rango del tipo de destino, el valor se puede convertir de forma implícita en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`:</span><span class="sxs-lookup"><span data-stu-id="50b08-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="50b08-154">Como se muestra en el ejemplo anterior, si el valor del literal no está dentro del intervalo del tipo de destino, se produce el error [CS0031](../../misc/cs0031.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="50b08-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="50b08-155">También puede usar una conversión para convertir el valor representado por un literal entero en un tipo que no sea el determinado del literal:</span><span class="sxs-lookup"><span data-stu-id="50b08-155">You can also use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="50b08-156">Conversiones</span><span class="sxs-lookup"><span data-stu-id="50b08-156">Conversions</span></span>

<span data-ttu-id="50b08-157">Puede convertir un tipo numérico entero en cualquier otro tipo numérico entero.</span><span class="sxs-lookup"><span data-stu-id="50b08-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="50b08-158">Si el tipo de destino puede almacenar todos los valores del tipo de origen, la conversión es implícita.</span><span class="sxs-lookup"><span data-stu-id="50b08-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="50b08-159">De lo contrario, debe usar una [expresión Cast](../operators/type-testing-and-cast.md#cast-expression) para realizar una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="50b08-159">Otherwise, you need to use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span> <span data-ttu-id="50b08-160">Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="50b08-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="50b08-161">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="50b08-161">C# language specification</span></span>

<span data-ttu-id="50b08-162">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="50b08-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="50b08-163">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="50b08-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="50b08-164">Literales enteros</span><span class="sxs-lookup"><span data-stu-id="50b08-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="50b08-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b08-165">See also</span></span>

- [<span data-ttu-id="50b08-166">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="50b08-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="50b08-167">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="50b08-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="50b08-168">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="50b08-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="50b08-169">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="50b08-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="50b08-170">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="50b08-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
