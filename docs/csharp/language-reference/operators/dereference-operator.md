---
title: 'Operador ->: Referencia de C#'
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: be74f02a85aa05cdab32768ed38222fc4d9289b1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255372"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="804f7-102">-> (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="804f7-102">-> Operator (C# Reference)</span></span>

<span data-ttu-id="804f7-103">El operador de acceso de miembro de puntero `->` combina el direccionamiento indirecto del puntero y el acceso del miembro.</span><span class="sxs-lookup"><span data-stu-id="804f7-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="804f7-104">Si `x` es un puntero de tipo `T*` y `y` es un miembro accesible de `T`, una expresión de formato</span><span class="sxs-lookup"><span data-stu-id="804f7-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="804f7-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="804f7-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="804f7-106">El operador `->` requiere un contexto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="804f7-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="804f7-107">Para obtener más información, vea [Cómo: Acceder a un miembro con un puntero (Guía de programación de C#)](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="804f7-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="804f7-108">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="804f7-108">Operator overloadability</span></span>

<span data-ttu-id="804f7-109">El operador `->` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="804f7-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="804f7-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="804f7-110">C# language specification</span></span>

<span data-ttu-id="804f7-111">Para más información, vea la sección [Acceso a miembros de puntero](~/_csharplang/spec/unsafe-code.md#pointer-member-access) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="804f7-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="804f7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="804f7-112">See also</span></span>

- [<span data-ttu-id="804f7-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="804f7-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="804f7-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="804f7-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="804f7-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="804f7-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="804f7-116">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="804f7-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
