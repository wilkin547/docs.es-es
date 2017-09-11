---
title: "Pasar parámetros (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
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
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="40e91-102">Pasar parámetros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="40e91-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="40e91-103">En C#, los argumentos se pueden pasar a parámetros por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="40e91-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="40e91-104">El paso de parámetros por referencia permite a los miembros de funciones, métodos, propiedades, indexadores, operadores y constructores cambiar el valor de los parámetros y hacer que ese cambio persista en el entorno de la llamada.</span><span class="sxs-lookup"><span data-stu-id="40e91-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="40e91-105">Para pasar un parámetro por referencia, use una de las palabras clave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="40e91-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="40e91-106">En los ejemplos de este tema, para simplificar, solo se usa la palabra clave `ref`.</span><span class="sxs-lookup"><span data-stu-id="40e91-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="40e91-107">Para obtener más información sobre la diferencia entre `ref` y `out`, vea [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) y [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="40e91-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="40e91-108">En el ejemplo siguiente se muestra la diferencia entre los parámetros de valor y de referencia.</span><span class="sxs-lookup"><span data-stu-id="40e91-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 <span data-ttu-id="40e91-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="40e91-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="40e91-110">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="40e91-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="40e91-111">Pasar parámetros de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="40e91-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="40e91-112">Pasar parámetros Reference-Type</span><span class="sxs-lookup"><span data-stu-id="40e91-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="40e91-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="40e91-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="40e91-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="40e91-114">See Also</span></span>  
 <span data-ttu-id="40e91-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="40e91-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="40e91-116">Métodos</span><span class="sxs-lookup"><span data-stu-id="40e91-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

