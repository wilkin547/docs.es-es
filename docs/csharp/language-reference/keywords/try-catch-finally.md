---
title: try-catch-finally (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
dev_langs:
- CSharp
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
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
ms.openlocfilehash: 05b2e0075aae79f85fba26d64690eefadaa166cd
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="24552-102">try-catch-finally (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="24552-102">try-catch-finally (C# Reference)</span></span>
<span data-ttu-id="24552-103">Un uso habitual de `catch` y `finally` juntos es obtener y usar recursos de un bloque `try`, lidiar con circunstancias excepcionales de un bloque `catch` y liberar los recursos del bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="24552-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>  
  
 <span data-ttu-id="24552-104">Para más información y ejemplos sobre cómo volver a iniciar excepciones, vea [try-catch](../../../csharp/language-reference/keywords/try-catch.md) y [Generación de excepciones](https://msdn.microsoft.com/library/xhcbs8fz).</span><span class="sxs-lookup"><span data-stu-id="24552-104">For more information and examples on re-throwing exceptions, see [try-catch](../../../csharp/language-reference/keywords/try-catch.md) and [Throwing Exceptions](https://msdn.microsoft.com/library/xhcbs8fz).</span></span> <span data-ttu-id="24552-105">Para más información sobre el bloque `finally`, vea [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="24552-105">For more information about the `finally` block, see [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24552-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24552-106">Example</span></span>  
 <span data-ttu-id="24552-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="24552-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="24552-108">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="24552-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24552-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="24552-109">See Also</span></span>  
 <span data-ttu-id="24552-110">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="24552-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="24552-111">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="24552-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="24552-112">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="24552-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="24552-113">[Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="24552-113">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="24552-114">[Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="24552-114">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="24552-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="24552-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="24552-116">[Cómo: Iniciar excepciones explícitamente](https://msdn.microsoft.com/library/xhcbs8fz) </span><span class="sxs-lookup"><span data-stu-id="24552-116">[How to: Explicitly Throw Exceptions](https://msdn.microsoft.com/library/xhcbs8fz) </span></span>  
 [<span data-ttu-id="24552-117">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="24552-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

