---
title: "Cómo: Aumentar y disminuir punteros (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="14c01-102">Cómo: Aumentar y disminuir punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="14c01-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="14c01-103">Use los operadores de incremento y decremento, `++` y `--`, para cambiar la ubicación del puntero en [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) para un puntero de tipo pointer-type*.</span><span class="sxs-lookup"><span data-stu-id="14c01-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="14c01-104">Las expresiones de incremento y decremento adquieren la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="14c01-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="14c01-105">Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="14c01-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="14c01-106">El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type` es agregar [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) a la dirección que está en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="14c01-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="14c01-107">El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type` es restar `sizeof` (`pointer-type`) de la dirección que está en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="14c01-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="14c01-108">No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="14c01-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14c01-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14c01-109">Example</span></span>  
 <span data-ttu-id="14c01-110">En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`.</span><span class="sxs-lookup"><span data-stu-id="14c01-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="14c01-111">Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="14c01-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="14c01-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="14c01-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="14c01-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="14c01-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="14c01-114">**Value:0 @ Address:12860272**</span><span class="sxs-lookup"><span data-stu-id="14c01-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="14c01-115">**Value:1 @ Address:12860276**</span><span class="sxs-lookup"><span data-stu-id="14c01-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="14c01-116">**Value:2 @ Address:12860280**</span><span class="sxs-lookup"><span data-stu-id="14c01-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="14c01-117">**Value:3 @ Address:12860284**</span><span class="sxs-lookup"><span data-stu-id="14c01-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="14c01-118">**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="14c01-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="14c01-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="14c01-119">See Also</span></span>  
 <span data-ttu-id="14c01-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="14c01-121">[Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="14c01-122">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="14c01-123">[Manipulación de punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="14c01-124">[Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="14c01-125">[Tipos](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="14c01-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="14c01-127">[fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="14c01-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="14c01-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="14c01-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

