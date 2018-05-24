---
title: 'Operador ?: (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 68e7daac63a5f7d9bd1f48adfdee973bd695a13e
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fa72e-102">Operador ?: (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fa72e-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="fa72e-103">El operador condicional (`?:`), normalmente conocido como un operador condicional ternario, devuelve uno de dos valores según el valor de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="fa72e-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="fa72e-104">A continuación se muestra la sintaxis del operador condicional.</span><span class="sxs-lookup"><span data-stu-id="fa72e-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa72e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa72e-105">Remarks</span></span>  
 <span data-ttu-id="fa72e-106">`condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="fa72e-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="fa72e-107">Si `condition` es `true`, `first_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="fa72e-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="fa72e-108">Si `condition` es `false`, `second_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="fa72e-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="fa72e-109">Solo se evalúa una de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="fa72e-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="fa72e-110">Tanto el tipo de `first_expression` como el de `second_expression` deben coincidir, o bien debe existir una conversión implícita de un tipo al otro.</span><span class="sxs-lookup"><span data-stu-id="fa72e-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="fa72e-111">Puede expresar cálculos que, de lo contrario, podrían requerir una construcción `if-else` más concisa mediante el operador condicional.</span><span class="sxs-lookup"><span data-stu-id="fa72e-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="fa72e-112">Por ejemplo, el código siguiente usa primero una instrucción `if` y después un operador condicional para clasificar un entero como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="fa72e-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="fa72e-113">El operador condicional es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="fa72e-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="fa72e-114">La expresión `a ? b : c ? d : e` se evalúa como `a ? b : (c ? d : e)`, no como `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="fa72e-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="fa72e-115">El operador condicional no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="fa72e-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa72e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa72e-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fa72e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa72e-117">See Also</span></span>  
 [<span data-ttu-id="fa72e-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fa72e-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fa72e-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fa72e-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fa72e-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="fa72e-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="fa72e-121">if-else</span><span class="sxs-lookup"><span data-stu-id="fa72e-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 <span data-ttu-id="fa72e-122">[Operadores ?. y ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="fa72e-122">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
 [<span data-ttu-id="fa72e-123">Operador !</span><span class="sxs-lookup"><span data-stu-id="fa72e-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
