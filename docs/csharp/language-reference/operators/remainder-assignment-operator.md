---
title: '%= (operador) (Referencia de C#)'
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: ab3a6a8d5cbfeb4d527ca1f9c233ddfaba3d35ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188721"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cca49-102">%= (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="cca49-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="cca49-103">El operador de asignación y resto.</span><span class="sxs-lookup"><span data-stu-id="cca49-103">The remainder assignment operator.</span></span>

<span data-ttu-id="cca49-104">Una expresión que usa el operador `%=`, como</span><span class="sxs-lookup"><span data-stu-id="cca49-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="cca49-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="cca49-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="cca49-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="cca49-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="cca49-107">El [operador de resto](remainder-operator.md) `%` calcula el resto después de la división de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="cca49-107">The [remainder operator](remainder-operator.md) `%` computes the remainder after division of its operands.</span></span> <span data-ttu-id="cca49-108">Es compatible con todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="cca49-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="cca49-109">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de resto](remainder-operator.md) `%`, el operador de asignación de resto `%=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="cca49-109">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="cca49-110">En el siguiente ejemplo se muestra el uso del operador `%=`:</span><span class="sxs-lookup"><span data-stu-id="cca49-110">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="cca49-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca49-111">See also</span></span>

- [<span data-ttu-id="cca49-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cca49-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cca49-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cca49-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cca49-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="cca49-114">C# Operators</span></span>](index.md)
