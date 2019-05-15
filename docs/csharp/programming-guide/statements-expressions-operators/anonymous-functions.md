---
title: 'Funciones anónimas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: c949bf5af441728b311391ecb42623951d0145ab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608147"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="f6428-102">Funciones anónimas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f6428-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="f6428-103">Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="f6428-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="f6428-104">Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.</span><span class="sxs-lookup"><span data-stu-id="f6428-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="f6428-105">Hay dos tipos de funciones anónimas, que se describen por separado en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6428-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
- <span data-ttu-id="f6428-106">[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f6428-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
- [<span data-ttu-id="f6428-107">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="f6428-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="f6428-108">Las expresiones lambda se pueden enlazar a árboles de expresión y también a delegados.</span><span class="sxs-lookup"><span data-stu-id="f6428-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="f6428-109">La evolución de los delegados en C\#</span><span class="sxs-lookup"><span data-stu-id="f6428-109">The Evolution of Delegates in C\#</span></span>
 <span data-ttu-id="f6428-110">En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="f6428-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="f6428-111">C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado.</span><span class="sxs-lookup"><span data-stu-id="f6428-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="f6428-112">C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas.</span><span class="sxs-lookup"><span data-stu-id="f6428-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="f6428-113">Estas dos características se conocen colectivamente como *funciones anónimas*.</span><span class="sxs-lookup"><span data-stu-id="f6428-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="f6428-114">En general, las aplicaciones destinadas a la versión 3.5 y posteriores de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] deberían usar expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="f6428-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="f6428-115">En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="f6428-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f6428-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f6428-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6428-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6428-117">See also</span></span>

- [<span data-ttu-id="f6428-118">Instrucciones, expresiones y operadores</span><span class="sxs-lookup"><span data-stu-id="f6428-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="f6428-119">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="f6428-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="f6428-120">Delegados</span><span class="sxs-lookup"><span data-stu-id="f6428-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="f6428-121">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="f6428-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
