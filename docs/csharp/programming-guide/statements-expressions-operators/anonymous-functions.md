---
title: "Funciones anónimas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
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
ms.openlocfilehash: 9f0105ad5ee5a97243e9aeda42c9b1842ec15d0e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="11cce-102">Funciones anónimas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="11cce-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="11cce-103">Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="11cce-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="11cce-104">Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.</span><span class="sxs-lookup"><span data-stu-id="11cce-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="11cce-105">Hay dos tipos de funciones anónimas, que se describen por separado en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="11cce-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
-   <span data-ttu-id="11cce-106">[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11cce-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
-   [<span data-ttu-id="11cce-107">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="11cce-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="11cce-108">Las expresiones lambda se pueden enlazar a árboles de expresión y también a delegados.</span><span class="sxs-lookup"><span data-stu-id="11cce-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="11cce-109">La evolución de los delegados en C#</span><span class="sxs-lookup"><span data-stu-id="11cce-109">The Evolution of Delegates in C#</span></span>  
 <span data-ttu-id="11cce-110">En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="11cce-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="11cce-111">C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado.</span><span class="sxs-lookup"><span data-stu-id="11cce-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="11cce-112">C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas.</span><span class="sxs-lookup"><span data-stu-id="11cce-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="11cce-113">Estas dos características se conocen colectivamente como *funciones anónimas*.</span><span class="sxs-lookup"><span data-stu-id="11cce-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="11cce-114">En general, las aplicaciones destinadas a la versión 3.5 y posteriores de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] deberían usar expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="11cce-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="11cce-115">En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="11cce-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 <span data-ttu-id="11cce-116">[!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="11cce-116">[!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="11cce-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="11cce-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11cce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="11cce-118">See Also</span></span>  
 <span data-ttu-id="11cce-119">[Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="11cce-119">[Statements, Expressions, and Operators](../../../csharp/programming-guide/statements-expressions-operators/index.md) </span></span>  
 <span data-ttu-id="11cce-120">[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="11cce-120">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="11cce-121">[Delegados](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="11cce-121">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="11cce-122">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="11cce-122">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

