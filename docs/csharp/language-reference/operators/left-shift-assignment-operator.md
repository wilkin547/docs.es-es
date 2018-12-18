---
title: 'Operador &lt;&lt;=: C# Reference'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239178"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="e5642-102">Operador &lt;&lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e5642-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="e5642-103">Operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="e5642-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5642-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5642-104">Remarks</span></span>  
 <span data-ttu-id="e5642-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="e5642-105">An expression of the form</span></span>  
  
```csharp  
x <<= y  
```  
  
 <span data-ttu-id="e5642-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="e5642-106">is evaluated as</span></span>  
  
```csharp  
x = x << y  
```  
  
 <span data-ttu-id="e5642-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="e5642-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e5642-108">El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.</span><span class="sxs-lookup"><span data-stu-id="e5642-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="e5642-109">El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e5642-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5642-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5642-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e5642-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5642-111">See Also</span></span>

- [<span data-ttu-id="e5642-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e5642-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e5642-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e5642-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e5642-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e5642-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
