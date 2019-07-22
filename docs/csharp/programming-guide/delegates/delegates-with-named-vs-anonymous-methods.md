---
title: 'Delegados con métodos con nombre y Métodos anónimos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 68428c097b4fc43617834c684ec6dc9705512597
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363932"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="bb0d5-102">Delegados con métodos con nombre y Métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bb0d5-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="bb0d5-103">Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede asociarse con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="bb0d5-104">Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bb0d5-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="bb0d5-105">Esto se llama con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-105">This is called using a named method.</span></span> <span data-ttu-id="bb0d5-106">Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../../csharp/language-reference/keywords/static.md) o un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="bb0d5-107">Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="bb0d5-108">En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="bb0d5-109">El bloque puede contener una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="bb0d5-110">Para obtener más información, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="bb0d5-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb0d5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb0d5-111">Remarks</span></span>  
 <span data-ttu-id="bb0d5-112">El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="bb0d5-113">Una instancia de delegado puede encapsular un método de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="bb0d5-114">Aunque el delegado puede usar un parámetro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="bb0d5-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="bb0d5-115">Example 1</span></span>  
 <span data-ttu-id="bb0d5-116">A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="bb0d5-117">Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma</span><span class="sxs-lookup"><span data-stu-id="bb0d5-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="bb0d5-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="bb0d5-118">Example 2</span></span>  
 <span data-ttu-id="bb0d5-119">En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.</span><span class="sxs-lookup"><span data-stu-id="bb0d5-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="bb0d5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb0d5-120">See also</span></span>

- [<span data-ttu-id="bb0d5-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bb0d5-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="bb0d5-122">Delegados</span><span class="sxs-lookup"><span data-stu-id="bb0d5-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="bb0d5-123">Cómo: Combinar delegados (delegados de multidifusión)</span><span class="sxs-lookup"><span data-stu-id="bb0d5-123">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="bb0d5-124">Eventos</span><span class="sxs-lookup"><span data-stu-id="bb0d5-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)
