---
title: Tipos numéricos enteros - Referencia de C#
description: Obtenga información sobre el intervalo, el tamaño de almacenamiento y el uso de cada uno de los tipos numéricos enteros.
ms.date: 06/25/2019
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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236076"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="e9815-103">Tipos numéricos enteros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e9815-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="e9815-104">Los **tipos numéricos enteros** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#integral-literals).</span><span class="sxs-lookup"><span data-stu-id="e9815-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="e9815-105">Todos los tipos enteros también son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="e9815-105">All integral types are also value types.</span></span> <span data-ttu-id="e9815-106">Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación e igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e9815-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="e9815-107">Características de los tipos enteros</span><span class="sxs-lookup"><span data-stu-id="e9815-107">Characteristics of the integral types</span></span>

<span data-ttu-id="e9815-108">C# admite los siguientes tipos enteros predefinidos:</span><span class="sxs-lookup"><span data-stu-id="e9815-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="e9815-109">Palabra clave/tipo de C#</span><span class="sxs-lookup"><span data-stu-id="e9815-109">C# type/keyword</span></span>|<span data-ttu-id="e9815-110">Intervalo</span><span class="sxs-lookup"><span data-stu-id="e9815-110">Range</span></span>|<span data-ttu-id="e9815-111">Tamaño</span><span class="sxs-lookup"><span data-stu-id="e9815-111">Size</span></span>|<span data-ttu-id="e9815-112">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="e9815-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="e9815-113">De -128 a 127</span><span class="sxs-lookup"><span data-stu-id="e9815-113">-128 to 127</span></span>|<span data-ttu-id="e9815-114">Entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e9815-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="e9815-115">De 0 a 255</span><span class="sxs-lookup"><span data-stu-id="e9815-115">0 to 255</span></span>|<span data-ttu-id="e9815-116">Entero de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e9815-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="e9815-117">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="e9815-117">-32,768 to 32,767</span></span>|<span data-ttu-id="e9815-118">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e9815-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="e9815-119">De 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="e9815-119">0 to 65,535</span></span>|<span data-ttu-id="e9815-120">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e9815-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="e9815-121">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="e9815-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="e9815-122">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e9815-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="e9815-123">De 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="e9815-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="e9815-124">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e9815-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="e9815-125">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="e9815-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="e9815-126">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e9815-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="e9815-127">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="e9815-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="e9815-128">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e9815-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="e9815-129">En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e9815-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="e9815-130">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="e9815-130">They are interchangeable.</span></span> <span data-ttu-id="e9815-131">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="e9815-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="e9815-132">El valor predeterminado de cada tipo entero es cero, `0`.</span><span class="sxs-lookup"><span data-stu-id="e9815-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="e9815-133">Cada uno de los tipos enteros tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="e9815-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="e9815-134">Use la estructura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> para representar un entero con signo sin límite superior ni inferior.</span><span class="sxs-lookup"><span data-stu-id="e9815-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="e9815-135">Literales enteros</span><span class="sxs-lookup"><span data-stu-id="e9815-135">Integral literals</span></span>

<span data-ttu-id="e9815-136">Los literales enteros pueden especificarse como *literales decimales*, *literales hexadecimales* o *literales binarios*.</span><span class="sxs-lookup"><span data-stu-id="e9815-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="e9815-137">A continuación se muestra un ejemplo de cada uno:</span><span class="sxs-lookup"><span data-stu-id="e9815-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="e9815-138">Los literales decimales no requieren ningún prefijo.</span><span class="sxs-lookup"><span data-stu-id="e9815-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="e9815-139">El prefijo `x` o `X` significa un *literal hexadecimal*.</span><span class="sxs-lookup"><span data-stu-id="e9815-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="e9815-140">El prefijo `b` o `B` significa un *literal binario*.</span><span class="sxs-lookup"><span data-stu-id="e9815-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="e9815-141">La declaración de `binaryLiteral` muestra el uso de `_` como un *separador de dígitos*.</span><span class="sxs-lookup"><span data-stu-id="e9815-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="e9815-142">El separador de dígitos también se puede usar con todos los literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="e9815-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="e9815-143">Los literales binarios y el separador de dígitos `_` se admiten a partir de C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="e9815-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="e9815-144">Sufijos literales</span><span class="sxs-lookup"><span data-stu-id="e9815-144">Literal suffixes</span></span>

<span data-ttu-id="e9815-145">El sufijo `l` o `L` especifica que el literal entero debe ser del tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="e9815-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="e9815-146">El sufijo `ul` o `UL` especifica el tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e9815-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="e9815-147">Si el sufijo `L` se usa en un literal que es mayor de 9 223 372 036 854 775 807 (el valor máximo de `long`), el valor se convierte en el tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e9815-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="e9815-148">Si el valor que representa un literal integral supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="e9815-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="e9815-149">Puede usar la letra minúscula "l" como sufijo,</span><span class="sxs-lookup"><span data-stu-id="e9815-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="e9815-150">aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1".</span><span class="sxs-lookup"><span data-stu-id="e9815-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="e9815-151">Use "L" para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="e9815-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="e9815-152">Tipo de un literal entero</span><span class="sxs-lookup"><span data-stu-id="e9815-152">Type of an integral literal</span></span>

<span data-ttu-id="e9815-153">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="e9815-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="e9815-154">Puede convertir un literal entero en un tipo con un rango menor que el valor predeterminado mediante una asignación o una conversión:</span><span class="sxs-lookup"><span data-stu-id="e9815-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="e9815-155">Puede convertir un literal entero en un tipo con un rango mayor que el valor predeterminado mediante una asignación, una conversión o un sufijo en el literal:</span><span class="sxs-lookup"><span data-stu-id="e9815-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="e9815-156">Conversiones</span><span class="sxs-lookup"><span data-stu-id="e9815-156">Conversions</span></span>

<span data-ttu-id="e9815-157">Hay una conversión implícita (llamada *conversión de ampliación*) entre los dos tipos enteros donde el tipo de destino puede almacenar todos los valores del tipo de origen.</span><span class="sxs-lookup"><span data-stu-id="e9815-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="e9815-158">Por ejemplo, hay una conversión implícita de `int` a `long` porque el rango de valores de `int` es un subconjunto apropiado de `long`.</span><span class="sxs-lookup"><span data-stu-id="e9815-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="e9815-159">Hay conversiones implícitas de un tipo entero sin signo más pequeño en un tipo entero con signo de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="e9815-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="e9815-160">También hay una conversión implícita de cualquier tipo entero en cualquier tipo de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e9815-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="e9815-161">No hay ninguna conversión implícita de ningún tipo entero con signo en ningún tipo entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="e9815-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="e9815-162">Debe usar una conversión explícita para convertir un tipo entero en otro tipo entero cuando no se define una conversión implícita del tipo de origen en el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e9815-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="e9815-163">Esto se denomina *conversión de restricción*.</span><span class="sxs-lookup"><span data-stu-id="e9815-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="e9815-164">El caso explícito es necesario porque la conversión puede producir pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="e9815-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9815-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9815-165">See also</span></span>

- [<span data-ttu-id="e9815-166">Especificación del lenguaje C# - Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="e9815-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="e9815-167">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e9815-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e9815-168">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="e9815-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="e9815-169">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="e9815-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="e9815-170">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="e9815-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="e9815-171">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="e9815-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="e9815-172">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="e9815-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
