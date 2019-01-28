---
title: 'Métodos anónimos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
ms.openlocfilehash: ba80626a777f9f2d813694abf3deda0ef0c93606
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732527"
---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="e03bc-102">Métodos anónimos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e03bc-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="e03bc-103">En las versiones de C# anteriores a 2.0, la única manera de declarar un [delegado](../../../csharp/language-reference/keywords/delegate.md) era usar [métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e03bc-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="e03bc-104">C# 2.0 introdujo los métodos anónimos y en C# 3.0 y versiones posteriores, las expresiones lambda reemplazan a los métodos anónimos como la manera preferida de escribir código en línea.</span><span class="sxs-lookup"><span data-stu-id="e03bc-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="e03bc-105">En cambio, la información sobre los métodos anónimos de este tema también se aplica a las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="e03bc-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="e03bc-106">Existe un caso en el que un método anónimo proporciona funciones que no se encuentran en las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="e03bc-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="e03bc-107">Los métodos anónimos le permiten omitir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="e03bc-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="e03bc-108">Esto significa que un método anónimo puede convertirse en delegados con una variedad de firmas.</span><span class="sxs-lookup"><span data-stu-id="e03bc-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="e03bc-109">Esto no es posible con las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="e03bc-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="e03bc-110">Para obtener más información específica sobre las expresiones lambda, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e03bc-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="e03bc-111">Crear métodos anónimos es básicamente una manera de pasar un bloque de código como un parámetro de delegado.</span><span class="sxs-lookup"><span data-stu-id="e03bc-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="e03bc-112">Dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e03bc-112">Here are two examples:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 <span data-ttu-id="e03bc-113">Mediante los métodos anónimos, reduce la sobrecarga de codificación al crear instancias de delegados porque no tiene que crear un método independiente.</span><span class="sxs-lookup"><span data-stu-id="e03bc-113">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="e03bc-114">Por ejemplo, especificar un bloque de código en lugar de un delegado puede ser útil en una situación en la que tener que crear un método puede parecer una sobrecarga innecesaria.</span><span class="sxs-lookup"><span data-stu-id="e03bc-114">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="e03bc-115">Un buen ejemplo sería cuando inicia un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="e03bc-115">A good example would be when you start a new thread.</span></span> <span data-ttu-id="e03bc-116">Esta clase crea un subproceso y también contiene el código que el subproceso ejecuta sin crear un método adicional para el delegado.</span><span class="sxs-lookup"><span data-stu-id="e03bc-116">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="e03bc-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e03bc-117">Remarks</span></span>  
 <span data-ttu-id="e03bc-118">El ámbito de los parámetros de un método anónimo es el *bloque de método anónimo*.</span><span class="sxs-lookup"><span data-stu-id="e03bc-118">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="e03bc-119">Es un error tener una instrucción de salto, como [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), dentro del bloque de método anónimo si el destino está fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="e03bc-119">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="e03bc-120">También es un error tener una instrucción de salto, como `goto`, `break` o `continue`, fuera del bloque de método anónimo si el destino está dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="e03bc-120">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="e03bc-121">Las variables locales y los parámetros cuyo ámbito contiene una declaración de método anónimo se denominan variables *externas* del método anónimo.</span><span class="sxs-lookup"><span data-stu-id="e03bc-121">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="e03bc-122">Por ejemplo, en el siguiente segmento de código, `n` es una variable externa:</span><span class="sxs-lookup"><span data-stu-id="e03bc-122">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 <span data-ttu-id="e03bc-123">Una referencia a la variable externa `n` se dice que está *capturada* cuando se crea el delegado.</span><span class="sxs-lookup"><span data-stu-id="e03bc-123">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="e03bc-124">A diferencia de las variables locales, la duración de una variable capturada se extiende hasta que los delegados que hacen referencia a los métodos anónimos son aptos para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e03bc-124">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="e03bc-125">Un método anónimo no puede tener acceso a los parámetros [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) de un ámbito externo.</span><span class="sxs-lookup"><span data-stu-id="e03bc-125">An anonymous method cannot access the [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="e03bc-126">No se puede tener acceso a ningún código no seguro dentro del *bloque de método anónimo*.</span><span class="sxs-lookup"><span data-stu-id="e03bc-126">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="e03bc-127">Los métodos anónimos no se permiten en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="e03bc-127">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03bc-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e03bc-128">Example</span></span>  
 <span data-ttu-id="e03bc-129">En el ejemplo siguiente se muestran dos maneras de crear instancias de un delegado:</span><span class="sxs-lookup"><span data-stu-id="e03bc-129">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="e03bc-130">Asociar el delegado con un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="e03bc-130">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="e03bc-131">Asociar el delegado con un método con nombre (`DoWork`).</span><span class="sxs-lookup"><span data-stu-id="e03bc-131">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="e03bc-132">En cada caso, se muestra un mensaje cuando se invoca al delegado.</span><span class="sxs-lookup"><span data-stu-id="e03bc-132">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e03bc-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03bc-133">See also</span></span>

- [<span data-ttu-id="e03bc-134">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e03bc-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e03bc-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e03bc-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e03bc-136">Delegados</span><span class="sxs-lookup"><span data-stu-id="e03bc-136">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="e03bc-137">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e03bc-137">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="e03bc-138">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="e03bc-138">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="e03bc-139">Métodos</span><span class="sxs-lookup"><span data-stu-id="e03bc-139">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="e03bc-140">Delegados con métodos con nombre y delegados con métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="e03bc-140">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
