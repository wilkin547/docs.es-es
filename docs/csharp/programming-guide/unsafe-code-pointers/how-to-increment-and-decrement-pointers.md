---
title: "Cómo: Aumentar y disminuir punteros (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c8efc6d0844d867ad6eebccf3bb22c03e6d5020
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="2b458-102">Cómo: Aumentar y disminuir punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2b458-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="2b458-103">Use los operadores de incremento y decremento, `++` y `--`, para cambiar la ubicación del puntero en [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) para un puntero de tipo pointer-type*.</span><span class="sxs-lookup"><span data-stu-id="2b458-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="2b458-104">Las expresiones de incremento y decremento adquieren la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b458-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="2b458-105">Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="2b458-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="2b458-106">El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type` es agregar [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) a la dirección que está en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="2b458-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="2b458-107">El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type` es restar `sizeof` (`pointer-type`) de la dirección que está en la variable del puntero.</span><span class="sxs-lookup"><span data-stu-id="2b458-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="2b458-108">No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="2b458-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b458-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b458-109">Example</span></span>  
 <span data-ttu-id="2b458-110">En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`.</span><span class="sxs-lookup"><span data-stu-id="2b458-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="2b458-111">Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="2b458-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="2b458-112">**Value:0 @ Address:12860272**</span><span class="sxs-lookup"><span data-stu-id="2b458-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="2b458-113">**Value:1 @ Address:12860276**</span><span class="sxs-lookup"><span data-stu-id="2b458-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="2b458-114">**Value:2 @ Address:12860280**</span><span class="sxs-lookup"><span data-stu-id="2b458-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="2b458-115">**Value:3 @ Address:12860284**</span><span class="sxs-lookup"><span data-stu-id="2b458-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="2b458-116">**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="2b458-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="2b458-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b458-117">See Also</span></span>  
 [<span data-ttu-id="2b458-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2b458-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2b458-119">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="2b458-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="2b458-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="2b458-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="2b458-121">Manipular punteros</span><span class="sxs-lookup"><span data-stu-id="2b458-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="2b458-122">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="2b458-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="2b458-123">Tipos</span><span class="sxs-lookup"><span data-stu-id="2b458-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="2b458-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="2b458-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="2b458-125">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2b458-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="2b458-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="2b458-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
