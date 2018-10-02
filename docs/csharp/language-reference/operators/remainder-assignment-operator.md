---
title: '%= (operador) (Referencia de C#)'
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085652"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e5bce-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e5bce-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="e5bce-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="e5bce-103">The remainder assignment operator.</span></span>

<span data-ttu-id="e5bce-104">Una expresión que usa el operador `%=`, como</span><span class="sxs-lookup"><span data-stu-id="e5bce-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="e5bce-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="e5bce-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="e5bce-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="e5bce-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="e5bce-107">El [operador de resto](remainder-operator.md) `%` es compatible con todos los tipos numéricos y calcula el resto después de la división de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="e5bce-107">The [remainder operator](remainder-operator.md) `%` is supported by all numeric types and computes the remainder after division of its operands.</span></span>

<span data-ttu-id="e5bce-108">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de resto](remainder-operator.md) `%`, el operador de asignación de resto `%=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="e5bce-108">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="e5bce-109">En el siguiente ejemplo se muestra el uso del operador `%=`:</span><span class="sxs-lookup"><span data-stu-id="e5bce-109">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="e5bce-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5bce-110">See also</span></span>

- [<span data-ttu-id="e5bce-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e5bce-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e5bce-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e5bce-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e5bce-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e5bce-113">C# Operators</span></span>](index.md)
