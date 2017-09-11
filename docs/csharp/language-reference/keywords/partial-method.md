---
title: "Método parcial (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a><span data-ttu-id="5784f-102">Método parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5784f-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="5784f-103">Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="5784f-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="5784f-104">Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no.</span><span class="sxs-lookup"><span data-stu-id="5784f-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="5784f-105">Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5784f-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="5784f-106">Se aplican las siguientes condiciones a los métodos parciales:</span><span class="sxs-lookup"><span data-stu-id="5784f-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="5784f-107">Las signaturas de ambas partes del tipo parcial deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="5784f-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="5784f-108">El método debe devolver el valor void.</span><span class="sxs-lookup"><span data-stu-id="5784f-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="5784f-109">No se permiten modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="5784f-109">No access modifiers are allowed.</span></span> <span data-ttu-id="5784f-110">Los métodos parciales son privados implícitamente.</span><span class="sxs-lookup"><span data-stu-id="5784f-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="5784f-111">En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:</span><span class="sxs-lookup"><span data-stu-id="5784f-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 <span data-ttu-id="5784f-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5784f-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span></span>  
  
 <span data-ttu-id="5784f-113">Para obtener más información, consulte [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5784f-113">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5784f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5784f-114">See Also</span></span>  
 <span data-ttu-id="5784f-115">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5784f-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="5784f-116">partial (Tipos)</span><span class="sxs-lookup"><span data-stu-id="5784f-116">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

