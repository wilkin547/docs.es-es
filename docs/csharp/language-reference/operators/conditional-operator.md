---
title: 'Operador ?: (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9abfe4ca6be29b54edd591b503069c15e02c3532
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c895f-102">Operador ?: (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c895f-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="c895f-103">El operador condicional (`?:`) devuelve uno de dos valores según el valor de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="c895f-103">The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="c895f-104">A continuación se muestra la sintaxis del operador condicional.</span><span class="sxs-lookup"><span data-stu-id="c895f-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="c895f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c895f-105">Remarks</span></span>  
 <span data-ttu-id="c895f-106">`condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c895f-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="c895f-107">Si `condition` es `true`, `first_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="c895f-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="c895f-108">Si `condition` es `false`, `second_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="c895f-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="c895f-109">Solo se evalúa una de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="c895f-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="c895f-110">Tanto el tipo de `first_expression` como el de `second_expression` deben coincidir, o bien debe existir una conversión implícita de un tipo al otro.</span><span class="sxs-lookup"><span data-stu-id="c895f-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="c895f-111">Puede expresar cálculos que, de lo contrario, podrían requerir una construcción `if-else` más concisa mediante el operador condicional.</span><span class="sxs-lookup"><span data-stu-id="c895f-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="c895f-112">Por ejemplo, el código siguiente usa primero una instrucción `if` y después un operador condicional para clasificar un entero como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="c895f-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
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
  
 <span data-ttu-id="c895f-113">El operador condicional es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c895f-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="c895f-114">La expresión `a ? b : c ? d : e` se evalúa como `a ? b : (c ? d : e)`, no como `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="c895f-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="c895f-115">El operador condicional no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="c895f-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c895f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c895f-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c895f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c895f-117">See Also</span></span>  
 [<span data-ttu-id="c895f-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c895f-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c895f-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c895f-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c895f-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c895f-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="c895f-121">if-else</span><span class="sxs-lookup"><span data-stu-id="c895f-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 [<span data-ttu-id="c895f-122">?. ¿y? Operadores</span><span class="sxs-lookup"><span data-stu-id="c895f-122">?. and ?Operators</span></span>](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [<span data-ttu-id="c895f-123">Operador !</span><span class="sxs-lookup"><span data-stu-id="c895f-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)
