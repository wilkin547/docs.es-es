---
title: "Delegados (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
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
ms.openlocfilehash: 1d3dc2252b086f9df9e64a059a53ec8792e11b45
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="dffad-102">Delegados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dffad-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="dffad-103">Un [delegado](../../../csharp/language-reference/keywords/delegate.md) es un tipo que representa referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="dffad-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="dffad-104">Cuando se crea una instancia de un delegado, puede asociar su instancia a cualquier método mediante una signatura compatible y un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="dffad-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="dffad-105">Puede invocar (o llamar) al método a través de la instancia del delegado.</span><span class="sxs-lookup"><span data-stu-id="dffad-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="dffad-106">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="dffad-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="dffad-107">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="dffad-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="dffad-108">Cree un método personalizado y una clase, como un control de Windows, podrá llamar al método cuando se produzca un determinado evento.</span><span class="sxs-lookup"><span data-stu-id="dffad-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="dffad-109">En el siguiente ejemplo se muestra una declaración de delegado:</span><span class="sxs-lookup"><span data-stu-id="dffad-109">The following example shows a delegate declaration:</span></span>  
  
 <span data-ttu-id="dffad-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dffad-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="dffad-111">Cualquier método de cualquier clase o struct accesible que coincida con el tipo de delegado se puede asignar al delegado.</span><span class="sxs-lookup"><span data-stu-id="dffad-111">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="dffad-112">El método puede ser estático o de instancia.</span><span class="sxs-lookup"><span data-stu-id="dffad-112">The method can be either static or an instance method.</span></span> <span data-ttu-id="dffad-113">Esto permite cambiar las llamadas a métodos mediante programación y agregar nuevo código a las clases existentes.</span><span class="sxs-lookup"><span data-stu-id="dffad-113">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dffad-114">En el contexto de la sobrecarga de métodos, la signatura de un método no incluye el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="dffad-114">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="dffad-115">Sin embargo, en el contexto de los delegados, la signatura sí lo incluye.</span><span class="sxs-lookup"><span data-stu-id="dffad-115">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="dffad-116">En otras palabras, un método debe tener el mismo tipo de valor devuelto que el delegado.</span><span class="sxs-lookup"><span data-stu-id="dffad-116">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="dffad-117">Esta capacidad de hacer referencia a un método como parámetro hace que los delegados sean idóneos para definir métodos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dffad-117">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="dffad-118">Por ejemplo, una referencia a un método que compara dos objetos podría pasarse como argumento a un algoritmo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="dffad-118">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="dffad-119">Dado que el código de comparación está en un procedimiento independiente, el algoritmo de ordenación se puede escribir de manera más general.</span><span class="sxs-lookup"><span data-stu-id="dffad-119">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="dffad-120">Información general sobre los delegados</span><span class="sxs-lookup"><span data-stu-id="dffad-120">Delegates Overview</span></span>  
 <span data-ttu-id="dffad-121">Los delegados tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="dffad-121">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="dffad-122">Los delegados son como los punteros de función de C++, pero tienen seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="dffad-122">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="dffad-123">Los delegados permiten pasar los métodos como parámetros.</span><span class="sxs-lookup"><span data-stu-id="dffad-123">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="dffad-124">Los delegados pueden usarse para definir métodos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dffad-124">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="dffad-125">Los delegados pueden encadenarse entre sí; por ejemplo, se puede llamar a varios métodos en un solo evento.</span><span class="sxs-lookup"><span data-stu-id="dffad-125">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="dffad-126">No es necesario que los métodos coincidan exactamente con el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="dffad-126">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="dffad-127">Para obtener más información, consulte [Usar varianza en delegados](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="dffad-127">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="dffad-128">La versión 2.0 de C# presentó el concepto de [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), los cuales permiten pasar bloques de código como parámetros en lugar de un método definido por separado.</span><span class="sxs-lookup"><span data-stu-id="dffad-128">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="dffad-129">En C# 3.0 se presentaron las expresiones lambda como una manera más concisa de escribir bloques de código alineado.</span><span class="sxs-lookup"><span data-stu-id="dffad-129">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="dffad-130">Tanto los métodos anónimos como las expresiones lambda (en ciertos contextos) se compilan en tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="dffad-130">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="dffad-131">Juntas, estas características se conocen ahora como funciones anónimas.</span><span class="sxs-lookup"><span data-stu-id="dffad-131">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="dffad-132">Para obtener más información sobre las expresiones lambda, consulte [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="dffad-132">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dffad-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dffad-133">In This Section</span></span>  
  
-   [<span data-ttu-id="dffad-134">Utilizar delegados</span><span class="sxs-lookup"><span data-stu-id="dffad-134">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="dffad-135">Cuándo usar delegados en lugar de interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dffad-135">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="dffad-136">Delegados con métodos con nombre y delegados con métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="dffad-136">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="dffad-137">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="dffad-137">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="dffad-138">Uso de varianza en delegados</span><span class="sxs-lookup"><span data-stu-id="dffad-138">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="dffad-139">Cómo: Combinar delegados (delegados de multidifusión)</span><span class="sxs-lookup"><span data-stu-id="dffad-139">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="dffad-140">Cómo: Declarar un delegado, crear instancias del mismo y utilizarlo</span><span class="sxs-lookup"><span data-stu-id="dffad-140">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="dffad-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dffad-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="dffad-142">Capítulos destacados del libro</span><span class="sxs-lookup"><span data-stu-id="dffad-142">Featured Book Chapters</span></span>  
 <span data-ttu-id="dffad-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="dffad-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="dffad-144">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) (Delegados, eventos y expresiones lambda) en [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="dffad-144">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffad-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="dffad-145">See Also</span></span>  
 <span data-ttu-id="dffad-146"><xref:System.Delegate></span><span class="sxs-lookup"><span data-stu-id="dffad-146"><xref:System.Delegate></span></span>   
 <span data-ttu-id="dffad-147">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dffad-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="dffad-148">Eventos</span><span class="sxs-lookup"><span data-stu-id="dffad-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)

