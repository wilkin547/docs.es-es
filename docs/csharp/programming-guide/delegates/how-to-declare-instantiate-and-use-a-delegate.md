---
title: "Cómo: Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
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
ms.openlocfilehash: 5a16fe4c627989f701ba523769cd87839d074849
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="fc8ef-102">Cómo: Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fc8ef-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="fc8ef-103">En C# 1.0 y versiones posteriores, los delegados se pueden declarar como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 <span data-ttu-id="fc8ef-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span></span>  
  
 <span data-ttu-id="fc8ef-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span></span>  
  
 <span data-ttu-id="fc8ef-106">C# 2.0 ofrece una forma más sencilla de escribir la declaración anterior, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fc8ef-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span></span>  
  
 <span data-ttu-id="fc8ef-108">En C# 2.0 y versiones posteriores, también es posible utilizar un método anónimo para declarar e inicializar un [delegado](../../../csharp/language-reference/keywords/delegate.md), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-108">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 <span data-ttu-id="fc8ef-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span></span>  
  
 <span data-ttu-id="fc8ef-110">En C# 3.0 y versiones posteriores, también se pueden declarar los delegados y crear una instancia de ellos mediante una expresión lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-110">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fc8ef-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span></span>  
  
 <span data-ttu-id="fc8ef-112">Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fc8ef-112">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="fc8ef-113">En el ejemplo siguiente se ilustra cómo declarar un delegado, crear una instancia del mismo y utilizarlo</span><span class="sxs-lookup"><span data-stu-id="fc8ef-113">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="fc8ef-114">La clase `BookDB` encapsula una base de datos de una librería que mantiene una base de datos de libros.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-114">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="fc8ef-115">Expone un método `ProcessPaperbackBooks`, que busca todos los libros de bolsillo en la base de datos y llama a un delegado para cada uno.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-115">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="fc8ef-116">El tipo `delegate` utilizado se denomina `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-116">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="fc8ef-117">La clase `Test` utiliza esta clase para imprimir los títulos y el precio medio de los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-117">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="fc8ef-118">El uso de delegados promueve una separación adecuada de la funcionalidad entre la base de datos de la librería y el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-118">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="fc8ef-119">El código de cliente no sabe cómo se almacenan los libros ni cómo el código de la biblioteca encuentra los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-119">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="fc8ef-120">El código de la librería no sabe qué procesamiento se realiza con los libros de bolsillo después de que los encuentra.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-120">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc8ef-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc8ef-121">Example</span></span>  
 <span data-ttu-id="fc8ef-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fc8ef-123">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fc8ef-123">Robust Programming</span></span>  
  
-   <span data-ttu-id="fc8ef-124">Declaración de un delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-124">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="fc8ef-125">La instrucción siguiente declara un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-125">The following statement declares a new delegate type.</span></span>  
  
     <span data-ttu-id="fc8ef-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span></span>  
  
     <span data-ttu-id="fc8ef-127">Cada tipo de delegado describe el número y los tipos de argumentos, y el tipo del valor devuelto de los métodos que puede encapsular.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-127">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="fc8ef-128">Siempre que se necesite un nuevo conjunto de tipos de argumentos o de tipos de valores devueltos, se debe declarar un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-128">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="fc8ef-129">Creación de instancias de un delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-129">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="fc8ef-130">Después de haber declarado un tipo de delegado, debe crearse un objeto delegado y asociarse con un método particular.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-130">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="fc8ef-131">En el ejemplo anterior, esto se hace pasando el método `PrintTitle` al método `ProcessPaperbackBooks` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc8ef-131">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     <span data-ttu-id="fc8ef-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span></span>  
  
     <span data-ttu-id="fc8ef-133">Esto crea un objeto delegado nuevo asociado con el método [estático](../../../csharp/language-reference/keywords/static.md) `Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-133">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="fc8ef-134">De forma similar, el método no estático `AddBookToTotal` del objeto `totaller` se pasa como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc8ef-134">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     <span data-ttu-id="fc8ef-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span></span>  
  
     <span data-ttu-id="fc8ef-136">En ambos casos, se pasa un nuevo objeto delegado al método `ProcessPaperbackBooks`.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-136">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="fc8ef-137">Después de que se ha creado un delegado, el método con el que está asociado nunca cambia; los objetos delegados son inmutables.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-137">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="fc8ef-138">Llamada a un delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-138">Calling a delegate.</span></span>  
  
     <span data-ttu-id="fc8ef-139">Después de haber creado un objeto delegado, este suele pasarse a otro código que llamará al delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-139">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="fc8ef-140">La llamada a un objeto delegado se realiza mediante la utilización del nombre de dicho objeto, seguido de los argumentos entre paréntesis que se deben pasar al delegado.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-140">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="fc8ef-141">A continuación se expone un ejemplo de llamada a un delegado:</span><span class="sxs-lookup"><span data-stu-id="fc8ef-141">Following is an example of a delegate call:</span></span>  
  
     <span data-ttu-id="fc8ef-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8ef-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span></span>  
  
     <span data-ttu-id="fc8ef-143">Se puede llamar a un delegado de forma sincrónica, como en este ejemplo, o bien de forma asincrónica con los métodos `BeginInvoke` y `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="fc8ef-143">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8ef-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc8ef-144">See Also</span></span>  
 <span data-ttu-id="fc8ef-145">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ef-145">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fc8ef-146">[Eventos](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ef-146">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="fc8ef-147">Delegados</span><span class="sxs-lookup"><span data-stu-id="fc8ef-147">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

