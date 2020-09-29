---
title: 'Procedimiento Declarar un delegado, crear instancias del mismo y utilizarlo: Guía de programación de C#'
description: Aprenda a declarar y usar un delegado, y a crear instancias suyas. Vea ejemplos que cubren C# 1.0, 2.0 y 3.0 y versiones posteriores.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 83dbd2dc497fafaf1922f8ad53208d0ab14f14a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185904"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="6a853-104">Procedimiento Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6a853-104">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>

<span data-ttu-id="6a853-105">En C# 1.0 y versiones posteriores, los delegados se pueden declarar como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a853-105">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="6a853-106">C# 2.0 ofrece una forma más sencilla de escribir la declaración anterior, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a853-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="6a853-107">En C# 2.0 y versiones posteriores, también es posible utilizar un método anónimo para declarar e inicializar un [delegado](../../language-reference/builtin-types/reference-types.md), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a853-107">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="6a853-108">En C# 3.0 y versiones posteriores, también se pueden declarar los delegados y crear una instancia de ellos mediante una expresión lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a853-108">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="6a853-109">Para obtener más información, vea [Expresiones lambda](../../language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6a853-109">For more information, see [Lambda Expressions](../../language-reference/operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="6a853-110">En el ejemplo siguiente se ilustra cómo declarar un delegado, crear una instancia del mismo y utilizarlo</span><span class="sxs-lookup"><span data-stu-id="6a853-110">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="6a853-111">La clase `BookDB` encapsula una base de datos de una librería que mantiene una base de datos de libros.</span><span class="sxs-lookup"><span data-stu-id="6a853-111">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="6a853-112">Expone un método `ProcessPaperbackBooks`, que busca todos los libros de bolsillo en la base de datos y llama a un delegado para cada uno.</span><span class="sxs-lookup"><span data-stu-id="6a853-112">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="6a853-113">El tipo `delegate` utilizado se denomina `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="6a853-113">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="6a853-114">La clase `Test` utiliza esta clase para imprimir los títulos y el precio medio de los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="6a853-114">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="6a853-115">El uso de delegados promueve una separación adecuada de la funcionalidad entre la base de datos de la librería y el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="6a853-115">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="6a853-116">El código de cliente no sabe cómo se almacenan los libros ni cómo el código de la biblioteca encuentra los libros de bolsillo.</span><span class="sxs-lookup"><span data-stu-id="6a853-116">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="6a853-117">El código de la librería no sabe qué procesamiento se realiza con los libros de bolsillo después de que los encuentra.</span><span class="sxs-lookup"><span data-stu-id="6a853-117">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a853-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a853-118">Example</span></span>  

 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6a853-119">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6a853-119">Robust Programming</span></span>  
  
- <span data-ttu-id="6a853-120">Declaración de un delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-120">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="6a853-121">La instrucción siguiente declara un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-121">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="6a853-122">Cada tipo de delegado describe el número y los tipos de argumentos, y el tipo del valor devuelto de los métodos que puede encapsular.</span><span class="sxs-lookup"><span data-stu-id="6a853-122">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="6a853-123">Siempre que se necesite un nuevo conjunto de tipos de argumentos o de tipos de valores devueltos, se debe declarar un nuevo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-123">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="6a853-124">Creación de instancias de un delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-124">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="6a853-125">Después de haber declarado un tipo de delegado, debe crearse un objeto delegado y asociarse con un método particular.</span><span class="sxs-lookup"><span data-stu-id="6a853-125">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="6a853-126">En el ejemplo anterior, esto se hace pasando el método `PrintTitle` al método `ProcessPaperbackBooks` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a853-126">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="6a853-127">Esto crea un objeto delegado nuevo asociado con el método [estático](../../language-reference/keywords/static.md)`Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="6a853-127">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="6a853-128">De forma similar, el método no estático `AddBookToTotal` del objeto `totaller` se pasa como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a853-128">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="6a853-129">En ambos casos, se pasa un nuevo objeto delegado al método `ProcessPaperbackBooks`.</span><span class="sxs-lookup"><span data-stu-id="6a853-129">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="6a853-130">Después de que se ha creado un delegado, el método con el que está asociado nunca cambia; los objetos delegados son inmutables.</span><span class="sxs-lookup"><span data-stu-id="6a853-130">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="6a853-131">Llamada a un delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-131">Calling a delegate.</span></span>  
  
     <span data-ttu-id="6a853-132">Después de haber creado un objeto delegado, este suele pasarse a otro código que llamará al delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-132">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="6a853-133">La llamada a un objeto delegado se realiza mediante la utilización del nombre de dicho objeto, seguido de los argumentos entre paréntesis que se deben pasar al delegado.</span><span class="sxs-lookup"><span data-stu-id="6a853-133">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="6a853-134">A continuación se expone un ejemplo de llamada a un delegado:</span><span class="sxs-lookup"><span data-stu-id="6a853-134">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="6a853-135">Se puede llamar a un delegado de forma sincrónica, como en este ejemplo, o bien de forma asincrónica con los métodos `BeginInvoke` y `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="6a853-135">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a853-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a853-136">See also</span></span>

- [<span data-ttu-id="6a853-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6a853-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6a853-138">Eventos</span><span class="sxs-lookup"><span data-stu-id="6a853-138">Events</span></span>](../events/index.md)
- [<span data-ttu-id="6a853-139">Delegados</span><span class="sxs-lookup"><span data-stu-id="6a853-139">Delegates</span></span>](./index.md)
