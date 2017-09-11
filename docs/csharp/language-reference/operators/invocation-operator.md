---
title: () (operador) (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="4f3ec-102">() (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4f3ec-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="4f3ec-103">Además de usarse para especificar el orden de las operaciones de una expresión, los paréntesis se usan para llevar a cabo las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f3ec-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="4f3ec-104">Especificar conversiones o conversiones de tipo.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-104">Specify casts, or type conversions.</span></span>  
  
     <span data-ttu-id="4f3ec-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4f3ec-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span></span>  
  
2.  <span data-ttu-id="4f3ec-106">Invocar métodos o delegados.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-106">Invoke methods or delegates.</span></span>  
  
     <span data-ttu-id="4f3ec-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4f3ec-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f3ec-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f3ec-108">Remarks</span></span>  
 <span data-ttu-id="4f3ec-109">Una conversión invoca explícitamente el operador de conversión de un tipo a otro; si no se define ningún operador de conversión, se produce un error en la conversión.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-109">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="4f3ec-110">Para definir un operador de conversión, vea [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="4f3ec-110">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="4f3ec-111">El operador `()` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-111">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="4f3ec-112">Para obtener más información, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="4f3ec-112">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="4f3ec-113">Una expresión de conversión podría implicar una sintaxis ambigua.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-113">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="4f3ec-114">Por ejemplo, la expresión `(x)–y` se podría interpretar como una expresión de conversión (una conversión de –y al tipo x) o como una expresión de suma combinada con una expresión entre paréntesis, que calcula el valor x – y.</span><span class="sxs-lookup"><span data-stu-id="4f3ec-114">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="4f3ec-115">Para obtener más información sobre la invocación de métodos, vea [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="4f3ec-115">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4f3ec-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4f3ec-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f3ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f3ec-117">See Also</span></span>  
 <span data-ttu-id="4f3ec-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f3ec-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4f3ec-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f3ec-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4f3ec-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4f3ec-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

