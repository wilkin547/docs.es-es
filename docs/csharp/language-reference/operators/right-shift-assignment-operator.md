---
title: Operador &gt;&gt;= (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6bd0a61860c35a485d61585a90ba297f75d8cf1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="1f856-102">Operador &gt;&gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1f856-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="1f856-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="1f856-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f856-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f856-104">Remarks</span></span>  
 <span data-ttu-id="1f856-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="1f856-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="1f856-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="1f856-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="1f856-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="1f856-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="1f856-108">El [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.</span><span class="sxs-lookup"><span data-stu-id="1f856-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="1f856-109">El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](../../../csharp/language-reference/operators/right-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="1f856-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f856-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f856-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1f856-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f856-111">See Also</span></span>  
 [<span data-ttu-id="1f856-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1f856-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1f856-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1f856-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1f856-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="1f856-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
