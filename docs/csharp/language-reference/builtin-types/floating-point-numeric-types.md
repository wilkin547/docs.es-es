---
title: Tipos numéricos de punto flotante - referencia de C#
description: Información general de los tipos de punto flotante integrados de C#
ms.date: 06/30/2019
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
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002193"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="6feb4-103">Tipos numéricos de punto flotante (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6feb4-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="6feb4-104">Los **tipos de punto flotante** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="6feb4-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="6feb4-105">Todos los tipos de punto flotante también son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="6feb4-105">All floating-point types are also value types.</span></span> <span data-ttu-id="6feb4-106">Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md) [de comparación e igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6feb4-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="6feb4-107">Características de los tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="6feb4-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="6feb4-108">C# admite los siguientes tipos de punto flotante predefinidos:</span><span class="sxs-lookup"><span data-stu-id="6feb4-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="6feb4-109">Palabra clave/tipo de C#</span><span class="sxs-lookup"><span data-stu-id="6feb4-109">C# type/keyword</span></span>|<span data-ttu-id="6feb4-110">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="6feb4-110">Approximate range</span></span>|<span data-ttu-id="6feb4-111">Precisión</span><span class="sxs-lookup"><span data-stu-id="6feb4-111">Precision</span></span>|<span data-ttu-id="6feb4-112">Tamaño</span><span class="sxs-lookup"><span data-stu-id="6feb4-112">Size</span></span>|<span data-ttu-id="6feb4-113">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="6feb4-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="6feb4-114">De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="6feb4-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="6feb4-115">De 6 a 9 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="6feb4-115">~6-9 digits</span></span>|<span data-ttu-id="6feb4-116">4 bytes</span><span class="sxs-lookup"><span data-stu-id="6feb4-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="6feb4-117">De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="6feb4-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="6feb4-118">De 15 a 17 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="6feb4-118">~15-17 digits</span></span>|<span data-ttu-id="6feb4-119">8 bytes</span><span class="sxs-lookup"><span data-stu-id="6feb4-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="6feb4-120">De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="6feb4-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="6feb4-121">28-29 dígitos</span><span class="sxs-lookup"><span data-stu-id="6feb4-121">28-29 digits</span></span>|<span data-ttu-id="6feb4-122">16 bytes</span><span class="sxs-lookup"><span data-stu-id="6feb4-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="6feb4-123">En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6feb4-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="6feb4-124">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="6feb4-124">They are interchangeable.</span></span> <span data-ttu-id="6feb4-125">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="6feb4-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="6feb4-126">El valor predeterminado de cada tipo de punto flotante es cero, `0`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="6feb4-127">Cada uno de los tipos de punto flotante tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor finito mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="6feb4-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="6feb4-128">Los tipos `float` y `double` también brindan constantes que representan valores infinitos y no numéricos.</span><span class="sxs-lookup"><span data-stu-id="6feb4-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="6feb4-129">Por ejemplo, el tipo `double` ofrece las siguientes constantes: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> y <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6feb4-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6feb4-130">Como el tipo `decimal` tiene más precisión y un intervalo más reducido que `float` y `double`, es adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="6feb4-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="6feb4-131">Puede combinar tipos [enteros](integral-numeric-types.md) y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="6feb4-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="6feb4-132">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="6feb4-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="6feb4-133">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6feb4-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="6feb4-134">Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="6feb4-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="6feb4-135">Si no hay ningún tipo `double` en la expresión, esta se evalúa como `float` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="6feb4-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="6feb4-136">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="6feb4-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="6feb4-137">Cero positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="6feb4-137">Positive and negative zero</span></span>
- <span data-ttu-id="6feb4-138">Infinito positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="6feb4-138">Positive and negative infinity</span></span>
- <span data-ttu-id="6feb4-139">Valor no numérico (NaN)</span><span class="sxs-lookup"><span data-stu-id="6feb4-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="6feb4-140">El conjunto finito de valores distintos de cero</span><span class="sxs-lookup"><span data-stu-id="6feb4-140">The finite set of nonzero values</span></span>

<span data-ttu-id="6feb4-141">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="6feb4-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="6feb4-142">Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="6feb4-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="6feb4-143">Literales de punto flotante</span><span class="sxs-lookup"><span data-stu-id="6feb4-143">Floating-point literals</span></span>

<span data-ttu-id="6feb4-144">De forma predeterminada, un literal numérico de punto flotante a la derecha del operador de asignación se trata como `double`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-144">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="6feb4-145">Puede usar sufijos para convertir un literal de punto flotante o entero a un tipo específico:</span><span class="sxs-lookup"><span data-stu-id="6feb4-145">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="6feb4-146">El sufijo `d` o `D` convierte un literal en `double`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-146">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="6feb4-147">El sufijo `f` o `F` convierte un literal en `float`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-147">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="6feb4-148">El sufijo `m` o `M` convierte un literal en `decimal`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-148">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="6feb4-149">En los siguientes ejemplos se muestra cada sufijo:</span><span class="sxs-lookup"><span data-stu-id="6feb4-149">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="6feb4-150">Conversiones</span><span class="sxs-lookup"><span data-stu-id="6feb4-150">Conversions</span></span>

<span data-ttu-id="6feb4-151">Hay una conversión implícita (llamada *conversión de ampliación*) desde `float` a `double` porque el intervalo de valores `float` es un subconjunto apropiado de `double` y no hay ninguna pérdida de precisión de `float` a `double`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-151">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="6feb4-152">Debe usar una conversión explícita para convertir un tipo de punto flotante en otro tipo de punto flotante cuando no se define una conversión implícita del tipo de origen en el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="6feb4-152">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="6feb4-153">Esto se denomina *conversión de restricción*.</span><span class="sxs-lookup"><span data-stu-id="6feb4-153">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="6feb4-154">El caso explícito es necesario porque la conversión puede producir pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="6feb4-154">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="6feb4-155">No hay ninguna conversión implícita entre otros tipos de punto flotante y el tipo `decimal` puesto que el tipo `decimal` tiene mayor precisión que `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="6feb4-155">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="6feb4-156">Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="6feb4-156">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="6feb4-157">Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="6feb4-157">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6feb4-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="6feb4-158">See also</span></span>

- [<span data-ttu-id="6feb4-159">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6feb4-159">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6feb4-160">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="6feb4-160">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="6feb4-161">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="6feb4-161">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="6feb4-162">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="6feb4-162">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="6feb4-163">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="6feb4-163">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="6feb4-164">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="6feb4-164">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="6feb4-165">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="6feb4-165">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="6feb4-166">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="6feb4-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="6feb4-167">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="6feb4-167">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
