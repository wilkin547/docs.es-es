---
title: "Control de excepciones (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
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
ms.openlocfilehash: ab03e00a6b62d0c737c90fdb489be2a78f7ab6af
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="ca6e9-102">Control de excepciones (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ca6e9-102">Exception Handling (C# Programming Guide)</span></span>
<span data-ttu-id="ca6e9-103">Los programadores de C# usan un bloque [try](../../../csharp/language-reference/keywords/try-catch.md) para separar el código que podría verse afectado por una excepción.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-103">A [try](../../../csharp/language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="ca6e9-104">Los bloques [catch](../../../csharp/language-reference/keywords/try-catch.md) asociados se usan para controlar las excepciones resultantes.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-104">Associated [catch](../../../csharp/language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="ca6e9-105">Los bloques [finally](../../../csharp/language-reference/keywords/try-finally.md) contienen código que se ejecuta independientemente de si se produce una excepción en el bloque `try`, como la liberación de recursos asignados en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-105">A [finally](../../../csharp/language-reference/keywords/try-finally.md) block contains code that is run regardless of whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="ca6e9-106">Los bloques `try` requieren uno o varios bloques `catch` asociados, un bloque `finally` o ambos.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-106">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>  
  
 <span data-ttu-id="ca6e9-107">En los ejemplos siguientes se muestra una instrucción `try-catch`, una instrucción `try-finally` y una instrucción `try-catch-finally`.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-107">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>  
  
 <span data-ttu-id="ca6e9-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span></span>  
  
 <span data-ttu-id="ca6e9-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span></span>  
  
 <span data-ttu-id="ca6e9-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span></span>  
  
 <span data-ttu-id="ca6e9-111">Un bloque `try` sin un bloque `catch` o `finally` produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-111">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>  
  
## <a name="catch-blocks"></a><span data-ttu-id="ca6e9-112">Bloques catch</span><span class="sxs-lookup"><span data-stu-id="ca6e9-112">Catch Blocks</span></span>  
 <span data-ttu-id="ca6e9-113">Los bloques `catch` pueden especificar el tipo de excepción que quiere detectar.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-113">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="ca6e9-114">La especificación de tipo se denomina *filtro de excepciones*.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-114">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="ca6e9-115">El tipo de excepción se debe derivar de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-115">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="ca6e9-116">En general, no especifique <xref:System.Exception> como el filtro de excepciones a menos que sepa cómo controlar todas las excepciones que puedan producirse en el bloque `try` o que haya incluido una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) al final del bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-116">In general, do not specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you have included a [throw](../../../csharp/language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>  
  
 <span data-ttu-id="ca6e9-117">Se pueden encadenar juntos varios bloques `catch` con distintos filtros de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-117">Multiple `catch` blocks with different exception filters can be chained together.</span></span> <span data-ttu-id="ca6e9-118">Los bloques `catch` se evalúan de arriba abajo en el código, pero solo se ejecuta un bloque `catch` para cada excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-118">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="ca6e9-119">Se ejecuta el primer bloque `catch` que especifica el tipo exacto o una clase base de la excepción producida.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-119">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="ca6e9-120">Si no hay ningún bloque `catch` que especifique un filtro de excepciones coincidente, se selecciona un bloque `catch` sin filtros, si hay alguno en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-120">If no `catch` block specifies a matching exception filter, a `catch` block that does not have a filter is selected, if one is present in the statement.</span></span> <span data-ttu-id="ca6e9-121">Es importante colocar primero los bloques `catch` con los tipos de excepción más específicos (es decir, los más derivados).</span><span class="sxs-lookup"><span data-stu-id="ca6e9-121">It is important to position `catch` blocks with the most specific (that is, the most derived) exception types first.</span></span>  
  
 <span data-ttu-id="ca6e9-122">Debe detectar excepciones cuando se cumplan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="ca6e9-122">You should catch exceptions when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="ca6e9-123">Comprende bien el motivo por el que podría producirse la excepción y puede implementar una recuperación específica, por ejemplo, pedir al usuario que escriba un nuevo nombre de archivo cuando detecte un objeto <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-123">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>  
  
-   <span data-ttu-id="ca6e9-124">Puede crear y producir una nueva excepción más específica.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-124">You can create and throw a new, more specific exception.</span></span>  
  
     <span data-ttu-id="ca6e9-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span></span>  
  
-   <span data-ttu-id="ca6e9-126">Quiere controlar parcialmente una excepción antes de pasarla para su control adicional.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-126">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="ca6e9-127">En el ejemplo siguiente, se usa un bloque `catch` para agregar una entrada a un registro de errores antes de volver a producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-127">In the following example, a `catch` block is used to add an entry to an error log before re-throwing the exception.</span></span>  
  
     <span data-ttu-id="ca6e9-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span></span>  
  
## <a name="finally-blocks"></a><span data-ttu-id="ca6e9-129">Bloques Finally</span><span class="sxs-lookup"><span data-stu-id="ca6e9-129">Finally Blocks</span></span>  
 <span data-ttu-id="ca6e9-130">Los bloques `finally` permiten limpiar las acciones que se realizan en un bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-130">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="ca6e9-131">Si está presente, el bloque `finally` se ejecuta en último lugar, después del bloque `try` y de cualquier bloque `catch` coincidente.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-131">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="ca6e9-132">Los bloques `finally` siempre se ejecutan, independientemente de si se produce una excepción o si se encuentra un bloque `catch` que coincida con el tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-132">A `finally` block always runs, regardless of whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>  
  
 <span data-ttu-id="ca6e9-133">Los bloques `finally` pueden usarse para liberar recursos como secuencias de archivo, conexiones de base de datos y controladores de gráficos sin necesidad de esperar a que el recolector de elementos no utilizados en tiempo de ejecución finalice los objetos.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-133">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="ca6e9-134">Consulte [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-134">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="ca6e9-135">En el ejemplo siguiente, el bloque `finally` se usa para cerrar un archivo que se abre en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-135">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="ca6e9-136">Observe que se comprueba el estado del identificador de archivos antes de cerrar el archivo.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-136">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="ca6e9-137">Si el bloque `try` no puede abrir el archivo, el identificador de archivos sigue teniendo el valor `null` y el bloque `finally` no intenta cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-137">If the `try` block cannot open the file, the file handle still has the value `null` and the `finally` block does not try to close it.</span></span> <span data-ttu-id="ca6e9-138">Como alternativa, si el archivo se abre correctamente en el bloque `try`, el bloque `finally` cierra el archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="ca6e9-138">Alternatively, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>  
  
 <span data-ttu-id="ca6e9-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca6e9-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ca6e9-140">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ca6e9-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca6e9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca6e9-141">See Also</span></span>  
 <span data-ttu-id="ca6e9-142">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ca6e9-143">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ca6e9-144">[Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-144">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="ca6e9-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="ca6e9-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 <span data-ttu-id="ca6e9-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span><span class="sxs-lookup"><span data-stu-id="ca6e9-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span></span>  
 [<span data-ttu-id="ca6e9-148">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ca6e9-148">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

