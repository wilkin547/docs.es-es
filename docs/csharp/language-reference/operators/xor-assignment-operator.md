---
title: Operador ^= (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="0e1a2-102">Operador ^= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0e1a2-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="0e1a2-103">El operador de asignación de OR exclusiva.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e1a2-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e1a2-104">Remarks</span></span>  
 <span data-ttu-id="0e1a2-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="0e1a2-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="0e1a2-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="0e1a2-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="0e1a2-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0e1a2-108">El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="0e1a2-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="0e1a2-109">El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0e1a2-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e1a2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e1a2-110">Example</span></span>  
 <span data-ttu-id="0e1a2-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0e1a2-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1a2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e1a2-112">See Also</span></span>  
 <span data-ttu-id="0e1a2-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e1a2-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0e1a2-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e1a2-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0e1a2-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0e1a2-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

