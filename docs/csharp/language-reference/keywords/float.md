---
title: float (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
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
ms.openlocfilehash: 2f1fb02f84de504112eee826dbee1275fa3ccb7a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="float-c-reference"></a><span data-ttu-id="404c8-102">float (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="404c8-102">float (C# Reference)</span></span>
<span data-ttu-id="404c8-103">La palabra clave `float` indica un tipo simple que almacena valores de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="404c8-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="404c8-104">En la tabla siguiente se muestran la precisión y el intervalo aproximado para el tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="404c8-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="404c8-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="404c8-105">Type</span></span>|<span data-ttu-id="404c8-106">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="404c8-106">Approximate range</span></span>|<span data-ttu-id="404c8-107">Precisión</span><span class="sxs-lookup"><span data-stu-id="404c8-107">Precision</span></span>|<span data-ttu-id="404c8-108">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="404c8-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="404c8-109">De -3,4 × 10<sup>38</sup>a +3,4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="404c8-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="404c8-110">7 dígitos</span><span class="sxs-lookup"><span data-stu-id="404c8-110">7 digits</span></span>|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="404c8-111">Literales</span><span class="sxs-lookup"><span data-stu-id="404c8-111">Literals</span></span>  
 <span data-ttu-id="404c8-112">De forma predeterminada, un literal numérico real a la derecha del operador de asignación se trata como [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="404c8-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="404c8-113">Por consiguiente, para inicializar una variable float, use el sufijo `f` o `F`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="404c8-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="404c8-114">Si no usa el sufijo en la declaración anterior, obtendrá un error de compilación porque intenta almacenar un valor [double](double.md) en una variable `float`.</span><span class="sxs-lookup"><span data-stu-id="404c8-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="404c8-115">Conversiones</span><span class="sxs-lookup"><span data-stu-id="404c8-115">Conversions</span></span>  
 <span data-ttu-id="404c8-116">Puede combinar tipos numéricos enteros y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="404c8-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="404c8-117">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="404c8-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="404c8-118">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="404c8-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="404c8-119">Si uno de los tipos de punto flotante es [double](double.md), la expresión se evalúa como [double](double.md) o [bool](bool.md) en expresiones relacionales o booleanas.</span><span class="sxs-lookup"><span data-stu-id="404c8-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="404c8-120">Si no hay ningún tipo [double](double.md) en la expresión, esta se evalúa como `float` o [bool](bool.md) en expresiones relacionales o booleanas.</span><span class="sxs-lookup"><span data-stu-id="404c8-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="404c8-121">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="404c8-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="404c8-122">Cero positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="404c8-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="404c8-123">Infinito positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="404c8-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="404c8-124">Valor no numérico (NaN)</span><span class="sxs-lookup"><span data-stu-id="404c8-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="404c8-125">El conjunto finito de valores distintos de cero</span><span class="sxs-lookup"><span data-stu-id="404c8-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="404c8-126">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="404c8-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="404c8-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="404c8-127">Example</span></span>  
 <span data-ttu-id="404c8-128">En el ejemplo siguiente, se incluyen un [int](int.md), un [short](short.md) y un `float` en una expresión matemática cuyo resultado es `float`.</span><span class="sxs-lookup"><span data-stu-id="404c8-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="404c8-129">(Recuerde que `float` es un alias para el tipo <xref:System.Single?displayProperty=fullName>). Observe que no hay ningún [double](double.md) en la expresión.</span><span class="sxs-lookup"><span data-stu-id="404c8-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=fullName> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 <span data-ttu-id="404c8-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="404c8-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="404c8-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="404c8-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="404c8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="404c8-132">See Also</span></span>  
 <span data-ttu-id="404c8-133"><xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="404c8-133"><xref:System.Single></span></span>   
 <span data-ttu-id="404c8-134">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="404c8-135">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="404c8-136">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="404c8-136">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="404c8-137">[Palabras clave de C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-137">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="404c8-138">[Tabla de tipos enteros](integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-138">[Integral Types Table](integral-types-table.md) </span></span>  
 <span data-ttu-id="404c8-139">[Tabla de tipos integrados](built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-139">[Built-In Types Table](built-in-types-table.md) </span></span>  
 <span data-ttu-id="404c8-140">[Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="404c8-140">[Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="404c8-141">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="404c8-141">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)

