---
title: 'Operador *=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333439"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4cda7-102">Operador \*= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4cda7-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="4cda7-103">El operador de asignación y multiplicación binaria.</span><span class="sxs-lookup"><span data-stu-id="4cda7-103">The binary multiplication assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cda7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4cda7-104">Remarks</span></span>

<span data-ttu-id="4cda7-105">Una expresión que use el operador de asignación `*=`, como</span><span class="sxs-lookup"><span data-stu-id="4cda7-105">An expression using the `*=` assignment operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="4cda7-106">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="4cda7-106">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="4cda7-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="4cda7-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="4cda7-108">El [operador \*](multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.</span><span class="sxs-lookup"><span data-stu-id="4cda7-108">The [\* operator](multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>

<span data-ttu-id="4cda7-109">El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador \*](multiplication-operator.md) (consulte [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="4cda7-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](multiplication-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="4cda7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cda7-110">Example</span></span>

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a><span data-ttu-id="4cda7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cda7-111">See also</span></span>

- [<span data-ttu-id="4cda7-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4cda7-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4cda7-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4cda7-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4cda7-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4cda7-114">C# Operators</span></span>](index.md)
