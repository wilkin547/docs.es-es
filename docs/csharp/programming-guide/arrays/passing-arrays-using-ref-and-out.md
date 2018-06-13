---
title: Pasar matrices mediante Ref y Out (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: a186399125e01bb2535f3a8b488c6fbd85932246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313575"
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="79506-102">Pasar matrices mediante Ref y Out (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="79506-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="79506-103">Al igual que todos los parámetros [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), un parámetro `out` de un tipo de matriz debe asignarse antes de usarse; es decir, debe asignarlo el destinatario.</span><span class="sxs-lookup"><span data-stu-id="79506-103">Like all [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="79506-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79506-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="79506-105">Al igual que todos los parámetros [ref](../../../csharp/language-reference/keywords/ref.md), un parámetro `ref` de un tipo de matriz debe asignarlo definitivamente el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="79506-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="79506-106">Por consiguiente, no es necesario que lo asigne definitivamente el destinatario.</span><span class="sxs-lookup"><span data-stu-id="79506-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="79506-107">Un parámetro `ref` de un tipo de matriz puede cambiar como resultado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="79506-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="79506-108">Por ejemplo, a la matriz se le puede asignar el valor [NULL](../../../csharp/language-reference/keywords/null.md) o se puede inicializar en otra matriz.</span><span class="sxs-lookup"><span data-stu-id="79506-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="79506-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79506-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="79506-110">En los dos ejemplos siguientes se muestra la diferencia entre `out` y `ref` cuando se usan para pasar matrices a métodos.</span><span class="sxs-lookup"><span data-stu-id="79506-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79506-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79506-111">Example</span></span>  
 <span data-ttu-id="79506-112">En este ejemplo, la matriz `theArray` se declara en el llamador (el método `Main`) y se inicializa en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="79506-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="79506-113">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="79506-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="79506-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79506-114">Example</span></span>  
 <span data-ttu-id="79506-115">En este ejemplo, la matriz `theArray` se inicializa en el llamador (el método `Main`) y se pasa al método `FillArray` mediante el parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="79506-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="79506-116">Algunos de los elementos de la matriz se actualizan en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="79506-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="79506-117">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="79506-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="79506-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="79506-118">See Also</span></span>  
 [<span data-ttu-id="79506-119">ref</span><span class="sxs-lookup"><span data-stu-id="79506-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="79506-120">Modificador del parámetro out</span><span class="sxs-lookup"><span data-stu-id="79506-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="79506-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="79506-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79506-122">Matrices</span><span class="sxs-lookup"><span data-stu-id="79506-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="79506-123">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="79506-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="79506-124">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="79506-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="79506-125">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="79506-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
