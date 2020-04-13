---
title: Tipos numéricos de punto flotante - referencia de C#
description: 'Información sobre los tipos de punto flotante de C# integrados: float, double y decimal'
ms.date: 02/10/2020
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: a277215d438b5f6b0bbbef72e5e0121b6ce41990
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121482"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="1e052-103">Tipos numéricos de punto flotante (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1e052-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="1e052-104">Los *tipos numéricos de punto flotante* representan números reales.</span><span class="sxs-lookup"><span data-stu-id="1e052-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="1e052-105">Todos los tipos numéricos de punto flotante son [tipos de valor](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="1e052-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="1e052-106">También son [tipos simples](value-types.md#built-in-value-types) y se pueden inicializar con [literales](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="1e052-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="1e052-107">Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md), [de comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1e052-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="1e052-108">Características de los tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="1e052-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="1e052-109">C# admite los siguientes tipos de punto flotante predefinidos:</span><span class="sxs-lookup"><span data-stu-id="1e052-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="1e052-110">Palabra clave/tipo de C#</span><span class="sxs-lookup"><span data-stu-id="1e052-110">C# type/keyword</span></span>|<span data-ttu-id="1e052-111">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="1e052-111">Approximate range</span></span>|<span data-ttu-id="1e052-112">Precisión</span><span class="sxs-lookup"><span data-stu-id="1e052-112">Precision</span></span>|<span data-ttu-id="1e052-113">Tamaño</span><span class="sxs-lookup"><span data-stu-id="1e052-113">Size</span></span>|<span data-ttu-id="1e052-114">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="1e052-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="1e052-115">De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="1e052-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="1e052-116">De 6 a 9 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="1e052-116">~6-9 digits</span></span>|<span data-ttu-id="1e052-117">4 bytes</span><span class="sxs-lookup"><span data-stu-id="1e052-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="1e052-118">De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="1e052-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="1e052-119">De 15 a 17 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="1e052-119">~15-17 digits</span></span>|<span data-ttu-id="1e052-120">8 bytes</span><span class="sxs-lookup"><span data-stu-id="1e052-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="1e052-121">De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="1e052-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="1e052-122">28-29 dígitos</span><span class="sxs-lookup"><span data-stu-id="1e052-122">28-29 digits</span></span>|<span data-ttu-id="1e052-123">16 bytes</span><span class="sxs-lookup"><span data-stu-id="1e052-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="1e052-124">En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1e052-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="1e052-125">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="1e052-125">They are interchangeable.</span></span> <span data-ttu-id="1e052-126">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="1e052-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="1e052-127">El valor predeterminado de cada tipo de punto flotante es cero, `0`.</span><span class="sxs-lookup"><span data-stu-id="1e052-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="1e052-128">Cada uno de los tipos de punto flotante tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor finito mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="1e052-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="1e052-129">Los tipos `float` y `double` también brindan constantes que representan valores infinitos y no numéricos.</span><span class="sxs-lookup"><span data-stu-id="1e052-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="1e052-130">Por ejemplo, el tipo `double` ofrece las siguientes constantes: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> y <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e052-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1e052-131">Como el tipo `decimal` tiene más precisión y un intervalo más reducido que `float` y `double`, es adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="1e052-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="1e052-132">En una expresión, puede combinar tipos [enteros](integral-numeric-types.md) y tipos `float` y `double`.</span><span class="sxs-lookup"><span data-stu-id="1e052-132">You can mix [integral](integral-numeric-types.md) types and the `float` and `double` types in an expression.</span></span> <span data-ttu-id="1e052-133">En este caso, los tipos enteros se convierten implícitamente en uno de los tipos de punto flotante y, si es necesario, el tipo `float` se convierte implícitamente en `double`.</span><span class="sxs-lookup"><span data-stu-id="1e052-133">In this case, integral types are implicitly converted to one of the floating-point types and, if necessary, the `float` type is implicitly converted to `double`.</span></span> <span data-ttu-id="1e052-134">La expresión se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="1e052-134">The expression is evaluated as follows:</span></span>

- <span data-ttu-id="1e052-135">Si hay un tipo `double` en la expresión, esta se evalúa como `double`, o bien como [`bool`](bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1e052-135">If there is `double` type in the expression, the expression evaluates to `double`, or to [`bool`](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="1e052-136">Si no hay un tipo `double` en la expresión, esta se evalúa como `float`, o bien como `bool` en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1e052-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="1e052-137">También es posible combinar en una expresión tipos enteros y el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1e052-137">You can also mix integral types and the `decimal` type in an expression.</span></span> <span data-ttu-id="1e052-138">En este caso, los tipos enteros se convierten implícitamente en el tipo `decimal` y la expresión se evalúa como `decimal`, o bien como `bool` en comparaciones relacionales y de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1e052-138">In this case, integral types are implicitly converted to the `decimal` type and the expression evaluates to `decimal`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="1e052-139">En una expresión, no se puede mezclar el tipo `decimal` con los tipos `float` y `double`.</span><span class="sxs-lookup"><span data-stu-id="1e052-139">You cannot mix the `decimal` type with the `float` and `double` types in an expression.</span></span> <span data-ttu-id="1e052-140">En este caso, si quiere realizar operaciones aritméticas, de comparación o de igualdad, debe convertir explícitamente los operandos del tipo `decimal` o a este mismo tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e052-140">In this case, if you want to perform arithmetic, comparison, or equality operations, you must explicitly convert the operands either from or to the `decimal` type, as the following example shows:</span></span>

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

<span data-ttu-id="1e052-141">Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="1e052-141">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="1e052-142">Literales reales</span><span class="sxs-lookup"><span data-stu-id="1e052-142">Real literals</span></span>

<span data-ttu-id="1e052-143">El tipo de un literal real viene determinado por su sufijo, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1e052-143">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="1e052-144">El literal sin sufijo o con el sufijo `d` o `D` es del tipo `double`</span><span class="sxs-lookup"><span data-stu-id="1e052-144">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="1e052-145">El literal con el sufijo `f` o `F` es del tipo `float`</span><span class="sxs-lookup"><span data-stu-id="1e052-145">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="1e052-146">El literal con el sufijo `m` o `M` es del tipo `decimal`</span><span class="sxs-lookup"><span data-stu-id="1e052-146">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="1e052-147">En el código siguiente se muestra un ejemplo de cada uno de ellos:</span><span class="sxs-lookup"><span data-stu-id="1e052-147">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="1e052-148">En el ejemplo anterior también se muestra el uso de `_` como un *separador de dígitos*, que se admite a partir de C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="1e052-148">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="1e052-149">Puede usar el separador de dígitos con todos los tipos de literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="1e052-149">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="1e052-150">También puede usar la notación científica; es decir, especificar una parte exponencial de un literal real, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e052-150">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="1e052-151">Conversiones</span><span class="sxs-lookup"><span data-stu-id="1e052-151">Conversions</span></span>

<span data-ttu-id="1e052-152">Solo hay una conversión implícita entre los tipos numéricos de punto flotante: de `float` a `double`.</span><span class="sxs-lookup"><span data-stu-id="1e052-152">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="1e052-153">Sin embargo, puede convertir un tipo de punto flotante a cualquier otro tipo de punto flotante con la [conversión explícita](../operators/type-testing-and-cast.md#cast-expression).</span><span class="sxs-lookup"><span data-stu-id="1e052-153">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-expression).</span></span> <span data-ttu-id="1e052-154">Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1e052-154">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1e052-155">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1e052-155">C# language specification</span></span>

<span data-ttu-id="1e052-156">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1e052-156">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1e052-157">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="1e052-157">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="1e052-158">El tipo decimal</span><span class="sxs-lookup"><span data-stu-id="1e052-158">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="1e052-159">Literales reales</span><span class="sxs-lookup"><span data-stu-id="1e052-159">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="1e052-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e052-160">See also</span></span>

- [<span data-ttu-id="1e052-161">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1e052-161">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1e052-162">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="1e052-162">Value types</span></span>](value-types.md)
- [<span data-ttu-id="1e052-163">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="1e052-163">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="1e052-164">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="1e052-164">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="1e052-165">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="1e052-165">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
