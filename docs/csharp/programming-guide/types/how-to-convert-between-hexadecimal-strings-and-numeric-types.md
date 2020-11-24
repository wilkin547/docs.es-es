---
title: 'Procedimiento Convertir cadenas hexadecimales en tipos numéricos: Guía de programación de C#'
description: Aprenda a convertir cadenas hexadecimales en tipos numéricos. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: fc2ffd24a67f026bd0c78e7d604a0147cf57ba49
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099164"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="ba9a3-104">Procedimiento Convertir cadenas hexadecimales en tipos numéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ba9a3-104">How to convert between hexadecimal strings and numeric types (C# Programming Guide)</span></span>

<span data-ttu-id="ba9a3-105">En estos ejemplos se muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba9a3-105">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="ba9a3-106">Obtener el valor hexadecimal de cada uno de los caracteres de un elemento [string](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a3-106">Obtain the hexadecimal value of each character in a [string](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="ba9a3-107">Obtener el elemento [char](../../language-reference/builtin-types/char.md) que corresponde a cada valor de una cadena hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-107">Obtain the [char](../../language-reference/builtin-types/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="ba9a3-108">Convertir un elemento `string` hexadecimal en un elemento [int](../../language-reference/builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a3-108">Convert a hexadecimal `string` to an [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="ba9a3-109">Convertir un elemento `string` hexadecimal en un elemento [float](../../language-reference/builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a3-109">Convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="ba9a3-110">Convertir una matriz de [bytes](../../language-reference/builtin-types/integral-numeric-types.md) en un elemento `string` hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-110">Convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9a3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a3-111">Example</span></span>  

 <span data-ttu-id="ba9a3-112">En este ejemplo se genera el valor hexadecimal de cada uno de los caracteres de `string`.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-112">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="ba9a3-113">Primero, analiza `string` como una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-113">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="ba9a3-114">Después, llama a <xref:System.Convert.ToInt32%28System.Char%29> en cada carácter para obtener su valor numérico.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-114">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="ba9a3-115">Finalmente, aplica formato al número como su representación hexadecimal en un elemento `string`.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-115">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="ba9a3-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a3-116">Example</span></span>  

 <span data-ttu-id="ba9a3-117">En este ejemplo se analiza un elemento `string` de valores hexadecimales y genera el carácter correspondiente a cada valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-117">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="ba9a3-118">Primero, llama al método [Split(Char\[\])](xref:System.String.Split(System.Char[])) para obtener cada valor hexadecimal como un elemento `string` individual en una matriz.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-118">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="ba9a3-119">Después, llama a <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> para convertir el valor hexadecimal a un valor decimal representado como [int](../../language-reference/builtin-types/integral-numeric-types.md). Muestra dos maneras distintas de obtener el carácter correspondiente a ese código de carácter.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-119">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="ba9a3-120">En la primera técnica se usa <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, que devuelve el carácter correspondiente al argumento de tipo entero como `string`.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="ba9a3-121">En la segunda técnica, `int` se convierte de manera explícita en un elemento [char](../../language-reference/builtin-types/char.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a3-121">The second technique explicitly casts the `int` to a [char](../../language-reference/builtin-types/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="ba9a3-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a3-122">Example</span></span>  

 <span data-ttu-id="ba9a3-123">En este ejemplo se muestra otra manera de convertir un `string` hexadecimal en un entero mediante la llamada al método <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-123">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="ba9a3-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a3-124">Example</span></span>  

 <span data-ttu-id="ba9a3-125">En el siguiente ejemplo se muestra cómo convertir un `string` hexadecimal en un elemento [float](../../language-reference/builtin-types/floating-point-numeric-types.md) con la clase <xref:System.BitConverter?displayProperty=nameWithType> y el método <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-125">The following example shows how to convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="ba9a3-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a3-126">Example</span></span>  

 <span data-ttu-id="ba9a3-127">En el ejemplo siguiente se muestra cómo convertir una matriz [byte](../../language-reference/builtin-types/integral-numeric-types.md) en una cadena hexadecimal mediante la clase <xref:System.BitConverter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba9a3-127">The following example shows how to convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="ba9a3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba9a3-128">See also</span></span>

- [<span data-ttu-id="ba9a3-129">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="ba9a3-129">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="ba9a3-130">Tipos</span><span class="sxs-lookup"><span data-stu-id="ba9a3-130">Types</span></span>](./index.md)
- [<span data-ttu-id="ba9a3-131">Determinación de si una cadena representa un valor numérico</span><span class="sxs-lookup"><span data-stu-id="ba9a3-131">How to determine whether a string represents a numeric value</span></span>](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
