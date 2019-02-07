---
title: '>>Operador =:Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278985"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="38e6a-102">Operador >>= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="38e6a-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="38e6a-103">Operador de asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="38e6a-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="38e6a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38e6a-104">Remarks</span></span>

<span data-ttu-id="38e6a-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="38e6a-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="38e6a-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="38e6a-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="38e6a-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="38e6a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="38e6a-108">El [operador >>](right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.</span><span class="sxs-lookup"><span data-stu-id="38e6a-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="38e6a-109">El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](right-shift-operator.md) (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="38e6a-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="38e6a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38e6a-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="38e6a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="38e6a-111">See also</span></span>

- [<span data-ttu-id="38e6a-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="38e6a-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="38e6a-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="38e6a-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="38e6a-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="38e6a-114">C# operators</span></span>](index.md)