---
title: Operador ^= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: b868f2cdbfa8a80f89a12e6194a30154481f0b07
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e03f4-102">Operador ^= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e03f4-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="e03f4-103">El operador de asignación de OR exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e03f4-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e03f4-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e03f4-104">Remarks</span></span>  
 <span data-ttu-id="e03f4-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="e03f4-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="e03f4-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="e03f4-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="e03f4-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="e03f4-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e03f4-108">El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="e03f4-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="e03f4-109">El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e03f4-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03f4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e03f4-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e03f4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03f4-111">See Also</span></span>  
 [<span data-ttu-id="e03f4-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e03f4-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e03f4-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e03f4-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e03f4-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e03f4-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
