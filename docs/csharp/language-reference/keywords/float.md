---
title: Palabra clave float (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: 98f89ba3d79f7679b69ce10fd875b3caf69c5257
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668293"
---
# <a name="float-c-reference"></a><span data-ttu-id="49b9a-102">float (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="49b9a-102">float (C# Reference)</span></span>

<span data-ttu-id="49b9a-103">La palabra clave `float` indica un tipo simple que almacena valores de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="49b9a-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="49b9a-104">En la tabla siguiente se muestran la precisión y el intervalo aproximado para el tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="49b9a-104">The following table shows the precision and approximate range for the `float` type.</span></span>

|<span data-ttu-id="49b9a-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="49b9a-105">Type</span></span>|<span data-ttu-id="49b9a-106">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="49b9a-106">Approximate range</span></span>|<span data-ttu-id="49b9a-107">Precisión</span><span class="sxs-lookup"><span data-stu-id="49b9a-107">Precision</span></span>|<span data-ttu-id="49b9a-108">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="49b9a-108">.NET type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="49b9a-109">De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="49b9a-109">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="49b9a-110">7 dígitos</span><span class="sxs-lookup"><span data-stu-id="49b9a-110">7 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a><span data-ttu-id="49b9a-111">Literales</span><span class="sxs-lookup"><span data-stu-id="49b9a-111">Literals</span></span>

<span data-ttu-id="49b9a-112">De forma predeterminada, un literal numérico real a la derecha del operador de asignación se trata como [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="49b9a-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="49b9a-113">Por consiguiente, para inicializar una variable float, use el sufijo `f` o `F`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49b9a-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>

```csharp
float x = 3.5F;
```

<span data-ttu-id="49b9a-114">Si no usa el sufijo en la declaración anterior, obtendrá un error de compilación porque intenta almacenar un valor [double](double.md) en una variable `float`.</span><span class="sxs-lookup"><span data-stu-id="49b9a-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>

## <a name="conversions"></a><span data-ttu-id="49b9a-115">Conversiones</span><span class="sxs-lookup"><span data-stu-id="49b9a-115">Conversions</span></span>

<span data-ttu-id="49b9a-116">Puede combinar tipos numéricos enteros y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="49b9a-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="49b9a-117">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="49b9a-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="49b9a-118">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="49b9a-118">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="49b9a-119">Si uno de los tipos de punto flotante es [double](double.md), la expresión se evalúa como [double](double.md) o [bool](bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="49b9a-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md), or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

- <span data-ttu-id="49b9a-120">Si no hay ningún tipo [double](double.md) en la expresión, esta se evalúa como `float` o [bool](bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="49b9a-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="49b9a-121">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="49b9a-121">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="49b9a-122">Cero positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="49b9a-122">Positive and negative zero</span></span>

- <span data-ttu-id="49b9a-123">Infinito positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="49b9a-123">Positive and negative infinity</span></span>

- <span data-ttu-id="49b9a-124">Valor no numérico (NaN)</span><span class="sxs-lookup"><span data-stu-id="49b9a-124">Not-a-Number value (NaN)</span></span>

- <span data-ttu-id="49b9a-125">El conjunto finito de valores distintos de cero</span><span class="sxs-lookup"><span data-stu-id="49b9a-125">The finite set of nonzero values</span></span>

<span data-ttu-id="49b9a-126">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](http://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="49b9a-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) website.</span></span>

## <a name="example"></a><span data-ttu-id="49b9a-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49b9a-127">Example</span></span>

<span data-ttu-id="49b9a-128">En el ejemplo siguiente, se incluyen un [int](int.md), un [short](short.md) y un `float` en una expresión matemática cuyo resultado es `float`.</span><span class="sxs-lookup"><span data-stu-id="49b9a-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="49b9a-129">(Recuerde que `float` es un alias para el tipo <xref:System.Single?displayProperty=nameWithType>). Observe que no hay ningún [double](double.md) en la expresión.</span><span class="sxs-lookup"><span data-stu-id="49b9a-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="49b9a-130">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="49b9a-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="49b9a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="49b9a-131">See also</span></span>

- <xref:System.Single>  
- [<span data-ttu-id="49b9a-132">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="49b9a-132">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="49b9a-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="49b9a-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="49b9a-134">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="49b9a-134">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="49b9a-135">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="49b9a-135">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="49b9a-136">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="49b9a-136">Integral Types Table</span></span>](integral-types-table.md)  
- [<span data-ttu-id="49b9a-137">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="49b9a-137">Built-In Types Table</span></span>](built-in-types-table.md)  
- [<span data-ttu-id="49b9a-138">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="49b9a-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="49b9a-139">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="49b9a-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)  