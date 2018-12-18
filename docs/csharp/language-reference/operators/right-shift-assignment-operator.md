---
title: 'Operador &gt;&gt;=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: aebc92ffb007db7b4950313874ebc2bf3c40615f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239451"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="882a7-102">Operador &gt;&gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="882a7-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="882a7-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="882a7-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="882a7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="882a7-104">Remarks</span></span>  
 <span data-ttu-id="882a7-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="882a7-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="882a7-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="882a7-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="882a7-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="882a7-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="882a7-108">El [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.</span><span class="sxs-lookup"><span data-stu-id="882a7-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="882a7-109">El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="882a7-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="882a7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="882a7-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="882a7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="882a7-111">See Also</span></span>

- [<span data-ttu-id="882a7-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="882a7-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="882a7-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="882a7-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="882a7-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="882a7-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
