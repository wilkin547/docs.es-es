---
title: 'Palabra clave decimal: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: 7ad01f9e4f5a8b1a153b1ef306e9d6168335eb3d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424304"
---
# <a name="decimal-c-reference"></a><span data-ttu-id="b2e95-102">decimal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b2e95-102">decimal (C# Reference)</span></span>

<span data-ttu-id="b2e95-103">La palabra clave `decimal` indica un tipo de datos de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="b2e95-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="b2e95-104">Comparado con otros tipos de punto flotante, el tipo `decimal` tiene una mayor precisión y un intervalo más reducido, lo que lo hace adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="b2e95-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="b2e95-105">El intervalo aproximado y la precisión para el tipo `decimal` se muestran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="b2e95-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>

|<span data-ttu-id="b2e95-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="b2e95-106">Type</span></span>|<span data-ttu-id="b2e95-107">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="b2e95-107">Approximate Range</span></span>|<span data-ttu-id="b2e95-108">Precisión</span><span class="sxs-lookup"><span data-stu-id="b2e95-108">Precision</span></span>|<span data-ttu-id="b2e95-109">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="b2e95-109">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|<span data-ttu-id="b2e95-110">De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="b2e95-110">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="b2e95-111">28-29 dígitos significativos</span><span class="sxs-lookup"><span data-stu-id="b2e95-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="b2e95-112">El valor predeterminado de un `decimal` es 0m.</span><span class="sxs-lookup"><span data-stu-id="b2e95-112">The default value of a `decimal` is 0m.</span></span>

## <a name="literals"></a><span data-ttu-id="b2e95-113">Literales</span><span class="sxs-lookup"><span data-stu-id="b2e95-113">Literals</span></span>

<span data-ttu-id="b2e95-114">Si desea que un literal real numérico se trate como `decimal`, use el sufijo m o M; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b2e95-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>

```csharp
decimal myMoney = 300.5m;
```

<span data-ttu-id="b2e95-115">Sin el sufijo m, el número se trata como [double](../../../csharp/language-reference/keywords/double.md) y genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="b2e95-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>

## <a name="conversions"></a><span data-ttu-id="b2e95-116">Conversiones</span><span class="sxs-lookup"><span data-stu-id="b2e95-116">Conversions</span></span>

<span data-ttu-id="b2e95-117">Los tipos enteros se convierten implícitamente en `decimal` y el resultado se evalúa como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b2e95-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="b2e95-118">Por consiguiente, es posible inicializar una variable decimal mediante un literal entero, sin el sufijo, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2e95-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>

```csharp
decimal myMoney = 300;
```

<span data-ttu-id="b2e95-119">No hay una conversión implícita entre otros tipos de punto flotante y el tipo `decimal`; por lo tanto, se debe usar una conversión entre ambos.</span><span class="sxs-lookup"><span data-stu-id="b2e95-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="b2e95-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b2e95-120">For example:</span></span>

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

<span data-ttu-id="b2e95-121">Asimismo, puede mezclar `decimal` y tipos enteros numéricos en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="b2e95-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="b2e95-122">En cambio, al mezclar `decimal` y otros tipos de punto flotante sin una conversión se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="b2e95-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>

<span data-ttu-id="b2e95-123">Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="b2e95-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="b2e95-124">Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="b2e95-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="formatting-decimal-output"></a><span data-ttu-id="b2e95-125">Aplicación de formato a resultados decimales</span><span class="sxs-lookup"><span data-stu-id="b2e95-125">Formatting decimal output</span></span>

<span data-ttu-id="b2e95-126">Puede aplicar formato a los resultados mediante el método `String.Format` o a través del método <xref:System.Console.Write%2A?displayProperty=nameWithType>, que llama a `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="b2e95-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="b2e95-127">El formato de divisa se especifica mediante la cadena de formato de divisa estándar "C" o "c", como se muestra en el segundo ejemplo más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b2e95-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="b2e95-128">Para obtener más información sobre el método `String.Format`, vea <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2e95-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="b2e95-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2e95-129">Example</span></span>

<span data-ttu-id="b2e95-130">En el ejemplo siguiente se genera un error del compilador al intentar agregar las variables [double](../../../csharp/language-reference/keywords/double.md) y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b2e95-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

<span data-ttu-id="b2e95-131">El resultado es el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="b2e95-131">The result is the following error:</span></span>

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

<span data-ttu-id="b2e95-132">En este ejemplo, se mezclan `decimal` e [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="b2e95-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) are mixed in the same expression.</span></span> <span data-ttu-id="b2e95-133">El resultado se evalúa como tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b2e95-133">The result evaluates to the `decimal` type.</span></span>

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a><span data-ttu-id="b2e95-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2e95-134">Example</span></span>

<span data-ttu-id="b2e95-135">En este ejemplo, se da formato a los resultados mediante la cadena de formato de divisa.</span><span class="sxs-lookup"><span data-stu-id="b2e95-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="b2e95-136">Observe que `x` se redondea, ya que las posiciones decimales superan 0,99 $.</span><span class="sxs-lookup"><span data-stu-id="b2e95-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="b2e95-137">La variable `y`, que representa el máximo de dígitos exactos, se muestra exactamente en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="b2e95-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="b2e95-138">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b2e95-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b2e95-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2e95-139">See also</span></span>

- <xref:System.Decimal>
- [<span data-ttu-id="b2e95-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b2e95-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="b2e95-141">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b2e95-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b2e95-142">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b2e95-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="b2e95-143">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="b2e95-143">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="b2e95-144">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="b2e95-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="b2e95-145">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="b2e95-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="b2e95-146">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="b2e95-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="b2e95-147">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="b2e95-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
