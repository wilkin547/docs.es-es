---
title: Operaciones aritméticas en punteros - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 94e5d3fbf250f8b99560f83e14c063142ac7ad29
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242105"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="61b21-102">Operaciones aritméticas en punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="61b21-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="61b21-103">En este tema se describe el uso de los operadores aritméticos `+` y `-` para manipular punteros.</span><span class="sxs-lookup"><span data-stu-id="61b21-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61b21-104">No se pueden realizar operaciones aritméticas en punteros void.</span><span class="sxs-lookup"><span data-stu-id="61b21-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="61b21-105">Suma y resta de valores numéricos en punteros</span><span class="sxs-lookup"><span data-stu-id="61b21-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="61b21-106">Se puede sumar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero.</span><span class="sxs-lookup"><span data-stu-id="61b21-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="61b21-107">Si `p` es un puntero de tipo `pointer-type*`, el resultado `p+n` es el puntero resultante de sumar `n * sizeof(pointer-type)` a la dirección de `p`.</span><span class="sxs-lookup"><span data-stu-id="61b21-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="61b21-108">De forma similar, `p-n` es el puntero resultante de restar `n * sizeof(pointer-type)` de la dirección de `p`.</span><span class="sxs-lookup"><span data-stu-id="61b21-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="61b21-109">Resta de punteros</span><span class="sxs-lookup"><span data-stu-id="61b21-109">Subtracting pointers</span></span>  
 <span data-ttu-id="61b21-110">También se pueden restar punteros del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="61b21-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="61b21-111">El resultado siempre es de tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="61b21-111">The result is always of the type `long`.</span></span> <span data-ttu-id="61b21-112">Por ejemplo, si `p1` y `p2` son punteros de tipo `pointer-type*`, la expresión `p1-p2` da como resultado:</span><span class="sxs-lookup"><span data-stu-id="61b21-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="61b21-113">No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="61b21-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61b21-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61b21-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="61b21-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="61b21-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61b21-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="61b21-116">See also</span></span>

- [<span data-ttu-id="61b21-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="61b21-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="61b21-118">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="61b21-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="61b21-119">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="61b21-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="61b21-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="61b21-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="61b21-121">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="61b21-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="61b21-122">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="61b21-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="61b21-123">Tipos</span><span class="sxs-lookup"><span data-stu-id="61b21-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="61b21-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="61b21-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="61b21-125">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="61b21-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="61b21-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="61b21-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
