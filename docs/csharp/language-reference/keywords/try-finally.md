---
title: try-finally (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
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
ms.openlocfilehash: 88b9960b8c026d1fcd8eed1815ade57422cd2a15
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="try-finally-c-reference"></a><span data-ttu-id="f22bc-102">try-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f22bc-102">try-finally (C# Reference)</span></span>
<span data-ttu-id="f22bc-103">Mediante el uso de un bloque `finally`, puede limpiar todos los recursos asignados en un bloque [try](../../../csharp/language-reference/keywords/try-catch.md) y ejecutar código incluso si se produce una excepción en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="f22bc-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](../../../csharp/language-reference/keywords/try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="f22bc-104">Normalmente, las instrucciones de un bloque `finally` se ejecutan cuando el control abandona una instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="f22bc-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="f22bc-105">La transferencia de control se puede producir como resultado de la ejecución normal, de la ejecución de una instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try`.</span><span class="sxs-lookup"><span data-stu-id="f22bc-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>  
  
 <span data-ttu-id="f22bc-106">Dentro de una excepción controlada, se garantiza la ejecución del bloque `finally` asociado.</span><span class="sxs-lookup"><span data-stu-id="f22bc-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="f22bc-107">Pero en el caso de una excepción no controlada, la ejecución del bloque `finally` depende de la manera en que se desencadene la operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="f22bc-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="f22bc-108">Esto, a su vez, depende de cómo esté configurado el equipo.</span><span class="sxs-lookup"><span data-stu-id="f22bc-108">That, in turn, is dependent on how your computer is set up.</span></span> <span data-ttu-id="f22bc-109">Para obtener más información vea [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371) (Procesamiento de excepciones no controladas en CLR).</span><span class="sxs-lookup"><span data-stu-id="f22bc-109">For more information, see [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span></span>  
  
 <span data-ttu-id="f22bc-110">Normalmente, cuando una excepción no controlada finaliza una aplicación, no es importante si el bloque `finally` se ejecuta o no.</span><span class="sxs-lookup"><span data-stu-id="f22bc-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="f22bc-111">Pero si tiene instrucciones en un bloque `finally` que debe ejecutarse incluso en esa situación, una solución es agregar un bloque `catch` a la instrucción `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="f22bc-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="f22bc-112">Como alternativa, puede capturar la excepción que se podría producir en el bloque `try` de una instrucción `try`-`finally` más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="f22bc-113">Es decir, puede capturar la excepción en el método que llama al método que contiene la instrucción `try`-`finally`, en el método que llama a ese método o en cualquier método en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="f22bc-114">Si no se captura la excepción, la ejecución del bloque `finally` depende de si el sistema operativo decide desencadenar una operación de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="f22bc-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f22bc-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f22bc-115">Example</span></span>  
 <span data-ttu-id="f22bc-116">En el ejemplo siguiente, una instrucción de conversión no válida provoca una excepción `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="f22bc-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="f22bc-117">Se trata de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="f22bc-117">The exception is unhandled.</span></span>  
  
 <span data-ttu-id="f22bc-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f22bc-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span></span>  
  
 <span data-ttu-id="f22bc-119">En el ejemplo siguiente, se captura una excepción del método `TryCast` en un método más arriba en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-119">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>  
  
 <span data-ttu-id="f22bc-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f22bc-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="f22bc-121">Para obtener más información sobre `finally`, vea [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="f22bc-121">For more information about `finally`, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
 <span data-ttu-id="f22bc-122">C# también contiene la [instrucción using](../../../csharp/language-reference/keywords/using-statement.md), que proporciona una función similar para objetos <xref:System.IDisposable> en una sintaxis adecuada.</span><span class="sxs-lookup"><span data-stu-id="f22bc-122">C# also contains the [using statement](../../../csharp/language-reference/keywords/using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f22bc-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f22bc-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f22bc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f22bc-124">See Also</span></span>  
 <span data-ttu-id="f22bc-125">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f22bc-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f22bc-127">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f22bc-128">[Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="f22bc-128">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="f22bc-129">[Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-129">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="f22bc-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="f22bc-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="f22bc-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 [<span data-ttu-id="f22bc-132">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="f22bc-132">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

