---
title: decimal (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
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
ms.openlocfilehash: 4c06d14f01302a21427845d0269fc8181a380914
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="decimal-c-reference"></a><span data-ttu-id="26fc2-102">decimal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="26fc2-102">decimal (C# Reference)</span></span>
<span data-ttu-id="26fc2-103">La palabra clave `decimal` indica un tipo de datos de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="26fc2-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="26fc2-104">Comparado con otros tipos de punto flotante, el tipo `decimal` tiene una mayor precisión y un intervalo más reducido, lo que lo hace adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="26fc2-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="26fc2-105">El intervalo aproximado y la precisión para el tipo `decimal` se muestran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="26fc2-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="26fc2-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="26fc2-106">Type</span></span>|<span data-ttu-id="26fc2-107">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="26fc2-107">Approximate Range</span></span>|<span data-ttu-id="26fc2-108">Precisión</span><span class="sxs-lookup"><span data-stu-id="26fc2-108">Precision</span></span>|<span data-ttu-id="26fc2-109">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="26fc2-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="26fc2-110">(-7,9 x 10<sup>28</sup> a 7,9 x 10<sup>28</sup>) / (10<sup>0</sup> a 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="26fc2-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="26fc2-111">28-29 dígitos significativos</span><span class="sxs-lookup"><span data-stu-id="26fc2-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="26fc2-112">Literales</span><span class="sxs-lookup"><span data-stu-id="26fc2-112">Literals</span></span>  
 <span data-ttu-id="26fc2-113">Si desea que un literal real numérico se trate como `decimal`, use el sufijo m o M; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26fc2-113">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="26fc2-114">Sin el sufijo m, el número se trata como [double](../../../csharp/language-reference/keywords/double.md) y genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="26fc2-114">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="26fc2-115">Conversiones</span><span class="sxs-lookup"><span data-stu-id="26fc2-115">Conversions</span></span>  
 <span data-ttu-id="26fc2-116">Los tipos enteros se convierten implícitamente en `decimal` y el resultado se evalúa como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="26fc2-116">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="26fc2-117">Por consiguiente, es posible inicializar una variable decimal mediante un literal entero, sin el sufijo, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="26fc2-117">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="26fc2-118">No hay una conversión implícita entre otros tipos de punto flotante y el tipo `decimal`; por lo tanto, se debe usar una conversión entre ambos.</span><span class="sxs-lookup"><span data-stu-id="26fc2-118">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="26fc2-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26fc2-119">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="26fc2-120">Asimismo, puede mezclar `decimal` y tipos enteros numéricos en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="26fc2-120">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="26fc2-121">En cambio, al mezclar `decimal` y otros tipos de punto flotante sin una conversión se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="26fc2-121">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="26fc2-122">Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="26fc2-122">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="26fc2-123">Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="26fc2-123">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="26fc2-124">Aplicar formato a resultados decimales</span><span class="sxs-lookup"><span data-stu-id="26fc2-124">Formatting Decimal Output</span></span>  
 <span data-ttu-id="26fc2-125">Puede aplicar formato a los resultados mediante el método `String.Format` o a través del método <xref:System.Console.Write%2A?displayProperty=fullName>, que llama a `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="26fc2-125">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> method, which calls `String.Format()`.</span></span> <span data-ttu-id="26fc2-126">El formato de divisa se especifica mediante la cadena de formato de divisa estándar "C" o "c", como se muestra en el segundo ejemplo más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-126">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="26fc2-127">Para obtener más información sobre el método `String.Format`, vea <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="26fc2-127">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26fc2-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26fc2-128">Example</span></span>  
 <span data-ttu-id="26fc2-129">En el ejemplo siguiente se genera un error del compilador al intentar agregar las variables [double](../../../csharp/language-reference/keywords/double.md) y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="26fc2-129">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="26fc2-130">El resultado es el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="26fc2-130">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="26fc2-131">En este ejemplo, se mezclan `decimal` e [int](../../../csharp/language-reference/keywords/int.md) en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="26fc2-131">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="26fc2-132">El resultado se evalúa como tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="26fc2-132">The result evaluates to the `decimal` type.</span></span>  
  
 <span data-ttu-id="26fc2-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="26fc2-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="26fc2-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26fc2-134">Example</span></span>  
 <span data-ttu-id="26fc2-135">En este ejemplo, se da formato a los resultados mediante la cadena de formato de divisa.</span><span class="sxs-lookup"><span data-stu-id="26fc2-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="26fc2-136">Observe que `x` se redondea, ya que las posiciones decimales superan 0,99 $.</span><span class="sxs-lookup"><span data-stu-id="26fc2-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="26fc2-137">La variable `y`, que representa el máximo de dígitos exactos, se muestra exactamente en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="26fc2-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 <span data-ttu-id="26fc2-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="26fc2-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="26fc2-139">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="26fc2-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26fc2-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="26fc2-140">See Also</span></span>  
 <span data-ttu-id="26fc2-141"><xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="26fc2-141"><xref:System.Decimal></span></span>   
 <span data-ttu-id="26fc2-142">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="26fc2-143">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="26fc2-144">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-144">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="26fc2-145">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-145">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="26fc2-146">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-146">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="26fc2-147">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-147">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="26fc2-148">[Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="26fc2-148">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="26fc2-149">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="26fc2-149">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)

