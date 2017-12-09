---
title: explicit (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords: explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eab79d3ac48192f3c176ed44685ab58e50fc89be
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="explicit-c-reference"></a><span data-ttu-id="0edcd-102">explicit (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0edcd-102">explicit (C# Reference)</span></span>
<span data-ttu-id="0edcd-103">La palabra clave `explicit` declara un operador de conversión de tipo definido por el usuario que se debe invocar con una conversión.</span><span class="sxs-lookup"><span data-stu-id="0edcd-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="0edcd-104">Por ejemplo, este operador convierte una clase denominada Fahrenheit en una clase denominada Celsius:</span><span class="sxs-lookup"><span data-stu-id="0edcd-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="0edcd-105">Este operador de conversión se puede invocar de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0edcd-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="0edcd-106">El operador de conversión convierte un tipo de origen en un tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="0edcd-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="0edcd-107">El tipo de origen proporciona el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="0edcd-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="0edcd-108">A diferencia de la conversión implícita, los operadores de conversión explícitos deben invocarse mediante una conversión.</span><span class="sxs-lookup"><span data-stu-id="0edcd-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="0edcd-109">Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`.</span><span class="sxs-lookup"><span data-stu-id="0edcd-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="0edcd-110">Esto impide que el compilador invoque silenciosamente la operación de conversión con posibles consecuencias no deseadas.</span><span class="sxs-lookup"><span data-stu-id="0edcd-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="0edcd-111">Omitir la conversión produce el error en tiempo de compilación CS0266.</span><span class="sxs-lookup"><span data-stu-id="0edcd-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="0edcd-112">Para obtener más información, vea [Uso de operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0edcd-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0edcd-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0edcd-113">Example</span></span>  
 <span data-ttu-id="0edcd-114">En el ejemplo siguiente se proporciona una clase `Fahrenheit` y una clase `Celsius`, y cada una proporciona un operador de conversión explícita a la otra clase.</span><span class="sxs-lookup"><span data-stu-id="0edcd-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="0edcd-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0edcd-115">Example</span></span>  
 <span data-ttu-id="0edcd-116">En el ejemplo siguiente se define una struct, `Digit`, que representa un único dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="0edcd-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="0edcd-117">Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir a un `Digit`, la conversión es explícita.</span><span class="sxs-lookup"><span data-stu-id="0edcd-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0edcd-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0edcd-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0edcd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0edcd-119">See Also</span></span>  
 [<span data-ttu-id="0edcd-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0edcd-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0edcd-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0edcd-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0edcd-122">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0edcd-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0edcd-123">implicit</span><span class="sxs-lookup"><span data-stu-id="0edcd-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="0edcd-124">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0edcd-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="0edcd-125">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="0edcd-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 <span data-ttu-id="0edcd-126">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="0edcd-126">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
