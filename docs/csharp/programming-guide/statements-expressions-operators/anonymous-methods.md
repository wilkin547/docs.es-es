---
title: "Métodos anónimos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
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
ms.openlocfilehash: 92842becf26a15ab1a6f5e9621002abf71dc67bc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="97931-102">Métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="97931-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="97931-103">En las versiones de C# anteriores a 2.0, la única manera de declarar un [delegado](../../../csharp/language-reference/keywords/delegate.md) era usar [métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="97931-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="97931-104">C# 2.0 introdujo los métodos anónimos y en C# 3.0 y versiones posteriores, las expresiones lambda reemplazan a los métodos anónimos como la manera preferida de escribir código en línea.</span><span class="sxs-lookup"><span data-stu-id="97931-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="97931-105">En cambio, la información sobre los métodos anónimos de este tema también se aplica a las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="97931-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="97931-106">Existe un caso en el que un método anónimo proporciona funciones que no se encuentran en las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="97931-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="97931-107">Los métodos anónimos le permiten omitir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="97931-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="97931-108">Esto significa que un método anónimo puede convertirse en delegados con una variedad de firmas.</span><span class="sxs-lookup"><span data-stu-id="97931-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="97931-109">Esto no es posible con las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="97931-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="97931-110">Para obtener más información específica sobre las expresiones lambda, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="97931-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="97931-111">Crear métodos anónimos es básicamente una manera de pasar un bloque de código como un parámetro de delegado.</span><span class="sxs-lookup"><span data-stu-id="97931-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="97931-112">Dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="97931-112">Here are two examples:</span></span>  
  
 <span data-ttu-id="97931-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="97931-113">[!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="97931-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="97931-114">[!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="97931-115">Mediante los métodos anónimos, reduce la sobrecarga de codificación al crear instancias de delegados porque no tiene que crear un método independiente.</span><span class="sxs-lookup"><span data-stu-id="97931-115">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="97931-116">Por ejemplo, especificar un bloque de código en lugar de un delegado puede ser útil en una situación en la que tener que crear un método puede parecer una sobrecarga innecesaria.</span><span class="sxs-lookup"><span data-stu-id="97931-116">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="97931-117">Un buen ejemplo sería cuando inicia un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="97931-117">A good example would be when you start a new thread.</span></span> <span data-ttu-id="97931-118">Esta clase crea un subproceso y también contiene el código que el subproceso ejecuta sin crear un método adicional para el delegado.</span><span class="sxs-lookup"><span data-stu-id="97931-118">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 <span data-ttu-id="97931-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="97931-119">[!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97931-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97931-120">Remarks</span></span>  
 <span data-ttu-id="97931-121">El ámbito de los parámetros de un método anónimo es el *bloque de método anónimo*.</span><span class="sxs-lookup"><span data-stu-id="97931-121">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="97931-122">Es un error tener una instrucción de salto, como [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), dentro del bloque de método anónimo si el destino está fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="97931-122">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="97931-123">También es un error tener una instrucción de salto, como `goto`, `break` o `continue`, fuera del bloque de método anónimo si el destino está dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="97931-123">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="97931-124">Las variables locales y los parámetros cuyo ámbito contiene una declaración de método anónimo se denominan variables *externas* del método anónimo.</span><span class="sxs-lookup"><span data-stu-id="97931-124">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="97931-125">Por ejemplo, en el siguiente segmento de código, `n` es una variable externa:</span><span class="sxs-lookup"><span data-stu-id="97931-125">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 <span data-ttu-id="97931-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="97931-126">[!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="97931-127">Una referencia a la variable externa `n` se dice que está *capturada* cuando se crea el delegado.</span><span class="sxs-lookup"><span data-stu-id="97931-127">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="97931-128">A diferencia de las variables locales, la duración de una variable capturada se extiende hasta que los delegados que hacen referencia a los métodos anónimos son aptos para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="97931-128">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="97931-129">Un método anónimo no puede tener acceso a los parámetros [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md) de un ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="97931-129">An anonymous method cannot access the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="97931-130">No se puede tener acceso a ningún código no seguro dentro del *bloque de método anónimo*.</span><span class="sxs-lookup"><span data-stu-id="97931-130">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="97931-131">Los métodos anónimos no se permiten en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="97931-131">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97931-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97931-132">Example</span></span>  
 <span data-ttu-id="97931-133">En el ejemplo siguiente se muestran dos maneras de crear instancias de un delegado:</span><span class="sxs-lookup"><span data-stu-id="97931-133">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="97931-134">Asociar el delegado con un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="97931-134">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="97931-135">Asociar el delegado con un método con nombre (`DoWork`).</span><span class="sxs-lookup"><span data-stu-id="97931-135">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="97931-136">En cada caso, se muestra un mensaje cuando se invoca al delegado.</span><span class="sxs-lookup"><span data-stu-id="97931-136">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 <span data-ttu-id="97931-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="97931-137">[!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97931-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="97931-138">See Also</span></span>  
 <span data-ttu-id="97931-139">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="97931-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="97931-140">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="97931-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="97931-141">[Delegados](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="97931-141">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="97931-142">[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="97931-142">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="97931-143">[Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="97931-143">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="97931-144">[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="97931-144">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="97931-145">Delegados con métodos con nombre y delegados con métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="97931-145">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)

