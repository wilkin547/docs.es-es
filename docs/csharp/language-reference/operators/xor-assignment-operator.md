---
title: 'Operador ^=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333556"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="79f06-102">Operador ^= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="79f06-102">^= operator (C# Reference)</span></span>

<span data-ttu-id="79f06-103">El operador de asignación de OR exclusiva.</span><span class="sxs-lookup"><span data-stu-id="79f06-103">The exclusive-OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="79f06-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79f06-104">Remarks</span></span>

<span data-ttu-id="79f06-105">Una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="79f06-105">An expression of the form</span></span>

```csharp
x ^= y
```

<span data-ttu-id="79f06-106">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="79f06-106">is evaluated as</span></span>

```csharp
x = x ^ y
```

<span data-ttu-id="79f06-107">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="79f06-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="79f06-108">El [operador ^](xor-operator.md) realiza una operación de OR exclusiva bit a bit en operandos integrales y una OR exclusiva lógica en operandos [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="79f06-108">The [^ operator](xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="79f06-109">El operador ^= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador ^](xor-operator.md) (vea [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="79f06-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](xor-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="79f06-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79f06-110">Example</span></span>

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a><span data-ttu-id="79f06-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="79f06-111">See also</span></span>

- [<span data-ttu-id="79f06-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="79f06-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="79f06-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="79f06-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="79f06-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="79f06-114">C# operators</span></span>](index.md)