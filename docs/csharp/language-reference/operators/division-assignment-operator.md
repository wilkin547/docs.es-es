---
title: /= (operador) (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="b61ad-102">/= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b61ad-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="b61ad-103">Operador de asignación y división.</span><span class="sxs-lookup"><span data-stu-id="b61ad-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b61ad-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b61ad-104">Remarks</span></span>  
 <span data-ttu-id="b61ad-105">Una expresión que use el operador de asignación `/=`, como</span><span class="sxs-lookup"><span data-stu-id="b61ad-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="b61ad-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="b61ad-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="b61ad-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="b61ad-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b61ad-108">El [operador /](../../../csharp/language-reference/operators/division-operator.md) está predefinido en tipos numéricos para realizar la división.</span><span class="sxs-lookup"><span data-stu-id="b61ad-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="b61ad-109">El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador /](../../../csharp/language-reference/operators/division-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md) [Operador]).</span><span class="sxs-lookup"><span data-stu-id="b61ad-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b61ad-110">En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.</span><span class="sxs-lookup"><span data-stu-id="b61ad-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b61ad-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b61ad-111">Example</span></span>  
 <span data-ttu-id="b61ad-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b61ad-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61ad-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b61ad-113">See Also</span></span>  
 <span data-ttu-id="b61ad-114">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b61ad-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b61ad-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b61ad-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b61ad-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b61ad-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

