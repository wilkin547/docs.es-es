---
title: explicit (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
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
ms.openlocfilehash: f11a930f0be5d504c92271b66009613de5d68579
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-c-reference"></a><span data-ttu-id="00297-102">explicit (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="00297-102">explicit (C# Reference)</span></span>
<span data-ttu-id="00297-103">La palabra clave `explicit` declara un operador de conversión de tipo definido por el usuario que se debe invocar con una conversión.</span><span class="sxs-lookup"><span data-stu-id="00297-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="00297-104">Por ejemplo, este operador convierte una clase denominada Fahrenheit en una clase denominada Celsius:</span><span class="sxs-lookup"><span data-stu-id="00297-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 <span data-ttu-id="00297-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="00297-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span></span>  
  
 <span data-ttu-id="00297-106">Este operador de conversión se puede invocar de esta forma:</span><span class="sxs-lookup"><span data-stu-id="00297-106">This conversion operator can be invoked like this:</span></span>  
  
 <span data-ttu-id="00297-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="00297-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span></span>  
  
 <span data-ttu-id="00297-108">El operador de conversión convierte un tipo de origen en un tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="00297-108">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="00297-109">El tipo de origen proporciona el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="00297-109">The source type provides the conversion operator.</span></span> <span data-ttu-id="00297-110">A diferencia de la conversión implícita, los operadores de conversión explícitos deben invocarse mediante una conversión.</span><span class="sxs-lookup"><span data-stu-id="00297-110">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="00297-111">Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`.</span><span class="sxs-lookup"><span data-stu-id="00297-111">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="00297-112">Esto impide que el compilador invoque silenciosamente la operación de conversión con posibles consecuencias no deseadas.</span><span class="sxs-lookup"><span data-stu-id="00297-112">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="00297-113">Omitir la conversión produce el error en tiempo de compilación CS0266.</span><span class="sxs-lookup"><span data-stu-id="00297-113">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="00297-114">Para obtener más información, vea [Uso de operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="00297-114">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00297-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00297-115">Example</span></span>  
 <span data-ttu-id="00297-116">En el ejemplo siguiente se proporciona una clase `Fahrenheit` y una clase `Celsius`, y cada una proporciona un operador de conversión explícita a la otra clase.</span><span class="sxs-lookup"><span data-stu-id="00297-116">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 <span data-ttu-id="00297-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="00297-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00297-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00297-118">Example</span></span>  
 <span data-ttu-id="00297-119">En el ejemplo siguiente se define una struct, `Digit`, que representa un único dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="00297-119">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="00297-120">Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir a un `Digit`, la conversión es explícita.</span><span class="sxs-lookup"><span data-stu-id="00297-120">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 <span data-ttu-id="00297-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="00297-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="00297-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00297-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00297-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="00297-123">See Also</span></span>  
 <span data-ttu-id="00297-124">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="00297-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="00297-125">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="00297-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="00297-126">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="00297-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="00297-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="00297-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="00297-128">[operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="00297-128">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="00297-129">[Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span><span class="sxs-lookup"><span data-stu-id="00297-129">[How to: Implement User-Defined Conversions Between Structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span></span>  
 <span data-ttu-id="00297-130">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="00297-130">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>

