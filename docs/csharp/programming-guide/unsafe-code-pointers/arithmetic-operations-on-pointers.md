---
title: Operaciones aritméticas en punteros (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: c40b125e42649093aa1f1fe860a3e8f5d2690359
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="b4d27-102">Operaciones aritméticas en punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b4d27-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="b4d27-103">En este tema se describe el uso de los operadores aritméticos `+` y **-** para manipular punteros.</span><span class="sxs-lookup"><span data-stu-id="b4d27-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4d27-104">No se pueden realizar operaciones aritméticas en punteros void.</span><span class="sxs-lookup"><span data-stu-id="b4d27-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="b4d27-105">Suma y resta de valores numéricos a punteros</span><span class="sxs-lookup"><span data-stu-id="b4d27-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="b4d27-106">Se puede sumar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero, `p`, de cualquier tipo excepto `void*`.</span><span class="sxs-lookup"><span data-stu-id="b4d27-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="b4d27-107">El `p+n` resultante es el puntero que resulta de sumar `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="b4d27-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="b4d27-108">De forma similar, `p-n` es el puntero resultante de restar `n * sizeof(p)` de la dirección de `p`.</span><span class="sxs-lookup"><span data-stu-id="b4d27-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="b4d27-109">Restar punteros</span><span class="sxs-lookup"><span data-stu-id="b4d27-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="b4d27-110">También se pueden restar punteros del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="b4d27-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="b4d27-111">El resultado siempre es de tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="b4d27-111">The result is always of the type `long`.</span></span> <span data-ttu-id="b4d27-112">Por ejemplo, si `p1` y `p2` son punteros de tipo `pointer-type*`, la expresión `p1-p2` da como resultado:</span><span class="sxs-lookup"><span data-stu-id="b4d27-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="b4d27-113">No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b4d27-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d27-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4d27-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b4d27-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b4d27-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4d27-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4d27-116">See Also</span></span>  
 [<span data-ttu-id="b4d27-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b4d27-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b4d27-118">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="b4d27-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="b4d27-119">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="b4d27-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="b4d27-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b4d27-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="b4d27-121">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="b4d27-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="b4d27-122">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="b4d27-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="b4d27-123">Tipos</span><span class="sxs-lookup"><span data-stu-id="b4d27-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b4d27-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="b4d27-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="b4d27-125">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b4d27-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="b4d27-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b4d27-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
