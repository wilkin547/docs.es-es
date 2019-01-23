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
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333699"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="8a233-102">Operador &gt;&gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8a233-102">&gt;&gt;= operator (C# Reference)</span></span>

<span data-ttu-id="8a233-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8a233-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a233-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a233-104">Remarks</span></span>

<span data-ttu-id="8a233-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="8a233-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="8a233-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="8a233-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="8a233-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="8a233-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8a233-108">El [operador >>](right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.</span><span class="sxs-lookup"><span data-stu-id="8a233-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="8a233-109">El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](right-shift-operator.md) (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8a233-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="8a233-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a233-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="8a233-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a233-111">See also</span></span>

- [<span data-ttu-id="8a233-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8a233-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8a233-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8a233-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8a233-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8a233-114">C# operators</span></span>](index.md)