---
title: "Pasar matrices mediante Ref y Out (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2d4e613491b26e82523d230398af3ec34b4d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="cf07c-102">Pasar matrices mediante Ref y Out (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cf07c-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="cf07c-103">Al igual que todos los parámetros [out](../../../csharp/language-reference/keywords/out.md), un parámetro `out` de un tipo de matriz debe asignarse antes de usarse; es decir, debe asignarlo el destinatario.</span><span class="sxs-lookup"><span data-stu-id="cf07c-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="cf07c-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf07c-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="cf07c-105">Al igual que todos los parámetros [ref](../../../csharp/language-reference/keywords/ref.md), un parámetro `ref` de un tipo de matriz debe asignarlo definitivamente el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf07c-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="cf07c-106">Por consiguiente, no es necesario que lo asigne definitivamente el destinatario.</span><span class="sxs-lookup"><span data-stu-id="cf07c-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="cf07c-107">Un parámetro `ref` de un tipo de matriz puede cambiar como resultado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf07c-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="cf07c-108">Por ejemplo, a la matriz se le puede asignar el valor [NULL](../../../csharp/language-reference/keywords/null.md) o se puede inicializar en otra matriz.</span><span class="sxs-lookup"><span data-stu-id="cf07c-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="cf07c-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf07c-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="cf07c-110">En los dos ejemplos siguientes se muestra la diferencia entre `out` y `ref` cuando se usan para pasar matrices a métodos.</span><span class="sxs-lookup"><span data-stu-id="cf07c-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf07c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf07c-111">Example</span></span>  
 <span data-ttu-id="cf07c-112">En este ejemplo, la matriz `theArray` se declara en el llamador (el método `Main`) y se inicializa en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="cf07c-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="cf07c-113">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="cf07c-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="cf07c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf07c-114">Example</span></span>  
 <span data-ttu-id="cf07c-115">En este ejemplo, la matriz `theArray` se inicializa en el llamador (el método `Main`) y se pasa al método `FillArray` mediante el parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="cf07c-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="cf07c-116">Algunos de los elementos de la matriz se actualizan en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="cf07c-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="cf07c-117">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="cf07c-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="cf07c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf07c-118">See Also</span></span>  
 [<span data-ttu-id="cf07c-119">ref</span><span class="sxs-lookup"><span data-stu-id="cf07c-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="cf07c-120">Modificador del parámetro out</span><span class="sxs-lookup"><span data-stu-id="cf07c-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="cf07c-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cf07c-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cf07c-122">Matrices</span><span class="sxs-lookup"><span data-stu-id="cf07c-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="cf07c-123">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="cf07c-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="cf07c-124">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="cf07c-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="cf07c-125">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="cf07c-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
