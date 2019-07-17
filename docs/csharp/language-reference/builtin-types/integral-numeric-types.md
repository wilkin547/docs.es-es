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
ms.openlocfilehash: 0a1ed01d9e6cb86ea177e8b947627f9dc02eedae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744220"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="666ed-103">Tipos numéricos enteros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="666ed-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="666ed-104">Los **tipos numéricos enteros** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#integral-literals).</span><span class="sxs-lookup"><span data-stu-id="666ed-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="666ed-105">Todos los tipos enteros también son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="666ed-105">All integral types are also value types.</span></span>

<span data-ttu-id="666ed-106">Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación e igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="666ed-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="666ed-107">Tamaños e intervalos</span><span class="sxs-lookup"><span data-stu-id="666ed-107">Sizes and ranges</span></span>

<span data-ttu-id="666ed-108">En la siguiente tabla, se muestran los tamaños e intervalos de los tipos enteros:</span><span class="sxs-lookup"><span data-stu-id="666ed-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="666ed-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="666ed-109">Type</span></span>|<span data-ttu-id="666ed-110">Intervalo</span><span class="sxs-lookup"><span data-stu-id="666ed-110">Range</span></span>|<span data-ttu-id="666ed-111">Tamaño</span><span class="sxs-lookup"><span data-stu-id="666ed-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="666ed-112">De -128 a 127</span><span class="sxs-lookup"><span data-stu-id="666ed-112">-128 to 127</span></span>|<span data-ttu-id="666ed-113">Entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="666ed-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="666ed-114">De 0 a 255</span><span class="sxs-lookup"><span data-stu-id="666ed-114">0 to 255</span></span>|<span data-ttu-id="666ed-115">Entero de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="666ed-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="666ed-116">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="666ed-116">-32,768 to 32,767</span></span>|<span data-ttu-id="666ed-117">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="666ed-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="666ed-118">De 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="666ed-118">0 to 65,535</span></span>|<span data-ttu-id="666ed-119">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="666ed-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="666ed-120">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="666ed-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="666ed-121">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="666ed-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="666ed-122">De 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="666ed-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="666ed-123">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="666ed-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="666ed-124">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="666ed-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="666ed-125">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="666ed-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="666ed-126">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="666ed-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="666ed-127">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="666ed-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="666ed-128">El valor predeterminado para todos los tipos enteros es `0`.</span><span class="sxs-lookup"><span data-stu-id="666ed-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="666ed-129">Cada uno de los tipos enteros tiene constantes denominadas `MinValue` y `MaxValue` para el valor mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="666ed-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="666ed-130">Use la estructura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> para representar un entero con signo sin límite superior ni inferior.</span><span class="sxs-lookup"><span data-stu-id="666ed-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="666ed-131">Literales enteros</span><span class="sxs-lookup"><span data-stu-id="666ed-131">Integral literals</span></span>

<span data-ttu-id="666ed-132">Los literales enteros pueden especificarse como *literales decimales*, *literales hexadecimales* o *literales binarios*.</span><span class="sxs-lookup"><span data-stu-id="666ed-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="666ed-133">A continuación se muestra un ejemplo de cada uno:</span><span class="sxs-lookup"><span data-stu-id="666ed-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="666ed-134">Los literales decimales no requieren ningún prefijo.</span><span class="sxs-lookup"><span data-stu-id="666ed-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="666ed-135">El prefijo `x` o `X` significa un *literal hexadecimal*.</span><span class="sxs-lookup"><span data-stu-id="666ed-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="666ed-136">El prefijo `b` o `B` significa un *literal binario*.</span><span class="sxs-lookup"><span data-stu-id="666ed-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="666ed-137">La declaración de `binaryLiteral` muestra el uso de `_` como un *separador de dígitos*.</span><span class="sxs-lookup"><span data-stu-id="666ed-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="666ed-138">El separador de dígitos también se puede usar con todos los literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="666ed-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="666ed-139">Los literales binarios y el separador de dígitos `_` se admiten a partir de C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="666ed-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="666ed-140">Sufijos literales</span><span class="sxs-lookup"><span data-stu-id="666ed-140">Literal suffixes</span></span> 

<span data-ttu-id="666ed-141">El sufijo `l` o `L` especifica que el literal entero debe ser del tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="666ed-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="666ed-142">El sufijo `ul` o `UL` especifica el tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="666ed-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="666ed-143">Si el sufijo `L` se usa en un literal que es mayor de 9 223 372 036 854 775 807 (el valor máximo de `long`), el valor se convierte en el tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="666ed-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="666ed-144">Si el valor que representa un literal integral supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="666ed-144">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="666ed-145">Puede usar la letra minúscula "l" como sufijo,</span><span class="sxs-lookup"><span data-stu-id="666ed-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="666ed-146">aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1".</span><span class="sxs-lookup"><span data-stu-id="666ed-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="666ed-147">Use "L" para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="666ed-147">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="666ed-148">Tipo de un literal entero</span><span class="sxs-lookup"><span data-stu-id="666ed-148">Type of an integral literal</span></span>

<span data-ttu-id="666ed-149">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="666ed-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="666ed-150">Puede convertir un literal entero en un tipo con un rango menor que el valor predeterminado mediante una asignación o una conversión:</span><span class="sxs-lookup"><span data-stu-id="666ed-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="666ed-151">Puede convertir un literal entero en un tipo con un rango mayor que el valor predeterminado mediante una asignación, una conversión o un sufijo en el literal:</span><span class="sxs-lookup"><span data-stu-id="666ed-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="666ed-152">Conversiones</span><span class="sxs-lookup"><span data-stu-id="666ed-152">Conversions</span></span>

<span data-ttu-id="666ed-153">Hay una conversión implícita (llamada *conversión de ampliación*) entre los dos tipos enteros donde el tipo de destino puede almacenar todos los valores del tipo de origen.</span><span class="sxs-lookup"><span data-stu-id="666ed-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="666ed-154">Por ejemplo, hay una conversión implícita de `int` a `long` porque el rango de valores de `int` es un subconjunto apropiado de `long`.</span><span class="sxs-lookup"><span data-stu-id="666ed-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="666ed-155">Hay conversiones implícitas de un tipo entero sin signo más pequeño en un tipo entero con signo de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="666ed-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="666ed-156">También hay una conversión implícita de cualquier tipo entero en cualquier tipo de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="666ed-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="666ed-157">No hay ninguna conversión implícita de ningún tipo entero con signo en ningún tipo entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="666ed-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="666ed-158">Debe usar una conversión explícita para convertir un tipo entero en otro tipo entero cuando no se define una conversión implícita del tipo de origen en el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="666ed-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="666ed-159">Esto se denomina *conversión de restricción*.</span><span class="sxs-lookup"><span data-stu-id="666ed-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="666ed-160">El caso explícito es necesario porque la conversión puede producir pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="666ed-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="666ed-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="666ed-161">See also</span></span>

- [<span data-ttu-id="666ed-162">Especificación del lenguaje C# - Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="666ed-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="666ed-163">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="666ed-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="666ed-164">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="666ed-164">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="666ed-165">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="666ed-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="666ed-166">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="666ed-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="666ed-167">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="666ed-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="666ed-168">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="666ed-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
