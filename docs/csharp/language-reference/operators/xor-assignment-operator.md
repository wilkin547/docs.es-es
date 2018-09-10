---
title: Operador ^= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857237"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="10dbc-102">Operador ^= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="10dbc-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="10dbc-103">El operador de asignación de OR exclusiva.</span><span class="sxs-lookup"><span data-stu-id="10dbc-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10dbc-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10dbc-104">Remarks</span></span>  
 <span data-ttu-id="10dbc-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="10dbc-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="10dbc-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="10dbc-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="10dbc-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="10dbc-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="10dbc-108">El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="10dbc-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="10dbc-109">El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="10dbc-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10dbc-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10dbc-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="10dbc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="10dbc-111">See Also</span></span>

- [<span data-ttu-id="10dbc-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="10dbc-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="10dbc-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="10dbc-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="10dbc-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="10dbc-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
