---
title: "Operaciones aritméticas en punteros (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d40d44f8be590a909ff059b0fa84efb598fcf263
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="b4843-102">Operaciones aritméticas en punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b4843-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="b4843-103">En este tema se describe el uso de los operadores aritméticos `+` y **-** para manipular punteros.</span><span class="sxs-lookup"><span data-stu-id="b4843-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4843-104">No se pueden realizar operaciones aritméticas en punteros void.</span><span class="sxs-lookup"><span data-stu-id="b4843-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="b4843-105">Suma y resta de valores numéricos a punteros</span><span class="sxs-lookup"><span data-stu-id="b4843-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="b4843-106">Se puede sumar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero, `p`, de cualquier tipo excepto `void*`.</span><span class="sxs-lookup"><span data-stu-id="b4843-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="b4843-107">El `p+n` resultante es el puntero que resulta de sumar `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="b4843-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="b4843-108">De forma similar, `p-n` es el puntero resultante de restar `n * sizeof(p)` de la dirección de `p`.</span><span class="sxs-lookup"><span data-stu-id="b4843-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="b4843-109">Restar punteros</span><span class="sxs-lookup"><span data-stu-id="b4843-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="b4843-110">También se pueden restar punteros del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="b4843-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="b4843-111">El resultado siempre es de tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="b4843-111">The result is always of the type `long`.</span></span> <span data-ttu-id="b4843-112">Por ejemplo, si `p1` y `p2` son punteros de tipo `pointer-type*`, la expresión `p1-p2` da como resultado:</span><span class="sxs-lookup"><span data-stu-id="b4843-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="b4843-113">No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b4843-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4843-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4843-114">Example</span></span>  
 <span data-ttu-id="b4843-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4843-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="b4843-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b4843-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b4843-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b4843-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4843-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4843-118">See Also</span></span>  
 <span data-ttu-id="b4843-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b4843-120">[Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-120">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="b4843-121">[Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="b4843-122">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="b4843-123">[Manipulación de punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="b4843-124">[Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="b4843-125">[Tipos](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="b4843-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="b4843-127">[fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4843-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="b4843-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b4843-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

