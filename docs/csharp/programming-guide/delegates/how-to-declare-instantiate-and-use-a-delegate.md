---
title: "Cómo: Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5a5329b9e99fcd5830a57eb8f97b4edb67ad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="a6489-102">Cómo: Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a6489-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="a6489-103">En C# 1.0 y versiones posteriores, los delegados se pueden declarar como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6489-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 <span data-ttu-id="a6489-104">C# 2.0 ofrece una forma más sencilla de escribir la declaración anterior, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6489-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 <span data-ttu-id="a6489-105">En C# 2.0 y versiones posteriores, también es posible utilizar un método anónimo para declarar e inicializar un [delegado](../../../csharp/language-reference/keywords/delegate.md), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6489-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 <span data-ttu-id="a6489-106">En C# 3.0 y versiones posteriores, también se pueden declarar los delegados y crear una instancia de ellos mediante una expresión lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6489-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 <span data-ttu-id="a6489-107">Para obtener más información, vea [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) (Expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="a6489-107">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="a6489-108">En el ejemplo siguiente se ilustra cómo declarar un delegado, crear una instancia del mismo y utilizarlo</span><span class="sxs-lookup"><span data-stu-id="a6489-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="a6489-109">La clase `BookDB` encapsula una base de datos de una librería que mantiene una base de datos de libros.</span><span class="sxs-lookup"><span data-stu-id="a6489-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="a6489-110">Expone un método `ProcessPaperbackBooks`, que busca todos los libros de bolsillo en la base de datos y llama a un delegado para cada uno.</span><span class="sxs-lookup"><span data-stu-id="a6489-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="a6489-111">El tipo `delegate` utilizado se denomina `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="a6489-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="a6489-112">La clase `Test` utiliza esta clase para imprimir los títulos y el precio medio de los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="a6489-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="a6489-113">El uso de delegados promueve una separación adecuada de la funcionalidad entre la base de datos de la librería y el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="a6489-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="a6489-114">El código de cliente no sabe cómo se almacenan los libros ni cómo el código de la biblioteca encuentra los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="a6489-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="a6489-115">El código de la librería no sabe qué procesamiento se realiza con los libros de bolsillo después de que los encuentra.</span><span class="sxs-lookup"><span data-stu-id="a6489-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6489-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6489-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a6489-117">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a6489-117">Robust Programming</span></span>  
  
-   <span data-ttu-id="a6489-118">Declaración de un delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="a6489-119">La instrucción siguiente declara un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     <span data-ttu-id="a6489-120">Cada tipo de delegado describe el número y los tipos de argumentos, y el tipo del valor devuelto de los métodos que puede encapsular.</span><span class="sxs-lookup"><span data-stu-id="a6489-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="a6489-121">Siempre que se necesite un nuevo conjunto de tipos de argumentos o de tipos de valores devueltos, se debe declarar un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="a6489-122">Creación de instancias de un delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="a6489-123">Después de haber declarado un tipo de delegado, debe crearse un objeto delegado y asociarse con un método particular.</span><span class="sxs-lookup"><span data-stu-id="a6489-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="a6489-124">En el ejemplo anterior, esto se hace pasando el método `PrintTitle` al método `ProcessPaperbackBooks` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6489-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     <span data-ttu-id="a6489-125">Esto crea un objeto delegado nuevo asociado con el método [estático](../../../csharp/language-reference/keywords/static.md) `Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="a6489-125">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="a6489-126">De forma similar, el método no estático `AddBookToTotal` del objeto `totaller` se pasa como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6489-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     <span data-ttu-id="a6489-127">En ambos casos, se pasa un nuevo objeto delegado al método `ProcessPaperbackBooks`.</span><span class="sxs-lookup"><span data-stu-id="a6489-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="a6489-128">Después de que se ha creado un delegado, el método con el que está asociado nunca cambia; los objetos delegados son inmutables.</span><span class="sxs-lookup"><span data-stu-id="a6489-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="a6489-129">Llamada a un delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="a6489-130">Después de haber creado un objeto delegado, este suele pasarse a otro código que llamará al delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="a6489-131">La llamada a un objeto delegado se realiza mediante la utilización del nombre de dicho objeto, seguido de los argumentos entre paréntesis que se deben pasar al delegado.</span><span class="sxs-lookup"><span data-stu-id="a6489-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="a6489-132">A continuación se expone un ejemplo de llamada a un delegado:</span><span class="sxs-lookup"><span data-stu-id="a6489-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     <span data-ttu-id="a6489-133">Se puede llamar a un delegado de forma sincrónica, como en este ejemplo, o bien de forma asincrónica con los métodos `BeginInvoke` y `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="a6489-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6489-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6489-134">See Also</span></span>  
 [<span data-ttu-id="a6489-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a6489-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6489-136">Eventos</span><span class="sxs-lookup"><span data-stu-id="a6489-136">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="a6489-137">Delegados</span><span class="sxs-lookup"><span data-stu-id="a6489-137">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
