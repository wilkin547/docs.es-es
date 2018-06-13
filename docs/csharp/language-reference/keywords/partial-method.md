---
title: Método parcial (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 29b5d442a1aa33babc24aee987e749c93a5ec727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269046"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="d381d-102">Método parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d381d-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="d381d-103">Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="d381d-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="d381d-104">Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no.</span><span class="sxs-lookup"><span data-stu-id="d381d-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="d381d-105">Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d381d-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="d381d-106">Se aplican las siguientes condiciones a los métodos parciales:</span><span class="sxs-lookup"><span data-stu-id="d381d-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="d381d-107">Las signaturas de ambas partes del tipo parcial deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="d381d-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="d381d-108">El método debe devolver el valor void.</span><span class="sxs-lookup"><span data-stu-id="d381d-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="d381d-109">No se permiten modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="d381d-109">No access modifiers are allowed.</span></span> <span data-ttu-id="d381d-110">Los métodos parciales son privados implícitamente.</span><span class="sxs-lookup"><span data-stu-id="d381d-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="d381d-111">En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:</span><span class="sxs-lookup"><span data-stu-id="d381d-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="d381d-112">Para obtener más información, consulte [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d381d-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d381d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d381d-113">See Also</span></span>  
 [<span data-ttu-id="d381d-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d381d-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d381d-115">partial (Tipos)</span><span class="sxs-lookup"><span data-stu-id="d381d-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
