---
title: "Pasar matrices mediante Ref y Out (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="dbc82-102">Pasar matrices mediante Ref y Out (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dbc82-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="dbc82-103">Al igual que todos los parámetros [out](../../../csharp/language-reference/keywords/out.md), un parámetro `out` de un tipo de matriz debe asignarse antes de usarse; es decir, debe asignarlo el destinatario.</span><span class="sxs-lookup"><span data-stu-id="dbc82-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="dbc82-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dbc82-104">For example:</span></span>  
  
 <span data-ttu-id="dbc82-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dbc82-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="dbc82-106">Al igual que todos los parámetros [ref](../../../csharp/language-reference/keywords/ref.md), un parámetro `ref` de un tipo de matriz debe asignarlo definitivamente el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbc82-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="dbc82-107">Por consiguiente, no es necesario que lo asigne definitivamente el destinatario.</span><span class="sxs-lookup"><span data-stu-id="dbc82-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="dbc82-108">Un parámetro `ref` de un tipo de matriz puede cambiar como resultado de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbc82-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="dbc82-109">Por ejemplo, a la matriz se le puede asignar el valor [NULL](../../../csharp/language-reference/keywords/null.md) o se puede inicializar en otra matriz.</span><span class="sxs-lookup"><span data-stu-id="dbc82-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="dbc82-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dbc82-110">For example:</span></span>  
  
 <span data-ttu-id="dbc82-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dbc82-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="dbc82-112">En los dos ejemplos siguientes se muestra la diferencia entre `out` y `ref` cuando se usan para pasar matrices a métodos.</span><span class="sxs-lookup"><span data-stu-id="dbc82-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbc82-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbc82-113">Example</span></span>  
 <span data-ttu-id="dbc82-114">En este ejemplo, la matriz `theArray` se declara en el llamador (el método `Main`) y se inicializa en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="dbc82-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="dbc82-115">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="dbc82-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="dbc82-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="dbc82-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbc82-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbc82-117">Example</span></span>  
 <span data-ttu-id="dbc82-118">En este ejemplo, la matriz `theArray` se inicializa en el llamador (el método `Main`) y se pasa al método `FillArray` mediante el parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="dbc82-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="dbc82-119">Algunos de los elementos de la matriz se actualizan en el método `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="dbc82-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="dbc82-120">A continuación, los elementos de la matriz se devuelven al llamador y se muestran.</span><span class="sxs-lookup"><span data-stu-id="dbc82-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="dbc82-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="dbc82-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc82-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbc82-122">See Also</span></span>  
 <span data-ttu-id="dbc82-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="dbc82-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="dbc82-124">[Modificador del parámetro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="dbc82-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="dbc82-125">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dbc82-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dbc82-126">[Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)</span><span class="sxs-lookup"><span data-stu-id="dbc82-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="dbc82-127">[Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="dbc82-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="dbc82-128">[Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="dbc82-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="dbc82-129">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="dbc82-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

