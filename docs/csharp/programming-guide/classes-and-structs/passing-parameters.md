---
title: "Pasar parámetros (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9e0e06d67f9da39c6b55f91e35d4a75b43353f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="dd32e-102">Pasar parámetros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dd32e-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="dd32e-103">En C#, los argumentos se pueden pasar a parámetros por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="dd32e-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="dd32e-104">El paso de parámetros por referencia permite a los miembros de funciones, métodos, propiedades, indexadores, operadores y constructores cambiar el valor de los parámetros y hacer que ese cambio persista en el entorno de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dd32e-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="dd32e-105">Para pasar un parámetro por referencia, use una de las palabras clave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="dd32e-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="dd32e-106">En los ejemplos de este tema, para simplificar, solo se usa la palabra clave `ref`.</span><span class="sxs-lookup"><span data-stu-id="dd32e-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="dd32e-107">Para obtener más información sobre la diferencia entre `ref` y `out`, vea [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) y [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="dd32e-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="dd32e-108">En el ejemplo siguiente se muestra la diferencia entre los parámetros de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="dd32e-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="dd32e-109">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd32e-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="dd32e-110">Pasar parámetros de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="dd32e-110">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="dd32e-111">Pasar parámetros Reference-Type</span><span class="sxs-lookup"><span data-stu-id="dd32e-111">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd32e-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dd32e-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd32e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd32e-113">See Also</span></span>  
 [<span data-ttu-id="dd32e-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dd32e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd32e-115">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd32e-115">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
