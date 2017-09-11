---
title: "Delegados con métodos con nombre y delegados con métodos anónimos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
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
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="8339d-102">Delegados con métodos con nombre y delegados con métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8339d-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="8339d-103">Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede asociarse con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="8339d-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="8339d-104">Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8339d-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 <span data-ttu-id="8339d-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8339d-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="8339d-106">Esto se llama con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="8339d-106">This is called using a named method.</span></span> <span data-ttu-id="8339d-107">Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../../csharp/language-reference/keywords/static.md) o un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="8339d-107">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="8339d-108">Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="8339d-108">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="8339d-109">En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame.</span><span class="sxs-lookup"><span data-stu-id="8339d-109">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="8339d-110">El bloque puede contener una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="8339d-110">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="8339d-111">Para obtener más información, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8339d-111">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8339d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8339d-112">Remarks</span></span>  
 <span data-ttu-id="8339d-113">El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.</span><span class="sxs-lookup"><span data-stu-id="8339d-113">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="8339d-114">Una instancia de delegado puede encapsular un método de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="8339d-114">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="8339d-115">Aunque el delegado puede usar un parámetro [out](../../../csharp/language-reference/keywords/out.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.</span><span class="sxs-lookup"><span data-stu-id="8339d-115">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="8339d-116">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="8339d-116">Example 1</span></span>  
 <span data-ttu-id="8339d-117">A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado.</span><span class="sxs-lookup"><span data-stu-id="8339d-117">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="8339d-118">Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma</span><span class="sxs-lookup"><span data-stu-id="8339d-118">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 <span data-ttu-id="8339d-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8339d-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="8339d-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="8339d-120">Example 2</span></span>  
 <span data-ttu-id="8339d-121">En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.</span><span class="sxs-lookup"><span data-stu-id="8339d-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 <span data-ttu-id="8339d-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8339d-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8339d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8339d-123">See Also</span></span>  
 <span data-ttu-id="8339d-124">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8339d-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8339d-125">[Delegados](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="8339d-125">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="8339d-126">[Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="8339d-126">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="8339d-127">[Cómo: Combinar delegados (delegados de multidifusión)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="8339d-127">[How to: Combine Delegates (Multicast Delegates)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span></span>  
 [<span data-ttu-id="8339d-128">Eventos</span><span class="sxs-lookup"><span data-stu-id="8339d-128">Events</span></span>](../../../csharp/programming-guide/events/index.md)

