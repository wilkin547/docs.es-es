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
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664195"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="e901d-103">Tipos numéricos de punto flotante (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e901d-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="e901d-104">Los **tipos de punto flotante** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#floating-point-literals).</span><span class="sxs-lookup"><span data-stu-id="e901d-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="e901d-105">Todos los tipos de punto flotante también son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="e901d-105">All floating-point types are also value types.</span></span> <span data-ttu-id="e901d-106">Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md) [de comparación e igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e901d-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="e901d-107">La siguiente tabla muestra la precisión y el intervalo aproximado para los tipos de punto flotante:</span><span class="sxs-lookup"><span data-stu-id="e901d-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="e901d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="e901d-108">Type</span></span>|<span data-ttu-id="e901d-109">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="e901d-109">Approximate range</span></span>|<span data-ttu-id="e901d-110">Precisión</span><span class="sxs-lookup"><span data-stu-id="e901d-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="e901d-111">De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="e901d-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="e901d-112">De 6 a 9 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="e901d-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="e901d-113">De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="e901d-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="e901d-114">De 15 a 17 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="e901d-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="e901d-115">De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="e901d-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="e901d-116">28-29 dígitos</span><span class="sxs-lookup"><span data-stu-id="e901d-116">28-29 digits</span></span>|  

<span data-ttu-id="e901d-117">El valor predeterminado para todos los tipos de punto flotante es `0`.</span><span class="sxs-lookup"><span data-stu-id="e901d-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="e901d-118">Cada uno de los tipos de punto flotante tiene constantes denominadas `MinValue` y `MaxValue` para el valor mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="e901d-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="e901d-119">Los tipos `float` y `double` tienen constantes adicionales para `PositiveInfinity`, `NegativeInfinity` y `NaN` (para "No es un número").</span><span class="sxs-lookup"><span data-stu-id="e901d-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="e901d-120">El tipo `decimal` incluye las constantes para `Zero`, `One` y `MinusOne`.</span><span class="sxs-lookup"><span data-stu-id="e901d-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="e901d-121">El tipo `decimal` tiene una mayor precisión y un intervalo más reducido a `float` y `double`, lo que lo hace adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="e901d-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="e901d-122">Puede combinar tipos enteros y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e901d-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="e901d-123">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e901d-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="e901d-124">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e901d-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="e901d-125">Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="e901d-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="e901d-126">Si no hay ningún tipo `double` en la expresión, esta se evalúa como `float` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="e901d-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="e901d-127">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="e901d-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="e901d-128">Cero positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="e901d-128">Positive and negative zero</span></span>
- <span data-ttu-id="e901d-129">Infinito positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="e901d-129">Positive and negative infinity</span></span>
- <span data-ttu-id="e901d-130">Valor no numérico (NaN)</span><span class="sxs-lookup"><span data-stu-id="e901d-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="e901d-131">El conjunto finito de valores distintos de cero</span><span class="sxs-lookup"><span data-stu-id="e901d-131">The finite set of nonzero values</span></span>

<span data-ttu-id="e901d-132">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="e901d-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="e901d-133">Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="e901d-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="e901d-134">Literales de punto flotante</span><span class="sxs-lookup"><span data-stu-id="e901d-134">Floating-point literals</span></span>

<span data-ttu-id="e901d-135">De forma predeterminada, un literal numérico de punto flotante a la derecha del operador de asignación se trata como `double`.</span><span class="sxs-lookup"><span data-stu-id="e901d-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="e901d-136">Puede usar sufijos para convertir un literal de punto flotante o entero a un tipo específico:</span><span class="sxs-lookup"><span data-stu-id="e901d-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="e901d-137">El sufijo `d` o `D` convierte un literal en `double`.</span><span class="sxs-lookup"><span data-stu-id="e901d-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="e901d-138">El sufijo `f` o `F` convierte un literal en `float`.</span><span class="sxs-lookup"><span data-stu-id="e901d-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="e901d-139">El sufijo `m` o `M` convierte un literal en `decimal`.</span><span class="sxs-lookup"><span data-stu-id="e901d-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="e901d-140">En los siguientes ejemplos se muestra cada sufijo:</span><span class="sxs-lookup"><span data-stu-id="e901d-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="e901d-141">Conversiones</span><span class="sxs-lookup"><span data-stu-id="e901d-141">Conversions</span></span>

<span data-ttu-id="e901d-142">Hay una conversión implícita (llamada *conversión de ampliación*) desde `float` a `double` porque el intervalo de valores `float` es un subconjunto apropiado de `double` y no hay ninguna pérdida de precisión de `float` a `double`.</span><span class="sxs-lookup"><span data-stu-id="e901d-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="e901d-143">Debe usar una conversión explícita para convertir un tipo de punto flotante en otro tipo de punto flotante cuando no se define una conversión implícita del tipo de origen en el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e901d-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="e901d-144">Esto se denomina *conversión de restricción*.</span><span class="sxs-lookup"><span data-stu-id="e901d-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="e901d-145">El caso explícito es necesario porque la conversión puede producir pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="e901d-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="e901d-146">No hay ninguna conversión implícita entre otros tipos de punto flotante y el tipo `decimal` puesto que el tipo `decimal` tiene mayor precisión que `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="e901d-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="e901d-147">Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="e901d-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="e901d-148">Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="e901d-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e901d-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="e901d-149">See also</span></span>

- [<span data-ttu-id="e901d-150">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e901d-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e901d-151">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="e901d-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="e901d-152">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="e901d-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="e901d-153">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="e901d-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="e901d-154">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="e901d-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="e901d-155">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="e901d-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="e901d-156">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="e901d-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="e901d-157">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="e901d-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="e901d-158">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="e901d-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="e901d-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="e901d-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
