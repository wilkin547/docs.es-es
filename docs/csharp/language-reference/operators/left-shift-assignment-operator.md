---
title: Operador &lt;&lt;= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
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
ms.openlocfilehash: fd562a538891a5592cc724e74cffb3d086248898
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="bdde2-102">Operador &lt;&lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bdde2-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="bdde2-103">Operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="bdde2-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdde2-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdde2-104">Remarks</span></span>  
 <span data-ttu-id="bdde2-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="bdde2-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="bdde2-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="bdde2-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="bdde2-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="bdde2-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="bdde2-108">El [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.</span><span class="sxs-lookup"><span data-stu-id="bdde2-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="bdde2-109">El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](../../../csharp/language-reference/operators/left-shift-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bdde2-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdde2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdde2-110">Example</span></span>  
 <span data-ttu-id="bdde2-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bdde2-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdde2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdde2-112">See Also</span></span>  
 <span data-ttu-id="bdde2-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bdde2-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bdde2-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bdde2-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bdde2-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="bdde2-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

