---
title: double (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d5588f8391157fb56a5e5067bb8e11f9269fe733
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="double-c-reference"></a><span data-ttu-id="66364-102">double (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="66364-102">double (C# Reference)</span></span>
<span data-ttu-id="66364-103">La palabra clave `double` indica un tipo simple que almacena valores de punto flotante de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="66364-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="66364-104">En la tabla siguiente se muestran la precisión y el intervalo aproximado para el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="66364-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="66364-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="66364-105">Type</span></span>|<span data-ttu-id="66364-106">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="66364-106">Approximate range</span></span>|<span data-ttu-id="66364-107">Precisión</span><span class="sxs-lookup"><span data-stu-id="66364-107">Precision</span></span>|<span data-ttu-id="66364-108">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66364-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="66364-109">De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="66364-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="66364-110">15-16 dígitos</span><span class="sxs-lookup"><span data-stu-id="66364-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="66364-111">Literales</span><span class="sxs-lookup"><span data-stu-id="66364-111">Literals</span></span>  
 <span data-ttu-id="66364-112">De forma predeterminada, un literal numérico real a la derecha del operador de asignación se trata como `double`.</span><span class="sxs-lookup"><span data-stu-id="66364-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="66364-113">Pero si quiere que un número entero se trate como `double`, use el sufijo d o D, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66364-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="66364-114">Conversiones</span><span class="sxs-lookup"><span data-stu-id="66364-114">Conversions</span></span>  
 <span data-ttu-id="66364-115">Puede combinar tipos numéricos enteros y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="66364-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="66364-116">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="66364-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="66364-117">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="66364-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="66364-118">Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double`, o [bool](../../../csharp/language-reference/keywords/bool.md) en expresiones relacionales o booleanas.</span><span class="sxs-lookup"><span data-stu-id="66364-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="66364-119">Si no hay ningún tipo `double` en la expresión se evalúa como [float](../../../csharp/language-reference/keywords/float.md), o [bool](../../../csharp/language-reference/keywords/bool.md) en expresiones relacionales o booleanas.</span><span class="sxs-lookup"><span data-stu-id="66364-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="66364-120">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="66364-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="66364-121">Cero positivo y negativo.</span><span class="sxs-lookup"><span data-stu-id="66364-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="66364-122">Infinito positivo y negativo.</span><span class="sxs-lookup"><span data-stu-id="66364-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="66364-123">Valor no numérico (NaN).</span><span class="sxs-lookup"><span data-stu-id="66364-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="66364-124">El conjunto finito de valores distintos de cero.</span><span class="sxs-lookup"><span data-stu-id="66364-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="66364-125">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="66364-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66364-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66364-126">Example</span></span>  
 <span data-ttu-id="66364-127">En el ejemplo siguiente, se agregan [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) y `double`, que dan un resultado `double`.</span><span class="sxs-lookup"><span data-stu-id="66364-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 <span data-ttu-id="66364-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="66364-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="66364-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="66364-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66364-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="66364-130">See Also</span></span>  
 <span data-ttu-id="66364-131">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="66364-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="66364-132">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66364-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="66364-133">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="66364-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="66364-134">[Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="66364-134">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="66364-135">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="66364-135">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="66364-136">[Tabla de tipos de punto flotante](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="66364-136">[Floating-Point Types Table](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span></span>  
 <span data-ttu-id="66364-137">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="66364-137">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="66364-138">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="66364-138">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

