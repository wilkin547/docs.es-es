---
title: '* operador: Referencia de C#'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333738"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="baa2d-102">Operador \* (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="baa2d-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="baa2d-103">El operador de multiplicación (`*`) calcula el producto de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="baa2d-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="baa2d-104">Todos los tipos numéricos tienen operadores de multiplicación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="baa2d-104">All numeric types have predefined multiplication operators.</span></span>

<span data-ttu-id="baa2d-105">`*` también ejerce de operador de desreferencia, que permite leer y escribir en un puntero.</span><span class="sxs-lookup"><span data-stu-id="baa2d-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>

## <a name="remarks"></a><span data-ttu-id="baa2d-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="baa2d-106">Remarks</span></span>

<span data-ttu-id="baa2d-107">El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros.</span><span class="sxs-lookup"><span data-stu-id="baa2d-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="baa2d-108">Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="baa2d-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../keywords/unsafe.md) keyword, and requiring the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="baa2d-109">El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="baa2d-109">The dereference operator is also known as the indirection operator.</span></span>

<span data-ttu-id="baa2d-110">Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="baa2d-110">User-defined types can overload the binary `*` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="baa2d-111">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="baa2d-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="baa2d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baa2d-112">Example</span></span>

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a><span data-ttu-id="baa2d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baa2d-113">Example</span></span>

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a><span data-ttu-id="baa2d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="baa2d-114">See also</span></span>

- [<span data-ttu-id="baa2d-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="baa2d-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="baa2d-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="baa2d-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="baa2d-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="baa2d-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="baa2d-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="baa2d-118">C# Operators</span></span>](index.md)