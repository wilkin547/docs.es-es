---
title: 'Delegados con métodos con nombre y Métodos anónimos: Guía de programación de C#'
description: Aprenda sobre los delegados con nombre frente a los métodos anónimos. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 940363b87e17b34feeffaff38ed498d6fcf6850a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302755"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="d6de5-104">Delegados con métodos con nombre y Métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d6de5-104">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="d6de5-105">Un [delegado](../../language-reference/builtin-types/reference-types.md) puede asociarse con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="d6de5-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="d6de5-106">Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d6de5-106">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="d6de5-107">Esto se llama con un método con nombre.</span><span class="sxs-lookup"><span data-stu-id="d6de5-107">This is called using a named method.</span></span> <span data-ttu-id="d6de5-108">Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../language-reference/keywords/static.md) o un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="d6de5-108">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="d6de5-109">Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="d6de5-109">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="d6de5-110">En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame.</span><span class="sxs-lookup"><span data-stu-id="d6de5-110">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="d6de5-111">El bloque puede contener una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="d6de5-111">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="d6de5-112">Para obtener más información, vea [Funciones anónimas](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d6de5-112">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6de5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6de5-113">Remarks</span></span>  
 <span data-ttu-id="d6de5-114">El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.</span><span class="sxs-lookup"><span data-stu-id="d6de5-114">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="d6de5-115">Una instancia de delegado puede encapsular un método de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="d6de5-115">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="d6de5-116">Aunque el delegado puede usar un parámetro [out](../../language-reference/keywords/out-parameter-modifier.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.</span><span class="sxs-lookup"><span data-stu-id="d6de5-116">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="d6de5-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="d6de5-117">Example 1</span></span>  
 <span data-ttu-id="d6de5-118">A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado.</span><span class="sxs-lookup"><span data-stu-id="d6de5-118">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="d6de5-119">Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma</span><span class="sxs-lookup"><span data-stu-id="d6de5-119">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="d6de5-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="d6de5-120">Example 2</span></span>  
 <span data-ttu-id="d6de5-121">En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.</span><span class="sxs-lookup"><span data-stu-id="d6de5-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d6de5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6de5-122">See also</span></span>

- [<span data-ttu-id="d6de5-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d6de5-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d6de5-124">Delegados</span><span class="sxs-lookup"><span data-stu-id="d6de5-124">Delegates</span></span>](./index.md)
- [<span data-ttu-id="d6de5-125">Procedimiento para combinar delegados (delegados de multidifusión)</span><span class="sxs-lookup"><span data-stu-id="d6de5-125">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="d6de5-126">Eventos</span><span class="sxs-lookup"><span data-stu-id="d6de5-126">Events</span></span>](../events/index.md)
