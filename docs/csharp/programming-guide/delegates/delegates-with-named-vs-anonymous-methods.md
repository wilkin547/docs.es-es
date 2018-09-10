---
title: Delegados con métodos con nombre y Métodos anónimos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 6d7dcb3c7c6fa8f1d55237504c23cf468aa0e79d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194223"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="efd1b-102">Delegados con métodos con nombre y Métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="efd1b-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="efd1b-103">Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede asociarse con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="efd1b-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="efd1b-104">Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="efd1b-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 <span data-ttu-id="efd1b-105">Esto se llama con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="efd1b-105">This is called using a named method.</span></span> <span data-ttu-id="efd1b-106">Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../../csharp/language-reference/keywords/static.md) o un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="efd1b-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="efd1b-107">Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="efd1b-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="efd1b-108">En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame.</span><span class="sxs-lookup"><span data-stu-id="efd1b-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="efd1b-109">El bloque puede contener una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="efd1b-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="efd1b-110">Para obtener más información, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="efd1b-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efd1b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efd1b-111">Remarks</span></span>  
 <span data-ttu-id="efd1b-112">El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.</span><span class="sxs-lookup"><span data-stu-id="efd1b-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="efd1b-113">Una instancia de delegado puede encapsular un método de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="efd1b-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="efd1b-114">Aunque el delegado puede usar un parámetro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.</span><span class="sxs-lookup"><span data-stu-id="efd1b-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="efd1b-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="efd1b-115">Example 1</span></span>  
 <span data-ttu-id="efd1b-116">A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado.</span><span class="sxs-lookup"><span data-stu-id="efd1b-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="efd1b-117">Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma</span><span class="sxs-lookup"><span data-stu-id="efd1b-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="efd1b-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="efd1b-118">Example 2</span></span>  
 <span data-ttu-id="efd1b-119">En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.</span><span class="sxs-lookup"><span data-stu-id="efd1b-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="efd1b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="efd1b-120">See Also</span></span>

- [<span data-ttu-id="efd1b-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="efd1b-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="efd1b-122">Delegados</span><span class="sxs-lookup"><span data-stu-id="efd1b-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="efd1b-123">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="efd1b-123">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [<span data-ttu-id="efd1b-124">Cómo: Combinar delegados (delegados de multidifusión)</span><span class="sxs-lookup"><span data-stu-id="efd1b-124">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
- [<span data-ttu-id="efd1b-125">Eventos</span><span class="sxs-lookup"><span data-stu-id="efd1b-125">Events</span></span>](../../../csharp/programming-guide/events/index.md)
