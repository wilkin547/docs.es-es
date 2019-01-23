---
title: 'Operador &lt;&lt;=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 4513c4b78dea3e8102c72a43249b4a44ffa2421d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333257"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="ce601-102">Operador &lt;&lt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ce601-102">&lt;&lt;= operator (C# Reference)</span></span>

<span data-ttu-id="ce601-103">Operador de asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ce601-103">The left-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce601-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce601-104">Remarks</span></span>

<span data-ttu-id="ce601-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="ce601-105">An expression of the form</span></span>

```csharp
x <<= y
```

<span data-ttu-id="ce601-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="ce601-106">is evaluated as</span></span>

```csharp
x = x << y
```

<span data-ttu-id="ce601-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="ce601-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ce601-108">El [operador <<](left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.</span><span class="sxs-lookup"><span data-stu-id="ce601-108">The [<< operator](left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>

<span data-ttu-id="ce601-109">El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](left-shift-operator.md) (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ce601-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](left-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="ce601-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce601-110">Example</span></span>

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a><span data-ttu-id="ce601-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce601-111">See also</span></span>

- [<span data-ttu-id="ce601-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ce601-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ce601-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ce601-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ce601-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ce601-114">C# Operators</span></span>](index.md)
